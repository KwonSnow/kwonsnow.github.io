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
C<sub>∞υ</sub>:  linear하고, inversion center가 없는 경우, HCl  
D<sub>∞h</sub>: linear하고 perpendicular C<sub>2</sub> axis, perpendicular mirror plane, inversion center가 존재하는 경우, CO<sub>2</sub>  
T<sub>d</sub>: Tetrahedral, CH<sub>4</sub>  
O<sub>h</sub>: Ohtahedral, SF<sub>6</sub>  
I<sub>h</sub>: Icosahedral, B<sub>12</sub>H<sub>12</sub><sup>2-</sup>  

[symmetry decision tree](https://www2.chemistry.msu.edu/faculty/reusch/VirtTxtJml/symmetry/symmtry.htm)  
![Alt Text](https://www2.chemistry.msu.edu/faculty/reusch/VirtTxtJml/symmetry/symmchrt.gif)

# Matrix representation
각각의 symmetry operation은 행렬의 형태로 표현할 수 있는데, 이를 transformation matrix라고 한다.  
<p class="text-center"> [New coordinates] = [transformation matrix] [old coordinates] </p>


H<sub>2</sub>O (C<sub>2υ</sub>)를 예로 들어보자. 물분자는 세개의 atom이 있고, 따라서 각 atom마다 xyz coordinate가 있다. 물분자에는 네 개의 symmetry operations이 있다. 이중에서 어떤 operation을 몇 번을 하든 원래의 물분자와 indistinguishable 하다.  

![image-center]({{ 'images/C2v_operations_1.PNG' | absolute_url }}){: .align-center}

__Character__ 란 위의 예시처럼 diagonal에 있는 요소들의 합을 말한다. 이런 character들의 집합을 __reducible representation (Γ)__ 이라고 한다. 각 symmetry operation의 matrix representaion은 diagonal element를 제외하면 모두 0 이기 때문에 x, y, z coordinates가 독립적으로 적용될 수 있으므로, 각각의 x, y, z contribution으로 deconvolution할 수 있는데 이렇게 deconvolute한 row를 __irreducible representation__ 이라고 한다.  


![image-center]({{ 'images/C2v_operations_2.PNG' | absolute_url }}){: .align-center}



