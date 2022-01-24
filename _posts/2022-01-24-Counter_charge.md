---
title: "Counter charge"
date: 2022-01-24T08:08:50-04:00
category: Electrochemistry
tags:
  - DFT
---


![image-center]({{ 'images/GaN_counter_charge.PNG' | absolute_url }}){: .align-center}  


periodic DFT 계산에서는 extra charge를 넣고 빼기 위해서 uniform counter charge를 가하게 되는데, 이것은 electrode와 electrolyte의 분간이 없으므로 현실과 동떨어지게 된다. 실제로는 electrolyte내의 counter ion의 accumulation이 일어나기 때문에, PB 모델을 이용하면 이 electrolyte의 counter ion이 이 extra charge를 상쇄시킨다.  

GaN 를 예로 들어보자. (a) 위쪽에는 Ga vacancy, 아래쪽에는 N vacancy가 있다. vacuum 계산(b, blue)에서는 slab model의 반대 방향의 vacuum level 서로 다른것을 보아 surface dipole이 있음을 확인할 수있다.  
PB 모델을 적용(b, Red)하면 counter ion에 의해 dipole이 상쇄되어 vacuum level이 일정해진다. 따라서 PB모델이 이미 dipole을 상쇄시키므로, dipole correction을 해도 (b, black) 거의 같은 결과를 보임을 알 수 있다.  


