---
title: "Density Functional Theory"
date: 2019-10-17T08:08:50-04:00
category: DFT
tags:
  - Quantum Mechanics
  - DFT
---

# Practical DFT-1

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
예를 들어 electron cloud에 electron이 하나 위치해 있다면, 이 electron은 그저 주변의 평균적인 charge density를 느끼지 않는다. 왜냐하면 만약 이 electron은 다른 electron과의 correlation 때문에 서로를 밀어낼 것이기 때문 by Pauli exclusion and Coulombic repulsion.  따라서 Something missing from the mean field description. 이것을 고려해주기 위하여 E(XC) 추가. (그런데 이미 Pauli exclusion은 orbital orthonormality, Coulomic repulsion은 U(el-el)로 고려하지 않았나?)  
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

### Solve Poisson's Equation
(1) Simplification
(2) Choose computational representation 
Expand in basis
<p><span class="math inline">\(n(r)=\sum_{\alpha} \hat{n}_{\alpha} b_{\alpha}(r)\)</span></p>
<p><span class="math inline">\(\varphi(r)=\sum_{\alpha} \hat{\varphi}_{\alpha} b_{\alpha}(r)\)</span></p>

  
---
Reference: Youtube: ['https://youtu.be/eixqE1mRZEw/'](https://youtu.be/eixqE1mRZEw/)



