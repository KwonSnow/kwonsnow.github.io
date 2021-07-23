---
title: "Oxidation states"
date: 2021-05-15T08:08:50-04:00
category: DFT
tags:
  - Oxidation states
---

### [Electron Counting in Solids: Oxidation States, Partial Charges, and Ionicity](https://pubs.acs.org/doi/10.1021/acs.jpclett.7b00809)  
Crystal 내의 electron은 multicentered wave functions (Bloch waves)에 의해 기술되므로 charge assigning은 어렵다.  
다만 실험과 비교해 볼 수 있는 것으로는,  
  * Lattice energy  
  * Response to electromagnetic fields
  * Core-level photoemission spectrscopy
  * Electron spin resonance (ESR)
  * nuclear magnetic resonance (NMR)  
등이 있다.  

 
### [Oxidation states and ionicity](https://www.nature.com/articles/s41563-018-0165-7)  
Oxidation states 는 구조를 예측하기 위한 VSEPR모델이나 spectroscopic response를 설명하기 위한 ligand and crystal field theory를 뒷받침하는 툴이다. Formal oxidation state를 할당함으로써 우리는 물질의 중요한 특성을 이해할 수 있지만, 이것이 effective charge는 아니다. 예를 들어 KMnO4에서 Mn(+7)은 d<sup>0</sup> configuration 이지만 이것이 실험적으로 측정하거나 이론적으로 계산했을때 3d orbital의 charge density가 0이라는 것을 의미하지는 않는다. 다만, 모든 3d electron이 직접적으로 Oxygen과 bonding을 이루고 있다는 것을 가리킨다.  
Chemical composition을 이용하여 oxidation state를 할당하는 방법외에도, bond나 angle같은 local structure를 이용할 수 있다. [PYMATGEN](https://pymatgen.org/pymatgen.analysis.bond_valence.html)을 통해 valence bond analysis를 수행할 수 있다.  
기본적으로 atomic charge는 양자역학적 observable이 아니다. DFT에서의 one-electron wavefunction은 대부분의 양자화학에서 쓰이지만, wavefunction은 실제 공간내에 delocalized 되어있다. 이를 partitioning 하는 방법에는,  
  * <b>Geometric partitioning</b> (radius or polyhedron)
  * <b>Bader</b>: Contour of zero density gradient
  * <b>Wannier function</b>: Fourier transforms of Bloch wavefunctions onto discrete centres
  * <b>Mulliken, Löwdin</b>: A linear combination of atomic orbitals
  * Polarity of bond: <b>Christoffersen</b> (Molecular orbitals),  <b>Hirshfeld</b>(Charge density)
  * <b>Electron localization function (ELF)</b>
  * <b>Modern theory of polarization</b>: The link between polarizability and experimentally observable quantities is far clearer than that between the atomic charges and experiment. 

Atomic charge에 대한 정보를 얻기 위한 alternative techniques으로는  
  * XPS, XANES, Neutron spectroscopy, spin resonance techniques, spectroscopic or magnetic measurements  


### [Rigorous Definition of Oxidation States of Ions in Solids](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.108.166403)  
