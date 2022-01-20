---
title: "Electrode-Electrolyte Interface"
date: 2022-01-20T08:08:50-04:00
category: Electrochemistry
tags:
  - DFT
---

[Joint density functional theory of the electrode-electrolyte interface: Application to fixed electrode
potentials, interfacial capacitances, and potentials of zero charge](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.86.075140)  

실제 전기화학적 시스템에서 이온농도가 0.1 M이면 ionic screening은 30 Å 정도. 이를 explicit solvent로 구현하려면 cost가 너무 크다. 또한 phase space를 잘 sampling 하기 위해서는 굉장히 긴 시뮬레이션을 필요로 한다. 무엇보다, 실제 reaction은 Potential of zero charge (PZC)가 아닌 환경에서 일어나는데, periodic supercell calculation에서 charge를 넣고 빼려면 이를 보상해 줄 uniform charged background를 넣게 되는데, 이것은 liquid region과 solid region 모두에 적용되므로 이러한 distribution은 실제 전기화학적 환경을 정확하게 기술하지는 않는다.  
다른 방법으로는 Poisson-Boltzmann (PB) model을 이용한
하지만 PB 모델도 정확한 theory를 바탕으로 하지는 않는다. 즉, non-locality and non-linearity of dieletric response of water 그리고 surface tension associated with formation of the liquid-solid interface를 고려하지 않는다. 예를들어, 3 Å double layer 두께정도면 0.1 V drop이 일어나는데, (즉 field가 300 MV/m 정도) 이것은 bulk water의 dieletric constant의 1/3정도에 해당하므로, 실제 liquid-solid interface에서는 non-linear dielectric saturation effect가 존재한다는 것을 나타낸다.  

