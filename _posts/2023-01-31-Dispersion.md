---
title: "Dispersion interaction"
date: 2023-01-31T08:08:50-04:00
category: Quantum Mechanics
tags:
  - Dispersion
---



# [DFT Methods for van der Waals Interactions](https://manual.q-chem.com/5.2/Ch5.S7.html)
## [Non-Local Correlation (NLC) Functionals](https://manual.q-chem.com/5.2/Ch5.S7.SS1.html)  
## [Empirical Dispersion Corrections: DFT-D](https://manual.q-chem.com/5.2/Ch5.S7.SS2.html)  
DFT의 주요한 개발이 이루어지고 있던 2000년대 중반에 semi-local density functional (GGA)가 dispersion을 정확히 기술하지 못한다는 것이 알려졌고, 이는 최근에야 Non-local correlation (NLC) fuctionals의 개발로 어느정도 해결된 문제이다. 그럼에도 -C<sub>6</sub>/R<sup>6</sup>의 형태를 가진 empirical potential 을 도입하여 아주 빠르고 간단하게 이를 기술할 수 있다. NLC functional을 사용하지 않는 이러한 접근방식을 dispersion-corrected DFT (DFT-D)라고 한다. 
### DFT-D2
가장 오래된 방법은 Stefan Grimme이 개발한 [DFT-D2](https://doi.org/10.1002/jcc.20495)로 다음과 같은 pairwise atomic term을 가지고 있다.  

<p><span class="math display">$$E_{\text {disp }}^{\mathrm{D} 2}=-s_6
\sum_A^{\text {atoms }} \sum_{B&lt;A}^{\text {atoms }}\left(\frac{C_{6, A B}}{R_{A
B}^6}\right) f_{\text {damp }}^{\mathrm{D} 2}\left(R_{A
B}\right)$$</span></p>

이 함수는 발산하는 R<sup>-6</sup> term 때문에 short range에서 감폭(damping)하도록 f<sub>damp</sub> 함수가 곱해져 있다.

<p><span class="math display"><em>f</em><sub>damp
</sub><sup>D2</sup>(<em>R</em><sub><em>A</em><em>B</em></sub>) = [1+<em>e</em><sup>−<em>d</em>(<em>R</em><sub><em>A</em><em>B</em></sub>/<em>R</em><sub>0, <em>A</em><em>B</em></sub>−1)</sup>]<sup>−1</sup></span></p>

이를 통해 추가적인 효과를 얻는데, 바로 electron correlation의 double-counting을 피할 수 있게 해준다. 왜냐하면 short- to medium-range correlation은 이미 density functional을 통해 어느정도 포함되어 있기 때문이다. 여기서 R<sub>0</sub> term은 atom A와 atom B의 van der Waals radii의 합이고 d는 추가적인 파라미터이다.  
가장 중요한 파라미터는 atomic coefficient인 C<sub>6</sub> 인데 이는 classical force field에서 흔한 방법인 [geometric mean](https://en.wikipedia.org/wiki/Geometric_mean)을 통해 얻어진다.
<p><span
class="math display"><em>C</em><sub>6, <em>A</em><em>B</em></sub> = (<em>C</em><sub>6, <em>A</em></sub><em>C</em><sub>6, <em>B</em></sub>)<sup>1/2</sup></span></p>
따라서 Total Energy는 
<p><span
class="math display"><em>E</em><sub>DFT − D2</sub> = <em>E</em><sub>KS − DFT</sub> + <em>E</em><sub>disp
</sub><sup>D2</sup></span></p>

### DFT-D3
이후에 개발된 [DFT-D3](https://doi.org/10.1063/1.3382344) method는 C2와 비슷하지만 atomic C<sub>8</sub> term이 추가되었다.
<p><span class="math display">$$E_{\mathrm{D} 3,2-\text { body
}}=-\sum_A^{\text {atoms }}
\sum_{B&lt;A}^{\text {atoms }}\left[s_6\left(\frac{C_{6, A B}}{R_{A B}^6}\right) f_{\text
{damp }, 6}\left(R_{A B}\right)+s_8\left(\frac{C_{8, A B}}{R_{A
B}^8}\right) f_{\text {damp }, 8}\left(R_{A
B}\right)\right]$$</span></p>
s<sub>6</sub> 일반적으로 1 이고, s<sub>8</sub>는 사용하는 functional에 따라 최적화 된 값이다.

DFT-D3의 "zero-dampling" version인 DFT-D3(0)는 아래와 같은 damping function을 사용한다.
<p><span class="math display">$$f_{\text {damp }, n}^{\mathrm{D}
3(0)}\left(R_{A B}\right)=\left[1+6\left(\frac{R_{A B}}{s_{r, n} R_{0, A
B}}\right)^{-\beta_n}\right]^{-1}$$</span></p>

R<sub>0,AB</sub>는 D2에서와 마찬가지로 van der Waals radii로 구하고, n=6 or 8, β<sub>6</sub>=12, β<sub>8</sub>=14, s<sub>r,6</sub>는 functional-dependent parameter이고 s<sub>r,8</sub>=1.

### DFT-D3(BJ)
그 이후에 Becke와 Johnson이(BJ) 개발한 DFT-D3의 damping version은 DFT-D3(BJ) R<sub>AB</sub> → 0 일때 finite value를 갖는 damping function을 사용한다.
<p><span class="math display">$$f_{\text {damp }, n}^{\mathrm{D}
3(\mathrm{BJ})}\left(R_{A B}\right)=\frac{R_{A B}^n}{R_{A
B}^n+\left(\alpha_1 R_{0, A B}+\alpha_2\right)^n}$$</span></p>
여기서 α<sub>1</sub>과 α<sub>2</sub>는 functional에 따라 조정이 가능한 파라미터이고, DFT-D3(0)에서처럼 s<sub>6</sub> 일반적으로 1 로 고정되고, s<sub>8</sub>는 사용하는 functional에 따라 최적화 된 값이다. DFT-D3(BJ)는 일반적으로 DFT-D3(0)에 비해 성능이 우수하다.[Journal of Computational Chemistry 2011, 32 (7), 1456](https://doi.org/10.1002/jcc.21759)

## [Exchange-Dipole Model (XDM)](https://manual.q-chem.com/5.2/Ch5.S7.SS3.html)  
## [Tkatchenko-Scheffler van der Waals Model (TS-vdW)](https://manual.q-chem.com/5.2/Ch5.S7.SS4.html)  
## [Many-Body Dispersion (MBD) Method](https://manual.q-chem.com/5.2/Ch5.S7.SS5.html)  


