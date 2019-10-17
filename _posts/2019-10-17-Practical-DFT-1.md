---
title: "Practical DFT"
date: 2019-10-17T08:08:50-04:00
category: DFT
tags:
  - Quantum Mechanics
  - DFT
---

# Practical DFT

## Kohn-Sham Theorm

Many body calculation과 동일한 결과를 얻을 수 있다.여기서의 결과란 Exact ground state E 과 Exact n(r).  
n(r) = number density = # of electron / volume  
If!! we do following:  
<p><span class="math inline">\(\mathrm{n}(\mathrm{r})=\sum_{i}\left|\varphi_{i}(r)\right|^{2}\)</span></p>

<p><span class="math inline">\(\mathrm{E}=\min_{\left\{\varphi_{i}(r), f_{i}\left|\sum_{i} f_{i}=N_{e l}\right| \int \varphi_{i}^{*}(r) \varphi_{i}(r) d^{3} r=\delta_{i j}\right\}}\left(T_{N}+T_{e l}+U_{N-N}+U_{N-e l}+U_{e l-e l}\right)\)</span></p>

<p><span class="math inline">\(T_{e l}=\sum_{i} f_{i} \int \varphi_{i}^{*}(r)\left[-\frac{1}{2} \frac{\hbar}{m_{e}} \varphi_{i}(r)\right] d^{3} r\)</span></p>

<p><span class="math inline">\(U_{N-N}=\frac{1}{2} k_{c} \sum_{I \neq J} \frac{\left(+Z_{I} e\right)\left(+Z_{J} e\right)}{\left|R_{I}-R_{J}\right|}=\frac{1}{2} k_{C} \sum_{I \neq J} \frac{Z_{I} Z_{J}}{\left|R_{I}-R_{J}\right|}\)</span></p>

<p><span class="math inline">\(U_{N-e l}=\int n(r) d^{3} r V_{n u c}(r)\)</span></p>

<p><span class="math inline">\(V_{n u c}(r)=k_{c} \sum_{I} \frac{(-e)\left(+Z_{I} e\right)}{\left|r-R_{I}\right|}=-k_{c} e^{2} \sum_{I} \frac{Z_{I}}{\left|r-R_{I}\right|}\)</span></p>

<p><span class="math inline">\(U_{H}=\frac{1}{2} \int d^{3} r \int d^{3} r^{\prime} \frac{[-e n(r)]\left[-e n\left(r^{\prime}\right)\right]}{\left|r-r^{\prime}\right|}=\frac{1}{2} k_{c} e^{2} \iint \frac{n(r)\left|n\left(r^{\prime}\right)\right|}{\left|r-r^{\prime}\right|}\)</span></p>




Reference: https://www.youtube.com/watch?v=dGYOsRsLII4&list=PLEawDeF-ZtxAfrW3qVy0Yj3wcDyJmZa_a&index=2


