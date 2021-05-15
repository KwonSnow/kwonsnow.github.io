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


## 1D PWDFT 만들기
1. hydrogen orbital 구성 ✓
2. DFT (or FFT)
3. n(r) 구하기.


##Plane-Wave Basis Sets  
[Introduction to DFT and the plane-wave pseudopotential method](https://www.archer.ac.uk/training/course-material/2014/04/PMMP_UCL/Slides/castep_1.pdf)  
<p><span class="math inline">\(\psi_{i, \boldsymbol{k}}(\boldsymbol{r})=\sum_{\boldsymbol{G}}^{|\boldsymbol{G}|&lt;G_{\max }} c_{i \boldsymbol{k}, \boldsymbol{G}} e^{i(\boldsymbol{k}+\boldsymbol{G}) \cdot \boldsymbol{r})}\)</span></p>  
Fourier Series expansion of (r): Fourier coefficients c<sub>ik,G</sub> stored on regular grid of G.  
Gs are reciprocal lattice vectors and k is a symmetry label in the 1st Brillouin zone.

Bloch's Theorem  
<p><span class="math inline">\(\phi_{\boldsymbol{k}}(\boldsymbol{r})=\exp (i \boldsymbol{k} \cdot \boldsymbol{r}) u_{\boldsymbol{k}}(\boldsymbol{r})\)</span></p>  
실제계산에서는 k-space에서의 적분을 discrete Fourier transfrom 하게 된다. 따라서 planewave를 DFT를 하면 coefficient인 u<sub>k</sub>(r)을 저장함.  
Charge density는 u<sub>k</sub>(r)을 Brillouin zone (BZ)에 대해 아래와 같이 표현할 수 있음.  
<p><span class="math inline">\(n(\boldsymbol{r})=\sum_{m} \int_{\mathrm{BZ}} d \boldsymbol{k} \quad u_{m \boldsymbol{k}}^{*}(\boldsymbol{r}) u_{m \boldsymbol{k}}(\boldsymbol{r})\)</span></p>  
여기서 m은 dimemsion을 나타내는데, real-space lattice vector R과 reciprocal lattice vector G는 G·R=2πm의 관계를 가지고, 여기서 m은 정수이다.  


주의: Charge density를 얻으려면 여기서 inverse DFT가 아니라 square 곱을 해줘야 함. 역시 적분을 해야하는데, 이때도 grid에서의 sum을 해준다.  
<p><span class="math inline">\(\sum_{k}^{\mathrm{BZ}}\)</span></p>  
실제 계산에서는 c<sub>mkG</sub> 과 n(r)을 둘다 3D grid에 저장하고, FFT를 통해서 real-space와 reciprocal-space를 mapping 함.예를 들어, n(r)은 다음과 같이 구하는데,  
<p><span class="math inline">\(n(\boldsymbol{r})=\sum_{\boldsymbol{k}} \sum_{m}^{\mathrm{occ}}\left|u_{m \boldsymbol{k}}(\boldsymbol{r})\right|^{2}\)</span></p>  
where  
<p><span class="math inline">\(u_{m \boldsymbol{k}}(\boldsymbol{r})=\sum_{\boldsymbol{G}} c_{m \boldsymbol{k}}(\boldsymbol{G}) \exp (i \boldsymbol{G} \cdot \boldsymbol{r})\)</span></p>  
이러한 mapping은 u<sub>mk</sub>(G)를 real-spalce로 transformation 시키기 위해 each band와 k-point 당 한번씩 FFT를 하게 된다.  
Hartree, local, potential terms을 계산하기 위해 우리는  
<p><span class="math inline">\(n(\boldsymbol{G})=\sum_{r} n(\boldsymbol{r}) \exp (-i \boldsymbol{G} \cdot \boldsymbol{r})\)</span></p>  
이 필요하다.  
plane-wave coefficients c<sub>mk</sub>(G)로 표현된 total KS energy는
<p><span class="math inline">\(\begin{aligned} E_{\mathrm{KS}} &amp;=\sum_{\boldsymbol{k}} \sum_{m} \sum_{\boldsymbol{G}}|\boldsymbol{G}+\boldsymbol{k}|^{2}\left|c_{m \boldsymbol{k}}(\boldsymbol{G})\right|^{2}+\sum_{G \neq 0} V_{\mathrm{ext}}(\boldsymbol{G}) n(\boldsymbol{G}) \\ &amp;+\sum_{G \neq 0} \frac{|n(\boldsymbol{G})|^{2}}{|\boldsymbol{G}|^{2}}+\int d \boldsymbol{r} n(\boldsymbol{r}) \varepsilon_{\mathrm{xc}}(n(\boldsymbol{r}))+E_{\mathrm{II}}\left(\left\{\boldsymbol{R}_{I}\right\}\right) \end{aligned}\)</span></p>  



애초에 planewave가 grid의 형태로 표현될텐데, 처음에 grid는 어떻게 설정?  
discrete planewave -> DFT (or FFT) -> u<sub>k</sub>(r) -> BZ integration (Monkhorst-Pack) -> n(r)  

우리가 cutoff energy를 정하게 되면, 아래 식에 의해 G<sub>max</sub>을 정하게 된다.  
<p><span class="math inline">\(E_{c}=\frac{\hbar^{2} G_{\max }^{2}}{2 m_{e}}\)</span></p>  
결국 reciprocal lattice에서 어느정도의 범위를 계산에 넣을 것인지 (2D에서는 원, 3D에서는 구) 한계를 두게 되는데, FFT할 때 이것의 두배 정도 되는 grid를 고려(2k<sub>cut</sub>)한다.




Hohenberg-Kohn Functional in Momentum Space:  
[The Plane-Wave Pseudopotential Method](https://th.fhi-berlin.mpg.de/th/Meetings/FHImd2001/pehlke1.pdf)

