---
title: "Photoelectrocatalytic Water Splitting"
date: 2021-10-13T08:08:50-04:00
category: Green chemistry
tags:
  - photocatalysis
  - electrocatalysis
  - water splitting
---

광합성은 태양에너지와 물, 이산화탄소를 이용하여 바이오매스와 산소를 얻는 과정이다. 대부분 사람들이 잊어버리는 것중 하나는 이 광합성은 사실 2-step process라는 것. 식물은 빛을 이용하여 물을 분해하여 산소와 수소(NADPH)를 생성하지만, 수소와 CO2를 이용하여 바이오매스를 생산하는 과정은 빛을 필요로 하지 않는다.
물분해는 열역학적으로 uphill. 하지만 우리가 이미 수소를 가지고 있다면, 이산화탄소를 환원해서 얻는 거의 모든 종류의 carbon product생산하는 것은 열역학적으로 thermoneutral이거나 downhill.
광합성은 사실 에너지를 저장하기 위한 최적의 시스템은 아니다. 왜냐하면 생물은 에너지를 저장하기보다 에너지를 쓰는데 더 집중하기 때문. 실제 광합성을 통한 에너지 저장 효율은 10.5 % 정도로, 일반적인 실리콘태양전지(> 25 %)의 효율보다도  낮다.

실리콘 태양전지로 생산한 에너지를 저장하는데도 어려움을 겪고 있는데, 태양전지 효율이 점점더 좋아지면 어떻게 될까.
(https://www.nrel.gov/pv/cell-efficiency.html)

수소를 생산하기만 하면 쓸데가 너무 많다. (https://doi.org/10.1016/j.biortech.2020.124175)
fuel cell, 철강생산, biomass 생산, ammonia 생산, methanol 생산, oil refining, 등등

Daniel Nocera: https://register.gotowebinar.com/recording/viewRecording/2339719380513223696/7369764076308052239/skwon@caltech.edu?registrantKey=8901663049494344459&type=ATTENDEEEMAILRECORDINGLINK
Hydrogenase(H2ase): H2 -> H+ and e- -> synthetic biology

Haber process: 
N2(g) + 1.5 CH4 + 1.5 O2 -> 2NH3(aq) + 1.5CO2(g)
unreacted hydrogen, nitrogen, CO2, ammonia -> cooled and compressed -> liquified ammonia is seperated


[A current perspective for photocatalysis towards the hydrogen production from biomass-derived organic substances and water](https://doi.org/10.1016/j.ijhydene.2019.08.121)  
H2 energy density 122 kJ/g 으로 gasoline (40 kJ/g)보다 4배 가량 높다.  

Solar-to-hydrogen (STH) 은 아직 낮다. 원인으로는
* rapid photo-generated electron/hole pair recombination: charge carrier lifetime & mobility
* fast-backward reaction
* unfavorable thermodynamic potential for water splitting
* ineffective harvesting visible photons for water splitting: adsorption coefficient
* instability against photo-corrosion

열역학적 에너지 손실 (0.3~0.4 eV)과 overpotential (0.4 ~ 0.6 eV)을 고려해 봤을 때, 반도체의 밴드갭은 1.8 eV 보다는 커야하지만 효율적인 visible light의 흡수를 위해선 3.2 eV 보다는 작아야 한다.  

dopant를 carbon, nitrogen, halogen과 같은 non-metal을 쓰게 되면 주로 VB 위에 electron-doner level을 생성하게 되고, 전이금속을 도핑하면 주로 CB아래에 electron-acceptor level을 생성하게 된다.
따라서 doping을 통해 밴드갭을 줄일 수도 있지만, doping을 많이 하면 recombination center로 작용할 수 있다. 

Grain boundary 또한 recombination center로 작용할 수 있기 때문에, calcination을 통해 high crystallinity를 유지함으로써 효율을 증가시킬 수 있다.  

Photocatalyst의 morphology도 중요한데, 가령 nano rod, nano wire 와 같은 1D 구조를 생성해서, e-과 h+의 migration을 moving direction을 제한함으로써 촉진시킬 수 있다.  

반도체를 electrolyte에 담그게 되면, 이온들이 표면에 위치함으로써 Helmhotz layer를 구성하게 되는데, 이것은 상온에서 -0.59 mV/pH 만큼의 potential drop (V<sub>H</sub>)을 야기시킨다. 따라서 반도체 내에서 band bending이 일어나게되며 charge carrier의 이동방향을 제한하거나 photo-induced e- and h+의 흐름에 영향을 주어 e-/h+ sepration effciency를 향상시킨다.


[Photoelectrochemical devices for solar water splitting – materials and challenges](https://doi.org/10.1039/C6CS00306K)  

지구에 도달하는 태양에너지는 약 100,000 TW이고, 이 중에서 지표면에 도달하는 에너지는 약 36,000 TW이다. 이 중에서 1 %의 에너지를 10%의 효율을 가진 photoelectrochemical (PEC) cell로 에너지 전환을 할 수 있다면 (36 TW), 2050년의 세계연간에너지소모를 충당할 수 있을것으로 예측된다. photovoltaic (PV) cell과 electrolyser를 결합하는 방식으로 solar-to-hydrgen (STH) efficiency는 이미 30%에 도달했기 때문에, 최근에는 안정적이고 저렴한 물분해 PEC cell을 만드는 것에 많은 집중이 이루어지고 있다.  
PV-electrolyser의 경우 electrolyser로 H2를 생성하기 위한 최저 포텐셜(3.0 V)에 도달하기 위하여 여러 개의 cell을 써야하므로 비용이 올라간다. PEC의 경우에는 보다 간단하고 적은 부품을 사용할 수 있어서 공간과 비용을 절약할 수 있다. 따라서 PV-electrolyser 시스템은 최소비용이 $8/kg이지만, light harvester와 물분해 광촉매를 하나의 시스템으로 통합하면 (PEC cell) 비용을 약 $ 3/kg으로 줄일 수 있는데, 이는 steam reforming으로 생성한 H2와 경쟁하기 위해 DOE가 설정한 목표비용($2~4/kg)에 적합하다.  









[Band Bending in Semiconductors: Chemical and Physical Consequences at Surfaces and Interfaces](https://pubs.acs.org/doi/pdf/10.1021/cr3000626)  
[Band Bending](http://tuttle.merc.iastate.edu/ee436/topics/fet/band_bending.pdf)  
OER reviews  
HER reeview (2D?)  

