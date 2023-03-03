---
title: "DFT parallelization"
date: 2021-02-20T08:08:50-04:00
category: DFT
tags:
  - VASP
  - JDFTx
  - parallelization
---


[Optimizing the parallelization](https://www.vasp.at/wiki/index.php/Optimizing_the_parallelization)  
[https://www.nsc.liu.se/~pla/blog/2015/01/12/vasp-how-many-cores/](https://www.nsc.liu.se/~pla/blog/2015/01/12/vasp-how-many-cores/)  


NBANDS = max(NELECT/2+NIONS/2,NELECT*0.6)  

### NPAR
[NPAR](https://www.vasp.at/wiki/index.php/NPAR)는 코어당 Band수를 정하는 것으로, 기본적으로 [NBANDS](https://www.vasp.at/wiki/index.php/NBANDS)를 NPAR를 통해서 number of task로 나누고, 각 task마다 하나의 코어를 할당한다. 예를 들어 Ag FCC conventional cell (NIONS=4)의 경우 NBANDS = 27 인데 이를 28로 올리고 7 tasks(w/ NPAR=4)로 계산하던지 NBANDS=32로 늘리고 4 tasks(w/ NPAR=8)로 계산할 수 있다. One ionic step 결과만 보면 Total CPU time (Elapsed time)은 각각 78.175(80.608), 78.231(82.239) 로 별반 차이가 없다. 후자가 적은 수의 코어(4)를 쓰기 때문에, NPAR=8로 하는 것이 좋다. 이는 또한 stampede2 KNL의 경우 [sqrt(64)](https://www.vasp.at/wiki/index.php/NPAR) = 8과 일치한다.  

w/ NPAR = 8  
#SBATCH --nodes 1               # Total # of nodes  
#SBATCH --ntasks-per-node 4  
#SBATCH --ntasks-per-core 1    # Run only one MPI process per CPU core  
#SBATCH --cpus-per-task   4    # Number of OpenMP threads per MPI process # KNL has 4 thread per core  

위의 경우 stampede2 KNL와 같은 하이퍼스레딩 프로세서의 경우 하나의 코어당 가능한 thread(가상코어)를 늘릴 수 있다. 


[NBANDS](https://www.vasp.at/wiki/index.php/NBANDS)는 better convergence를 위해서 최소한 
k-ponits grid가 큰 경우 NPAR와 KPAR를 동시에 사용하여 각 band 내에서 k-점 그리드를 분할하여 각각의 작업에 할당된 프로세서에서 병렬 처리할 수 있다. 

NBANDS는 NCORE나 KPAR에 따라 달라질 수 있으므로, NPAR를 사용하는 경우 NCORE나 KPAR를 사용하지 않도록 주의한다.


VASP은 NCORE와 --ntasks-per-node를 기준으로 TEST  
예를들어 노드당 코어수가 128개라면, --ntasks-per-node는 2, 4, 8, 16, 32, 64, 128개를 TEST할 수 있음.  
하지만, Expanse (SDSC) 처럼 core단위가 아니라 node단위로 청구하는 곳에서는 128개를 안쓸 이유가 없음.  

https://www.vasp.at/wiki/index.php/NCORE  
NCORE = 2 up to number-of-cores-per-socket (or number-of-cores-per-node)  
For large unit cells, we found that this can improve the performance by up to a factor four compared to the default, and it also significantly improves the stability of the code due to reduced memory requirements. Ideally, NCORE should be a factor of the number-of-cores-per-socket (or number-of-cores-per-node), since this reduces communication between the sockets or nodes. The best value NCORE depends somewhat on the number of atoms in the unit cell. Values around 4 are usually ideal for 100 atoms in the unit cell. For very large unit cells (more than 400 atoms) values around 12-16 are often optimal. If you run extensive simulations for similar systems, make your own tests.  

--ntasks-per-node=16, NCORE=4 로 설정하면 OUTCAR에는  
 running on   16 total cores  
 distrk:  each k-point on   16 cores,    1 groups  
 distr:  one band on NCORES_PER_BAND=   4 cores,    4 groups  
로 표기 됨.  

NCORE와 --ntasks-per-node를 같은 값으로 설정하라는 곳도 있음.  
[https://docs.ycrc.yale.edu/clusters-at-yale/guides/vasp/](https://docs.ycrc.yale.edu/clusters-at-yale/guides/vasp/)  
이렇게 할 경우 변수가 줄어들어서 test할 값이 적어지므로 좋음.  


JDFTx는 --cpus-per-task와 --ntasks-per-node를 기준으로 TEST  


