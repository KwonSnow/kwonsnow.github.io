---
title: "Density Functional Theory"
date: 2019-10-17T08:08:50-04:00
category: DFT
tags:
  - Quantum Mechanics
  - DFT
---

# Practical DFT by A. T. Arias

## Kohn-Sham Theorem

> If we do the following:  
> <p><span class="math inline">\(\mathrm{E}=\min_{\left\{\varphi_{i}(r), f_{i}\left|\sum_{i} f_{i}=N_{e l}\right| \int \varphi_{i}^{*}(r) \varphi_{i}(r) d^{3} r=\delta_{i j}\right\}}\left(T_{N}+T_{e l}+U_{N-N}+U_{N-e l}+U_{e l-e l}\right)\)</span></p>
> Many body calculation과 동일한 결과를 얻을 수 있다.  

여기서의 결과란 Exact ground state E 와 Exact n(r).  
where  
n(r) = number density = # of electron / volume  
<p><span class="math inline">\(\mathrm{n}(\mathrm{r})=\sum_{i}\left|\varphi_{i}(r)\right|^{2}\)</span></p>

<p><span class="math inline">\(T_{e l}=\sum_{i} f_{i} \int \varphi_{i}^{*}(r)\left[-\frac{1}{2} \frac{\hbar}{m_{e}} \varphi_{i}(r)\right] d^{3} r\)</span></p>

<p><span class="math inline">\(U_{N-N}=\frac{1}{2} k_{c} \sum_{I \neq J} \frac{\left(+Z_{I} e\right)\left(+Z_{J} e\right)}{\left|R_{I}-R_{J}\right|}=\frac{1}{2} k_{C} e^{2} \sum_{I \neq J} \frac{Z_{I} Z_{J}}{\left|R_{I}-R_{J}\right|}\)</span></p>

<p><span class="math inline">\(U_{N-e l}=\int n(r) d^{3} r V_{n u c}(r)\)</span></p>

<p><span class="math inline">\(V_{n u c}(r)=k_{c} \sum_{I} \frac{(-e)\left(+Z_{I} e\right)}{\left|r-R_{I}\right|}=-k_{c} e^{2} \sum_{I} \frac{Z_{I}}{\left|r-R_{I}\right|}\)</span></p>

<p><span class="math inline">\(U_{e l-e l}=U_{H}+E_{x c}[n(r)]\)</span></p>

<p><span class="math inline">\(U_{H}=\frac{1}{2} \int d^{3} r \int d^{3} r^{\prime} \frac{[-e n(r)]\left[-e n\left(r^{\prime}\right)\right]}{\left|r-r^{\prime}\right|}=\frac{1}{2} k_{c} e^{2} \iint \frac{n(r)\left|n\left(r^{\prime}\right)\right|}{\left|r-r^{\prime}\right|}\)</span></p>


여기서의 문제는 electron 사이의 correlation이 있다는 것.  
예를 들어 electron cloud에 electron이 하나 위치해 있다면, 이 electron은 그저 주변의 평균적인 charge density를 느끼지 않는다. 왜냐하면 만약 이 electron은 다른 electron과의 correlation 때문에 서로를 밀어낼 것이기 때문 by Pauli exclusion and Coulombic repulsion.  따라서 Something missing from the mean field description. 이것을 고려해주기 위하여 E(XC) 추가. (그런데 이미 Pauli exclusion은 orbital orthonormality, Coulomic repulsion은 U(el-el)로 고려하지 않았나?) Hartree-Fock theory is a single-particle approximation, and therefore cannot adequately treat the correlated motion of electrons that occurs due to electron-electron interactions.  
Kohn-Sham theorem의 강점은 이러한 E(XC)를 간단한(?) 형태로 표현할 수 있다는 것. exchange referring to the Pauli exclusion effect and the correlation referring to the additional dynamical correlations that the electron repel each other? 그리고 이것은 density의 함수로 나타낼 수 있음. 문제는 이러한 함수가 있다는 것은 알지만 (?) 어떻게 구성하는지는 모른다는 것. 괜찮은 approximatoin으로  LDA를 예로들 수 있다.

### Local Density Approximation (LDA)  
<p><span class="math inline">\(E_{X C}[n(r)]=\int f_{X C}(n(r)) d^{3} r\)</span></p>

![image-center]({{ 'images/Practical_DFT_1.PNG' | absolute_url }}){: .align-center}



### Computational attack (for any problem)
(1) as many analytic simplications as possible.
choose appropriate system of units. fundamental constant를 code에 넣는 것을 최대한 피한다.  
  
(2) Elimination of double integral
Mean field Hartree energy, U(H), 빼고는 다 single integral. U(H)는 double integral over spcae 포함되어 있고, 이걸 직접적으로 계산하려면 six dimentional sum을 해야하는데 그렇게 되면 계산이 너무 비싸지게 된다.
<p><span class="math inline">\(U_{H}=\frac{1}{2} \int n(r) \varphi(r) d^{3} r\)</span></p>
<p><span class="math inline">\(\varphi(r)=\int \frac{n\left(r^{\prime}\right) d^{3} r^{\prime}}{\left|r-r^{\prime}\right|}\)</span></p>
물론 이것은 약간 문제를 덮어두는 식이지만, 뭐 어쨌든 이렇게 하면 각 point에서 3차원 적분만 하면 된다.
one way to get around the action and distance thing is to take the field seriously. And look at the field equation. Then just couples neighboring points. And the corresponding field equation here is.... Poisson equation
위의 두 식을 푼다는 것은 적절한 boundary condition을 가지고 아래의 Poisson equation을 푸는 것과 같다.  

<p><span class="math inline">\(\nabla^{2} \varphi(r)=-4 \pi n(\mathrm{r})    w / B . C .^{\prime} S\)</span></p>
Solid의 경우 이 B.C.는 PBC.  

---
전기장을 나타내는 식인 Gauss법칙에
<p><span class="math inline">\(\nabla \cdot \vec{E}=\frac{\rho(\vec{r})}{\varepsilon_{0}}\)</span></p>
전기장과 포텐셜을 나타내는 관계식을 대입하면
<p><span class="math inline">\(\vec{E}=-\nabla V\)</span></p>
Poisson 식이 나타남.  
<p><span class="math inline">\(\nabla^{2} V(\vec{r})=-\frac{\rho}{\varepsilon_{0}}\)</span></p>
따라서 전하가 놓였을때 그것으로 부터 파생되는 포텐셜(전위)를 구할 수 있게 됨.  

---
### Solve Poisson's Equation
(1) Simplification  
(2) Choose computational representation  
Expand in basis
<p><span class="math inline">\(n(r)=\sum_{\alpha} \hat{n}_{\alpha} b_{\alpha}(r)=\sum_{\alpha} \hat{\bar{n}}_{\alpha} b_{\alpha}(r)\)</span></p>
<p><span class="math inline">\(\varphi(r)=\sum_{\alpha} \hat{\varphi}_{\alpha} b_{\alpha}(r)=\sum_{\alpha} \hat{\bar{\varphi}}_{\alpha} b_{\alpha}(r)\)</span></p>
공간의 서로 다른 지점에서 sample value를 얻기 위한 함수를 표현하기 위해 finite set of coefficient를 하나의 벡터로 표기. 벡터는 모두 column vector로 표기. row vector가 필요할 경우 column vector를 transpose.  
Poisson's Equation에 위의 computational representation을 대입하면,
<p><span class="math inline">\(\nabla^{2} \sum_{\alpha} \widehat{\varphi}_{\alpha} b_{\alpha}(r)=-4 \pi \sum_{\alpha} \hat{n}_{\alpha} b_{\alpha}(r)\)</span></p>

여기서 문제는 공간내 무한대의 점 (r)을 유한한 수로 표현해야 한다는 점. 즉, 공간을 coefficient 또는 basis function과 같은 수로 표현할 수 있어야 한다. 이럴 경우 standard method로 [Galerkin Method](https://en.wikipedia.org/wiki/Galerkin_method) 사용.
<p><span class="math inline">\(\int d^{3} r b_{\beta}^{*}(r) \cdots\)</span></p>
Take both sides of equation and integrate them against the complex conjugates of all of the basis functions. That will give you as many conditions its basis functions. 이러한 방법으로 공간(r)을 discretize 함.
<p><span class="math inline">\(\sum_{\alpha}\left(\int d^{3} r\left[b_{\beta}^{*}(r) \nabla^{2} b_{\alpha}(r)\right]\right) \hat{\varphi}_{\alpha}=-4 \pi \sum_{\alpha}\left[\int d^{3} r\left(b_{\beta}^{*}(r) b_{\alpha}(r)\right)\right] \hat{n}_{\alpha}\)</span></p>
왼쪽의 적분항은 some set of numbers that is defined by basis so I might as well give it a name. It is the matrix elements within my basis of the Laplacian operator. so call it L.  
오른쪽의 적분항은 overlaps of basis functions. so call it O. (만약 basis가 orthnormal 하다면 이 항은 identity) 
<p><span class="math inline">\(\mathbb{L} \vec{\varphi}=-4 \pi \mathbb{O} \vec{n}\)</span></p>
따라서 이제 목표는 Poisson's equatoin을 푸는 것 = 주어진 density로 potential을 구한다. 이것의 해는
<p><span class="math inline">\(\hat{\bar{\varphi}}=\mathbb{L}^{-1}(-4 \pi \mathbb{O} \hat{\vec{n}})\)</span></p>

<p><span class="math inline">\(\varphi_{p}=\varphi\left(r_{p}\right)=\sum_{\alpha} \hat{\varphi}_{\alpha} b_{\alpha}\left(r_{p}\right)=\sum_{\alpha} I_{p \alpha} \hat{\varphi}_{\alpha}\)</span></p>
p에서의 sample value phi_p는 linear transform on computational representation 으로부터 구할 수 있다. The kernel for the representation then are these values of basis functions?
여기서 coulmn vector 형식을 유지하면서 
<p><span class="math inline">\(\vec{\varphi}=\mathbb{L} \widehat{\varphi}\)</span></p>
<p><span class="math inline">\(\vec{n}=\mathbb{I} \hat{\vec{n}}\)</span></p>
<p><span class="math inline">\(\mathbb{J}=\mathbb{I}^{-1}\)</span></p>
<p><span class="math inline">\(\hat{\vec{n}}=\mathbb{J} \vec{n}\)</span></p>




---
Reference: Youtube: [https://youtu.be/dGYOsRsLII4](https://youtu.be/dGYOsRsLII4)



