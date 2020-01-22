---
title: "Point Group"
date: 2020-01-22T08:08:50-04:00
category: Inorganic Chemistry
tags:
  - Inorganic Chemistry
  - Symmetry
  - Point group
  - Matrices
---

# Point Groups
한 분자의 __여러 symmetry operations을 하나의 set로 모아놓은 것__ 을 그 분자의 point group이라고 한다.  
Point group을 결정하는 것은 아래의 diagram을 따라가기만 하면 된다. 다만 첫번째 step인 분자가 low (or high) symmetry를 가지고 있느냐만 집고 넘어가보자.  
low symmetry는 symmetry가 없거나(E), 하나의 mirror plane (C<sub>s</sub>)만 있거나, 하나의 inversion center (C<sub>i</sub>) 만 있을 경우에 해당된다.  
high symmetry는 여러가지가 있는데,  
C<sub>∞υ</sub>:  linear하고, inversion center가 없는 경우, <sub>HCl</sub>  
D<sub>∞h</sub>: linear하고 perpendicular C2 axis & perpendicular mirror plane, inversion center가 존재하는 경우, CO<sub>2</sub>  
T<sub>d</sub>: Tetrahedral, CH<sub>4</sub>  
O<sub>h</sub>: Ohtahedral, SF<sub>6</sub>  
I<sub>h</sub>: Icosahedral, B<sub>12</sub>H<sub>12</sub><sup>2-</sup>  

[symmetry decision tree](https://www2.chemistry.msu.edu/faculty/reusch/VirtTxtJml/symmetry/symmtry.htm)  
![Alt Text](https://www2.chemistry.msu.edu/faculty/reusch/VirtTxtJml/symmetry/symmchrt.gif)

# Matrix representation
각각의 symmetry operation은 행렬의 형태로 표현할 수 있는데, 이를 transformation matrix라고 한다.  
[New coordinates] = [transformation matrix] [old coordinates]

H<sub>2</sub>O (C<sub>2υ</sub>)를 예로 들어보자. 물분자는 세개의 atom이 있고, 따라서 각 atom마다 xyz coordinate가 있다. 물분자에는 네 개의 symmetry operations이 있다. 이중에서 어떤 operation을 몇 번을 하든 원래의 물분자와 indistinguishable 하다.  

![image-center]({{ 'images/C2v_operations_1.PNG' | absolute_url }}){: .align-center}

__Character__ 란 위의 예시처럼 diagonal에 있는 요소들의 합을 말한다. 이런 character들의 집합을 __representation__ 이라고 하는데,


![image-center]({{ 'images/C2v_operations_2.PNG' | absolute_url }}){: .align-center}



#




# Symmetry
분자의 symmetry를 분석함으로써 __optical activity__ 를 예측할 수 있고, __infrared-active stretching vibration__ 의 수와 type을 결정할 수 있으며, 본딩에 사용된 __orbital의 type__ 을 기술하기도 하고, __electronic spectra__ 를 해석할 수 있다.  

Symmetry __element__ : mirror planes, axies of rotation, and inversion centers  
Symmetry __operation__ : reflection, rotation, inversion  


## Identity operation (E)
아무런 변화를 일으키지 않지만, 수학적 기술을 위해 쓰인다. CHFClBr처럼 다른 아무런 symmetry가 적용되지 않을 때 할당될 수 있다.

## Rotation operation (C<sub>n</sub>), proper rotation
rotation axis를 기준으로 360°/n 만큼 회전시키는 operation. 
해당 operation을 몇번 했는지에 따라 C<sub>n</sub><sup>2</sup>, C<sub>n</sub><sup>3</sup> 으로 표기한다. 당연히, C<sub>n</sub><sup>n</sup> = E  
하나의 분자가 여러개의 rotation axis를 가질 수 있는데, 이러한 경우 가장 높은 order를 가지는 rotation axis를 the highest order rotation axis or __principal axis__ 라고 한다. Cartesian coordinates를 할당하기 위해서 주로 principal axis를 z 축으로 선택하고, z축에 수직한 나머지 rotation axis는 prime(′)으로 표기한다. 이 중에서 rotation axis가 여러개의 원자들을 통과하면 single prime, C<sub>n</sub>′으로 표기하고, outer atoms 사이를 통과하면 double prime,  C<sub>n</sub>″으로 표기한다.  

## Reflection operation (σ)
Mirror plane이 principal axis와 __수직이면__ σ<sub>h</sub> __(horizontal)__ 로 표기하고, mirror plane이 이를 포함하면 σ<sub>υ</sub> or σ<sub>d</sub>로 표기한다.

## Inversion operation (i)
주의: tetrahedra, triangle, pentagon 등은 inversion symmetry가 없다.

## Rotation-reflection operation (S<sub>n</sub>), improper rotation
rotation axis를 중심으로 360°/n 만큼 회전시킨 후 이 axis에 수직하는 plane을 기준으로 reflection시키는 operation.  
예) methane (CH<sub>4</sub>): S<sub>4</sub>, Ethane (staggered) (C<sub>2</sub>H<sub>4</sub>): S<sub>6</sub>  
S<sub>n</sub>을 두번하면 C<sub>n/2</sub> operation을 한번 한 것과 같다.  
S<sub>2</sub>는 i와 같고, S<sub>1</sub>은 σ와 같은데, 이러한 경우 i와 σ로 표기하는 것을 선호한다.  
