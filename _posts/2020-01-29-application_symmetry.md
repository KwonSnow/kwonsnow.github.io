---
title: "Applications of Symmetry"
date: 2020-01-29T08:08:50-04:00
category: Inorganic Chemistry
tags:
  - Inorganic Chemistry
  - optical activity
  - IR activity
  - Raman activity
---



# Molecular Vibrations
Vibration은 분자내 개개 원자의 motion에 관한 것이기 때문에 각 원자마다 x,y,z coordinate을 부여해야한다.
따라서 N개의 원자가 포함된 분자는 3N개의 degrees of freedom을 가진다. Degree of freedom의 수는 보존되어야 하므로,  

<p class="text-center"> Total Degree of freedom = Translational mode + Rotational mode + vibrational mode </p>

![image-center]({{ 'images/app_sym_1.PNG' | absolute_url }}){: .align-center}

H<sub>2</sub>(C<sub>2υ</sub>)는 9 개의 degree of freedom을 가지고 있다. C<sub>2υ</sub>의 symmetry operation은 4개가 있는데, 
9개의 motion에 대해 translation, rotation, and vibration을 할당하기 위해서는 transformation matrices의 character를 판별한 후 t

water의 경우 9x9 matrix여야 하나의 transformation matrix 를 표현할 수 있는데, C<sub>2υ</sub>는 아래의 symmetry operation은 4개가 있다.
9x9 matrix에서 C<sub>2υ</sub>나 σ<sub>υ(xz)</sub>처럼 H<sub>a</sub>와 H<sub>b</sub>의 위치가 서로 교환되는 경우에는 다음과 같이  
결국 이러한 경우에는 diagonal에서 벗어나므로 character를 결정할때는 기여가 0이 된다.
반면 E나 σ′<sub>υ(yz)</sub>처럼 위치에 변함이 없는 경우에는 모두 diagonal에 위치하여 character를 결정할 때 기여한다.

![image-center]({{ 'images/app_sym_2.PNG' | absolute_url }}){: .align-center}

따라서 reducible representation (Γ)는 9 -1 3 1 이 된다. 이것을 각각의 irreducible representation의 요소로 분리하기 위해서 다음과 같은 규칙을 사용한다.

![image-center]({{ 'images/app_sym_3.PNG' | absolute_url }}){: .align-center}
 
따라서 총 9개의 irreducible representaion이 있다. ( 3A<sub>1</sub> + A<sub>2</sub> + 3B<sub>1</sub> + 2B<sub>2</sub> )





각각의 irreduvible representation은 하나의 molecular motion으로 간주하자.
전체 irreducible representation의 수에서 translational + rotational degree of freedom을 빼면 남은 irreducible representation은 각각의 normal mode를 가진 vibrational mode로 생각할 수 있다.




각각의 irreducible representation에 symmetry label을 붙이는데,
