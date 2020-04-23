---
title: "Basis Set Issues"
date: 2019-10-23T05:08:50-04:00
category: DFT
tags:
  - DFT
  - Basis set
---

# Linear dependence
[1]  
큰 basis set, 특히 diffuse function (or  those with several closely spaced sets of off-centered functions)을 갖는 basis set으로 계산을 수행할 경우 linear dependency에 의한 numerical instabilities를 겪게 된다. 이러한 문제는 periodic systems나 large set of bonding functions를 사용하는 경우에 발생한다.  
HF level과 correlated calculation에서의 문제의 성격이 약간 다른데, HF equations에서는 construction of an orthgonalizing transformation matrix S<sup>-1/2</sup> (S: overlap matrix) 할 때 발생한다. near linear dependence basis set의 경우 S matrix의 eigenvalues가 너무 작아서 S<sup>-1/2</sup>을 구성할 때 nearly zero로 나눠야 하기 때문에 singularity가 발생하게 되고 따라서 precision에 영향을 미치게 된다. correlated calculation에서는 near linear dependence가 있으면 매우 큰 molecular orbital (MO) coefficients for virtual orbitals를 야기한다. 예를 들면, MO coefficient가 1000이면, 그러한 4 개의 coefficient들의 곱은 10<sup>12</sup>이 된다. two-electron integral의 정확도는 기껏해야 10<sup>-14</sup> 정도이기 때문에, the transformed integral은 매우 큰 numerical error를 가지게 된다.  
이 문제의 심각성을 평가하는 방법으로는 overlap matrix S의 가장 작은 eigen value의 값을 측정하는 방법이 있다. 더 작은 eigen value를 가질수록 더 큰 linear dependence를 가진다. eigen value가 10<sup>-8</sup> 이하일 경우 심각한 numerical instability를 야기하게 되는데, 경우에 따라 10<sup>-7</sup>, 10<sup>-6</sup> 인 경우도 신뢰할 수 없는 결과를 만들기도 한다.  
이 문제를 해결하기 위한 방법으로는 단순히 한 개 이상의 the most diffuse basis function을 생략하거나, 작은 eigen value를 야기하는 basis function의 linear combination을 생략하는 방법이 있다.
Gaussian 같은 프로그램들은 이것을 자동으로 해 주기도 한다.  CRYSTAL code의 경우 [3]을 참고하자.

[2]  
linear dependence in basis-set calculation 문제는 3차원 extended system의 intrinsic한 문제인데, 적은 차원에서는 그렇게 큰 심각한 문제는 아니다. plane waves로 Fermi-level 근처의 orbital이 잘 기술되는 경우의 3차원 extended system은 tight한 atomic orbital/plane-wave (AO-PW) basis set을 쓰면 이러한 문제를 가장 효과적으로 피할 수 있다.

[3]  
CRYSTAL code에서는 overlap matrix를 diagonalize 한 후, 원래 N 개의 positive eigenvalue를 사이크를 줄이는 쪽으로 재정렬함으로써 이 문제를 해결하고자 한다. 즉, cutoff (STOL) 이하의 값을 가지는 m 개의 eigen value를 제거하여 (N-m) rectangular matrix를 만든다. 만약 제거된 eigenvalue가 정확히 0 이었다면, (N-m) function set이 생기는 것과 같기 때문에, 정확도를 잃어버리진 않는다. 하지만 일반적으로 finite eigenvalue를 제거하게 되면 total energy에 error가 수반하게 된다. 이 error은 impirically quantified 되어야 한다.
replicated parallel and data distributed parallel (MPP) version에 implementaion될 예정인데, projector method라 불린다. 이 방법은 linear dependence를 제거해주지만, pre-conditioning을 잃어버리므로 성능에 심각한 저하를 수반한다.  
OVERLAPTOL 이라는 키워드로 두 개의 parameter가 필요하다.  
1. 소수값의 cutoff 값  
2. 정수값의 다변성 값 (1~3). 3이 가장 다변성이 크다.
integral tolerance (TOLINTEG) 가 충분히 높아 overlap matrix의 negative eigenvalue가 모두 제거되도록 해야한다. TOLINTEG를 증가시키려면 real space lattice vector array의 사이즈 (LAVEC) 도 증가시켜야 한다. 또한 stable convergence를 위해 k point sampling (SHRINK) 또한 늘려야 할 수도 있다.  


---
reference  
[1] [Exploration of Basis Set Issues for Calculation of Intermolecular Interactions, J. Phys. Chem. A 2006, 110, 9529](https://pubs.acs.org/doi/pdf/10.1021/jp0680239)  
[2] [Linear dependence in basis‐set calculations for extended systems](https://onlinelibrary.wiley.com/doi/epdf/10.1002/qua.560430602)  
[3] [Removing pseudo-linear dependence in Gaussian basis set calculations on crystalline systems with the CRYSTAL code](https://www.archer.ac.uk/community/eCSE/eCSE04-16/eCSE04-16_Technical_Report.pdf)  

