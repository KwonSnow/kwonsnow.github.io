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
DFT의 주요한 개발이 이루어지고 있던 2000년대 중반에는 semi-local density functional (GGA)가 dispersion을 정확히 기술하지 못한다는 것이 알려졌고, 이는 최근에야 Non-local correlation (NLC) fuctionals의 개발로 어느정도 해결된 문제이다. 그럼에도 -C<sub>6</sub>/R<sup>6</sup>의 형태를 가진 empirical potential 을 도입하여 아주 빠르고 간단하게 이를 기술할 수 있다. NLC functional을 사용하지 않는 이러한 접근방식을 dispersion-corrected DFT (DFT-D)라고 한다. 가장 오래된 방법은 Stefan Grimme이 개발한 [DFT-D2](https://doi.org/10.1002/jcc.20495)로 다음과 같은 pairwise atomic term을 가지고 있다.  

<p><span class="math display">$$E_{\text {disp }}^{\mathrm{D} 2}=-s_6
\sum_A^{\text {atoms atoms }} \sum_{B&lt;A}\left(\frac{C_{6, A B}}{R_{A
B}^6}\right) f_{\text {damp }}^{\mathrm{D} 2}\left(R_{A
B}\right)$$</span></p>

<p><span class="math display">R_{AB}^6</span></p>

이 함수는 발산하는 R<sup>-6</sup> term 때문에 short range에서 감폭(damping)하도록 f<sub>damp</sub> 함수가 곱해져 있다.

<p><span class="math display"><em>f</em><sub>damp
</sub><sup>D2</sup>(<em>R</em><sub><em>A</em><em>B</em></sub>) = [1+<em>e</em><sup>−<em>d</em>(<em>R</em><sub><em>A</em><em>B</em></sub>/<em>R</em><sub>0, <em>A</em><em>B</em></sub>−1)</sup>]<sup>−1</sup></span></p>

이는 추가적인 효과가 있는데, 바로 electron correlation의 double-counting을 피할 수 있게 해준다. 왜냐하면 short- to medium-range correlation은 이미 density functional을 통해 어느정도 포함되어 있기 때문이다.


## [Exchange-Dipole Model (XDM)](https://manual.q-chem.com/5.2/Ch5.S7.SS3.html)  
## [Tkatchenko-Scheffler van der Waals Model (TS-vdW)](https://manual.q-chem.com/5.2/Ch5.S7.SS4.html)  
## [Many-Body Dispersion (MBD) Method](https://manual.q-chem.com/5.2/Ch5.S7.SS5.html)  


