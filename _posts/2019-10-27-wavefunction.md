---
title: "Wavefunction"
date: 2019-10-27T08:08:50-04:00
category: Quantum Mechanics
tags:
  - Quantum Mechanics
  - Wavefunction
---

*  [Visualizing orbitals](https://towardsdatascience.com/quantum-physics-visualization-with-python-35df8b365ff)
*  [Animating the Schrodinger Equation](https://jakevdp.github.io/blog/2012/09/05/quantum-python/)
*  [Python package for calculating wavefunctions for 1D and 2D potentials](https://github.com/jrjohansson/wavefunction)
*  [1D density functional theory code in Python](https://github.com/tamuhey/python_1d_dft)
*  [DFT/LDA Solver for isolated Helium atom](https://https://github.com/sarah-allec/dftsolver)


# H2O
PARCHG 파일이 필요. VESTA 인식 가능, 다만 확장자 변경해야함.  
PARCHG: partial charge densities (Wavefunction 은 아니다)

1. WAVECAR 얻기, OUTCAR에서 Band 몇개 인지 확인하기.

2. PARCHG 얻기.

ISTART = 1  
LPARD = True  
IBAND = 1 2 3 4 5 6 7 8   # band number  
KPUSE = 1   # 1 k-point is needed  
LSEPB = True  #  whether the charge density is calculated for every band, PARCHG.nb.*  
LSEPK = True  #  pecifies whether the charge density of every k-point, PARCHG.*.nk  

Gamma point에서만 계산 했기 때문에, KPUSE = 1

PARCHG.band#.kpoint# 로 출력됨.

계산 후

PARCHG.0001.0001 -> PARCHG1  
PARCHG.0002.0001 -> PARCHG2  
PARCHG.0003.0001 -> PARCHG3  
PARCHG.0004.0001 -> PARCHG4  
PARCHG.0005.0001 -> PARCHG5  
PARCHG.0006.0001 -> PARCHG6  
PARCHG.0007.0001 -> PARCHG7  
PARCHG.0008.0001 -> PARCHG8  

로 변경 후 VESTA에서 plot.



