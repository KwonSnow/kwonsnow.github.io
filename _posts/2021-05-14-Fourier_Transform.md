---
title: "Fourier Transformation"
date: 2021-05-15T08:08:50-04:00
category: Mathematics
tags:
  - Fourier Transformation
---

Desktop\Project\Mathematics\Descrete_Fourier_Transform_1.ipynb  

[Fourier Transform(푸리에 변환)의 이해와 활용](https://darkpgmr.tistory.com/171)  
[python으로 신호 푸리에 변환하는 방법](https://ballentain.tistory.com/3)  
[Fourier transform 근사와 신호분석](https://wikidocs.net/14635)  
[형보다 나은 아우: 푸리에 변환(Fourier Transform)](https://ghebook.blogspot.com/2012/08/fourier-transform.html)  


autocorrelation function  
PWDFT, reciprocal lattice  


[Introduction to DFT and the plane-wave pseudopotential method](https://www.archer.ac.uk/training/course-material/2014/04/PMMP_UCL/Slides/castep_1.pdf)  
Bloch's Theorem  
<p><span class="math inline">\(\phi_{\boldsymbol{k}}(\boldsymbol{r})=\exp (i \boldsymbol{k} \cdot \boldsymbol{r}) u_{\boldsymbol{k}}(\boldsymbol{r})\)</span></p>  
실제계산에서는 k-space에서의 적분을 discrete Fourier transfrom 하게 된다. 따라서 planewave를 DFT를 하면 coefficient인 u<sub>k</sub>(r)을 저장함.  
Charge density는 u<sub>k</sub>(r)을 Brillouin zone (BZ)에 대해 아래와 같이 표현할 수 있음.  
<p><span class="math inline">\(n(\boldsymbol{r})=\sum_{m} \int_{\mathrm{BZ}} d \boldsymbol{k} \quad u_{m \boldsymbol{k}}^{*}(\boldsymbol{r}) u_{m \boldsymbol{k}}(\boldsymbol{r})\)</span></p>  
여기서 m은?  
주의: Charge density를 얻으려면 여기서 inverse DFT가 아니라 square 곱을 해줘야 함. 역시 적분을 해야하는데, 이때도 grid에서의 sum을 해준다. 
<p><span class="math inline">\int_{\mathrm{BZ}} d \boldsymbol{k}</span></p>
->  
<p><span class="math inline">\(\sum_{k}^{\mathrm{BZ}}\)</span></p>
애초에 planewave가 grid의 형태로 표현될텐데, 처음에 grid는 어떻게 설정?  
discrete planewave -> DFT (or FFT) -> u<sub>k</sub>(r) -> BZ integration (Monkhorst-Pack) -> n(r)  




Hohenberg-Kohn Functional in Momentum Space:  
[The Plane-Wave Pseudopotential Method](https://th.fhi-berlin.mpg.de/th/Meetings/FHImd2001/pehlke1.pdf)

