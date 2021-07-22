---
title: "Continuum Transport Model"
date: 2021-02-16T08:08:50-04:00
category: Electrochemistry
tags:
  - CO2RR
  - Ag(110)
  - Continuum transport model
  - Microkinetics
---

[PNAS 2017, 114, E8812](https://doi.org/10.1073/pnas.1713164114)

Ag와 Au는 CO2 to CO conversion에서 가장 좋은 activity와 selectivity(CO vs H2)를 가지고 있는데, Ag가 훨씬 싸기 때문에 CO 대량생산에 유리.
왜 Ag(110)인지에 대한 언급은 없음.


# Free energy calculations
### VASP  
3×4×3L slab model for Ag(110): 이정도 사이즈의 cell이면 periodic image에 의한 adsorbate간의 상호작용을 최소화 할수 있다고 언급.  
1. Reactant geometry는 48 H2O를 이용하여 준비 (minimization?)  
2. Using __RPBE__ functional, 5 ps AIMD w/ 72 H2O __to get water configuration__  
3. Using __M06-L__ functional, minimization followed by TS searching w/ 36 H2O + VASPsol + linearized Poisson-Boltzmann model __to get electrochemical potential__ from fermi energy.  
Frequency는 adsorbate만 대상으로 계산.

이 모델에서는 atomic configuration이 변할 때 applied potential을 유지하기 위해서 electron의 재배치가 일어나기 때문에 __electron transfer가 rate limiting가 아니라고 가정__ 한다.  
Energy profile은 -0.0132 ~ -1.132 V vs RHE w/ 0.1 V interval 로 구했다고 함.
TS searching은 Dimer method 이용 (VTST) < 0.01 eV/Å.

# Continuum transport model
### COMSOL 이용해서 CO2, OH-의 concentration (activity) 구함.
Anion (HCO<sub>3</sub><sup>-</sup>, CO<sub>3</sub><sup>2-</sup>, OH<sup>-</sup>)의 diffusion coefficient는 25도씨 실험값 이용하고 (일반적으로 electrolyte보다 1 order 낮다), cation은 two order 낮다고 가정.  
CO, H2의 activity는 각각 CO, H2의 fractional current density로부터 구함.
표면 근처 CO2의 local concentration와 pH는 Continuum model에 정의되어야 한다. 따라서 initial concentration은 bulk값을 이용하고, microkinetics에서 얻은 partial current density 값을 continuum model에 다시 대입하는 식으로, concentration과 current density가 수렴할 때 까지 반복한다.  

# Microkinetics
### MATLAB  
CO<sub>2</sub>(g) -> CO<sub>2</sub>* -> COOH* -> CO*  
Tafel reaction이 Heyrovsky보다 0.4 eV 낮아서, HER은 Volmer-Heyrovsky로 가정: 이게 옳은 가정인가? 데이터가 있나?  
reactant와 product의 adsorption/desorption은 electrocatalytic reaction보다 빠르다고 가정하고 quasi-equilibrium을 이룬다고 가정.  

# Iterative solver
c<sub>CO2</sub>은 Henry's constant로 구함. c<sub>CO2</sub> = K<sub>0</sub>*f<sub>CO2</sub>  

