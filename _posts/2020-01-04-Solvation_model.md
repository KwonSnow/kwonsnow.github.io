---
title: "Implicit solvation model"
date: 2020-01-04T08:08:50-04:00
category: DFT
tags:
  - Implicit solvation
---

Implicit solvation을 이용하면 효율적이로 solvent 거동에 대한 적당한 묘사가 가능하지만 solute 주변에 있는 solvation density에 대한 local fluctuations에 대한 고려는 하지 못한다. 이러한 density fluctuation은 solute 주변의 solvent ordering에 의해 발생하는데, 특히 solvent가 water일때 특히 중요하다.

Implicit solvents (or continuum solvents)는 implicit solvent molecules를 homogenesouly polarizable medium으로 대체가능 하다고 가정한다. Explicit solvent가 없기 때문에 solvent의 coordinate가 주어지지 않는다.
Continuum model은 thermally averaged and isotropic solvent만 고려하기 때문에, 적은 수의 parameter로도 적당한 정확도로 solvent를 표현할 수 있다.
Dieletric constant는 주로 solvent의 polarizability 정도를 정의하는데 사용된다.
일반적으로 말하면, Implicit solvent에서는 대상이 되는 solute를 타일로 된 cavity로 감싸게 되고, 이 cavity는 solvent를 묘사하는 homogeneously polarizable continuum 에 embedded 되어있다.

![image-center]({{ 'images/Cavity.PNG' | absolute_url }}){: .align-center}

solute의 charge distribution은 cavity의 surface에서 continuous dielectric field와 만나게 되고, 주변의 medium을 polarize 시킨다. 이 polarized 된 medium은 또다시 solute를 polarization 시키게 된다. 이러한 과정에서 polarization의 변화에 대한 반응, 즉 reaction potential이 정의되는데, 이러한 재귀적인 (recursive) reaction potential은 self-consistency를 만족하도록 iteration 된다.
Continuum models은 양자화학 뿐만 아니라 force field method에서도 널리 쓰인다.
양자화학에서 implicit solvent는 solute의 Hamiltonian에 일종의 perturbation으로서 나타내어진다. 수학적으로는 다음과 같이 나타내어지는데,  
<p><span class="math inline">\(\hat{H}^{\text {total }}\left(r_{\mathrm{m}}\right)=\hat{H}^{\text {molecule }}\left(r_{\mathrm{m}}\right)+\hat{V}^{\text {molecule +\ solvent <span class="math inline">\(\left(r_{\mathrm{m}}\right)\) }}+\)</span> solvent <span class="math inline">\(\left(r_{\mathrm{m}}\right)\)</span></p>  

solvent의 implicit nature는 solute molecule의 coordinate (r<sub>m</sub>) 에만 의존하는 것을 볼 수 있다. 두 번째 항인 V는 interaction operater (Q)들로 이루어져 있다. Q는 무한히 멀리 떨어진 독립된 시스템(gaseous)에서 continuum solution 안으로 상황이 바뀌었을 때의 반응을 계산한다. 따라서 이러한 과정은 gas phase에서 Hamiltonian에 perturbation을 줬을 때의 상황과 유사하다.  

<p><span class="math inline">\(Q(m)=Q_{\text {cavity }}+Q_{\text {electrostatic }}+Q_{\text {dispersion }}+Q_{\text {repulsion }}\)</span> <span class="math inline">\(G=G_{\text {cavity }}+G_{\text {electrostatic }}+G_{\text {dispersion }}+G_{\text {repulsion }}+G_{\text {thermal motion }}\)</span></p>  

일반적으로 continuum solvation model에서는 위와 같이 네 개의 Q를 고려한다. 각각은 분명한 물리적 의미를 담고 있다.  
첫째항은 cavity creation에 대한 것으로서, solute를 담는 cavity를 적당한 사이즈와 모양으로 solvent내에 만들 때 쓰이는 에너지이다. 물리적으로는, solvent 내에 공간을 만들 때 solvent structure에 압박을 가하는 에너지 비용으로 설명할 수 있다. (formation of the solvent-solute interface)   
둘째항은 solute와 solvent의 polarization을 다루는 electrostatic energy (reorientational and polarization screening in the solvent)  
세번째항은 quantum mechanical exchange repulsion에 대한 근사값으로서 implicit solvent에서 이 항은 high level theoretical calculation에 대해서만 근사가 가능하다. (short-range electron overlap effects)  
네번째항은 quantum mechanical dispersion energy로서 solvent의 charge distribution을 평균하는 방식으로 근사할 수 있다. (long-range electron correlations)  


여러가지 방법들이 개발되었는데,
Poisson-Boltzmann equation에 기반한 Polarizable continuum model (PCM)과 generalized Born equation에 기반한 Solvation Model (SMx)가 있다. SMD (based on Density) model은 PCM과 비슷하지만 cavity를 만들 때 특정한 parametrised radii를 사용한다.



출처
[Solvent model](https://en.wikipedia.org/wiki/Solvent_model)  
[Polarizable continuum model](https://en.wikipedia.org/wiki/Polarizable_continuum_model)

