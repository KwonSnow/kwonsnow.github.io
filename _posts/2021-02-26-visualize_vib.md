---
title: "Visualization of vibration mode"
date: 2021-02-26T08:08:50-04:00
category: DFT
tags:
  - VASP
  - vibration
  - Jmol
---

VASP의 vibration 모드를 Jmol을 이용해서 visualization 해보자.
OUTCAR에 이미 cartesian coordinate으로 변환된 Eigenvector와 해당 eigenvalue가 완성되어 있으므로, 앞에 원소만 표기해줘서 xyz 파일로 만들면 Jmol에서 시각화 할 수 있다.

[http://home.ustc.edu.cn/~lipai/scripts/vasp_scripts/bash_get_vibration.html](http://home.ustc.edu.cn/~lipai/scripts/vasp_scripts/bash_get_vibration.html)
먼저 con2xyz.pl의 Vasp 모듈을 이용하기 위해서 vtst script의 path를 환경변수로 추가해주자.
PATH=~/vtst_scripts:$PATH
POSCAR와 OUTCAR를 준비하고, get_vibration.sh를 실행시켜주자.
vib 폴더에 각각의 모드를 Jmol로 실행시켜주면 됨.


[https://github.com/QijingZheng/VaspVib2XSF](https://github.com/QijingZheng/VaspVib2XSF)
