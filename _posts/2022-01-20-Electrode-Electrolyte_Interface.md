---
title: "Electrode-Electrolyte Interface"
date: 2022-01-20T08:08:50-04:00
category: Electrochemistry
tags:
  - DFT
---


실제 전기화학적 시스템에서 이온농도가 0.1 M이면 ionic screening은 30 Å 정도. 이를 explicit solvent로 구현하려면 cost가 너무 크다. 또한 phase space를 잘 sampling 하기 위해서는 굉장히 긴 시뮬레이션을 필요로 한다. 무엇보다, 실제 reaction은 Potential of zero charge (PZC)가 아닌 환경에서 일어나는데, periodic supercell calculation에서 charge를 넣고 빼려면 이를 보상해 줄 uniform charged background를 넣게 되는데, 이것은 liquid region과 solid region 모두에 적용되므로 이러한 distribution은 실제 전기화학적 환경을 정확하게 기술하지는 않는다.  



