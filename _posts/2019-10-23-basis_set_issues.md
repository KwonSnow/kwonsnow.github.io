---
title: "Basis Set Issues"
date: 2019-10-23T05:08:50-04:00
category: DFT
tags:
  - DFT
  - Basis set
---

# Linear dependence
큰 basis set, 특히 diffuse function (or  those with several closely spaced sets of off-centered functions)을 갖는 basis set으로 계산을 수행할 경우 linear dependency에 의한 numerical instabilities를 겪게 된다.
이러한 문제는 periodic systems나 large set of bonding functions를 사용하는 경우에 발생한다.  

1. HF equations에서 construction of an orthgonalizing transformation matrix S<sup>-1/2</sup> (S: overlap matrix) 할 때 발생한다. near linear dependence basis set의 경우 S matrix의 eigenvalues가 너무 작아서 S<sup>-1/2</sup>을 구성할 때 nearly zero로 나눠야 하기 때문에 singularity가 발생하게 되고 따라서 precision에 영향을 미치게 된다.




---
reference  
[1] [Exploration of Basis Set Issues for Calculation of Intermolecular Interactions, J. Phys. Chem. A 2006, 110, 9529](https://pubs.acs.org/doi/pdf/10.1021/jp0680239)
