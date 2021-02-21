---
title: "DFT parallelization"
date: 2021-02-20T08:08:50-04:00
category: DFT
tags:
  - VASP
  - JDFTx
  - parallelization
---

VASP은 NCORE와 --ntasks-per-node를 기준으로 TEST  
예를들어 노드당 코어수가 128개라면, --ntasks-per-node는 2, 4, 8, 16, 32, 64, 128개를 TEST할 수 있음.  
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


