---
title: "Molecular orbitals"
date: 2020-01-29T08:08:50-04:00
category: Inorganic Chemistry
tags:
  - Inorganic Chemistry
  - Molecular orbitals
  - Bond order
  - Oribtal mixing
  - Magnetism
  - Photoelectron spectroscopy
---

# Molecular orbitals from atomic orbitals
분자의 Schrödinger equation을 풀면 대략적인 solution으로서 linear combination of the atomic orbitals (LCAO)를 구성할 수 있는데, LCAO란 원자의 wavefunction의 합 또는 차이다. H<sub>2</sub>를 예로 들면,

<p><span class="math inline">\(\Psi=c_{a} \psi_{a}+c_{b} \psi_{b}\)</span></p>

 
여기서 𝚿는 __molecular__ wave function이고, 𝝍<sub>a</sub>, 𝝍<sub>b</sub>는 __atomic__ wave function이다. c<sub>a</sub>, c<sub>b</sub>는 조정이 가능한 계수로 양수 또는 음수가 될 수 있고, 두 값이 같거나 다를 수도 있다.
두 원자간의 거리가 가까워질수록 orbital이 서로 overlap되며 molecular orbital을 구성할 수 있게 된다.
bonding을 구성하는 조건으로 다음의 세가지를 들 수 있다.
1. 두 orbital symmetry의 sign이 같아야 한다.
2. 두 atomic orbitals의 에너지가 서로 비슷해야한다.
3. 두 원자간의 거리가 적당히 가까워야 한다.

# Molecular orbitals from s orbitals

아래는 H<sub>a</sub>, H<sub>b</sub>를 가진 H<sub>2</sub> 분자의 molecular orbital (MO)이다.

<p><span class="math inline">\(\begin{aligned} \Psi(\sigma) &amp;=N\left[c_{a} \psi\left(1 s_{a}\right)+c_{b} \psi\left(1 s_{b}\right)\right]=\frac{1}{\sqrt{2}}\left[\psi\left(1 s_{a}\right)+\psi\left(1 s_{b}\right)\right]\left(\mathrm{H}_{a}+\mathrm{H}_{b}\right) \\ \Psi\left(\sigma^{*}\right) &amp;=N\left[c_{a} \psi\left(1 s_{a}\right)-c_{b} \psi\left(1 s_{b}\right)\right]=\frac{1}{\sqrt{2}}\left[\psi\left(1 s_{a}\right)-\psi\left(1 s_{b}\right)\right]\left(\mathrm{H}_{a}-\mathrm{H}_{b}\right) \end{aligned}\)</span></p>

여기서 __Atomic orbital(AO)의 부호(sign)는 임의적이다.__

Bonding MO는 두 AO의 합으로 두 원자핵 사이의 electron concentration을 증가시키고, 에너지를 낮다.  
Antibonding MO는는 두 AO의 차로 두 wave function의 상쇄로 인해 zero electron density, 즉 node가 생기고, 에너지가 높다. 이러한 antibonding MO의 electron은 두 원자 사이에 반발력을 일으킨다.  
Nonbonding orbital도 가능한데, 한 원자의 AO symmetry가 다른 원자의 AO symmetry와 맞지 않거나, 우연히 MO의 에너지가 AO의 에너지가 같은 경우이다.  
__어떤 상황에서든 MO의 수는 AO의 수와 같다.__

# Molecular orbitals from p orbitals
두 원자핵을 연결하는 축을 z축으로 정의하자. 이 경우 p<sub>z</sub> orbital끼리 빼야, σ orbital을 이루고, 더하면 σ* orbital을 만든다.

![image-center]({{ 'images/p_orbital_interaction.PNG' | absolute_url }}){: .align-center}

같거나 반대의 sign을 가진 orbital overlap의 기여가 같으면, bonding과 antibonding의 효과가 상쇄되어 MO를 만들지 않는다. 즉, 한 원자의 AO symmetry properties가 다른 원자의 __어떠한__ AO와도 맞지 않으면(do not match), __nonbonding orbital__ 이라고 한다.

# Molecular orbitals from d orbitals

![image-center]({{ 'images/d_orbital_interaction.PNG' | absolute_url }}){: .align-center}


<head>
<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
</style>
</head>
<body>

<h2>bonding notation</h2>

<table>
  <tr>
    <th>notation</th>
    <th>symmetry</th>
    <th># of nodes that include the center of bond axis</th>
  </tr>
  <tr>
    <td>σ(sigma)</td>
    <td>symmetric to rotation about bond axis</td>
    <td>0</td>
  </tr>
  <tr>
    <td>π(pi)</td>
    <td>change in sign with C<sub>2</sub> rotation</td>
    <td>1</td>
  </tr>
  <tr>
    <td>𝛿(delta)</td>
    <td>change in sign with C<sub>4</sub> rotation</td>
    <td>2</td>
  </tr>
</table>

</body>

# Molecular orbitals
Lewis electron-dot diagram을 이용하면 N<sub>2</sub>, O<sub>2</sub>, F<sub>2</sub>와 같은 분자들은 큰 문제가 없지만, Li<sub>2</sub>, Be<sub>2</sub>, B<sub>2</sub>, C<sub>2</sub>와 같은 분자들은 octet rule을 만족시키지 않기 때문에 설명하기 어렵다. 게다가 O<sub>2</sub>는 실험적으로 두개의 unpaired electrons이 관측되고 따라서 paramagnetic 성질을 보이는데 Lewis 방식으로는 이를 설명할 수 없으므로 Molecular orbital이 필요하다.
![image-center]({{ 'images/O2_molecule.PNG' | absolute_url }}){: .align-center}




## bond order
bonding과 antibonding electrons의 수는 bond의 수를 결정하는데, 이를 __bond order__ 라 한다.  
<p class="text-center"> Bond order = 1/2*{(# of e<sup>-</sup> in bonding orbitals)-(# of e<sup>-</sup> in antibonding orbitals)} </p>

O<sub>2</sub>를 예로들면 1/2*(10-6) = 2 로 Lewis electron-dot diagram의 경우와 같이 double bond를 나타낸다.

# Orbital Mixing

같은 symmetry를 가진 두 개의 __MO__ 이 비슷한 에너지를 가질 때, 이 둘은 서로 상호작용하여 낮은 orbital의 에너지를 더 낮추고, 높은 orbital의 에너지는 더 높인다.
아래의 homonuclear diatomics의 예를 보면, __<font color="red">σ<sub>g</sub>(2s)</font>__ 와 __<font color="blue">σ<sub>g</sub>(2p)</font>__ 는 같은 σ<sub>g</sub> symmetry를 가지고 있고, 서로 상호작용하여 __<font color="red">σ<sub>g</sub>(2s)</font>__ 의 에너지를 낮추고 __<font color="blue">σ<sub>g</sub>(2p)</font>__ 의 에너지를 높인다. 비슷하게, σ<sub>u</sub>* 끼리도 상호작용하여 <font color="red">σ<sub>u</sub>* (2s)</font> 의 에너지를 낮추고, <font color="blue">σ<sub>u</sub>* (2p)</font>의 에너지를 높인다.  

![image-center]({{ 'images/orbital_mixing.PNG' | absolute_url }}){: .align-center}

이 __네 개의 MO__ 를 비슷한 에너지를 가진 네 개의 AO의 combination으로 다음과 같이 나타낼 수 있다.


<p><span class="math inline">\(\Psi=c_{1} \psi\left(2 s_{a}\right) \pm c_{2} \psi\left(2 s_{b}\right) \pm c_{3} \psi\left(2 p_{a}\right) \pm c_{4} \psi\left(2 p_{b}\right)\)</span></p>

Homonuclear molecules의 경우 c<sub>1</sub>=c<sub>2</sub>, c<sub>3</sub>=c<sub>4</sub> 이다.
이 __네 개의 MO__ 는 mixing을 하지 않았을 때와 symmetry는 같지만, s와 p character의 mixing 때문에 모양은 좀 달라진다.

# Homonuclear Diatomic Molecules
먼저 magnetism에 대한 정리부터 시작해보자.  
__Diamagnetism__: unpaired electron이 없고, magnetic field에 대해 아주 적은 양만큼 __척력이 작용함.__  
__Paramagnetism__: unpaired electron이 작은 자석처럼 작용하여 외부 magnetic field에 대해 인력이 작용하지만 __magnetic field가 있을 때만 magnetized 됨.__  
__Ferromagnetism__: magnetic field로 인해 유도된 magnetism이 __field가 사라져도 유지됨.__


Homonuclear diatomic molecule의 경우를 보자.
__같은 symmetry를 갖는__ __σ<sub>g</sub>(2s)__ 와 __<font color="blue">σ<sub>g</sub>(2p)</font>__ 가 Mixing 하여 <font color="blue">σ<sub>g</sub>(2p)</font>의 에너지는 올라가고, σ<sub>g</sub>(2s)의 에너지는 내려간다. 따라서 nuclear charge (Z)가 작을 때는 <font color="blue">σ<sub>g</sub>(2p)</font>의 에너지가 <font color="darkorange">π<sub>u</sub>(2p)</font>의 에너지보다 높아진다. Z가 커질수록 σ orbital의 에너지가 π orbital 보다 더 크게 낮아지게 되는데, 이는 σ interaction에 참여하는 atomic orbital의 overlap이 더 크기 때문이다. 또한 2s orbital이 2p 보다 shielding effect가 적기 때문에 Z가 커질수록 더욱 크게 안정화되고, 2s와 2p간의 에너지차이가 심해지면서 mixing이 적어지고 따라서 <font color="blue">σ<sub>g</sub>(2p)</font>의 에너지가 <font color="darkorange">π<sub>u</sub>(2p)</font> 보다 낮아지게 된다.


![image-center]({{ 'images/homo_diatomic.PNG' | absolute_url }}){: .align-center}

MO theory에서는 Mixing 통해, 위의 그림처럼 B<sub>2</sub> 와 O<sub>2</sub> 가 Paramagnetic 성질을 갖는 지, C<sub>2</sub>가 어떻게 σ bond 없이 π bond만 가질 수 있는지, F<sub>2</sub>가 왜 그토록 reactive 한 지(bond order=1) 설명할 수 있다.

orbital의 에너지는 __photoelectron spectroscopy (PES)__ 를 통해 직접적으로 측정할 수 있다. 입사된 광자의 에너지에서 튀어나온 electron의 kinetic energy의 차이가 __ionization energy__ 이다. Ultraviolet lights은 주로 outer electrons을, X-rays는 주로 inner electron을 제거할 때 사용한다.  

위 PES stpectrum에서 N<sub>2</sub>와 O<sub>2</sub>의 <font color="blue">σ<sub>g</sub>(2p)</font>와 <font color="darkorange">π<sub>u</sub>(2p)</font>의 에너지가 역전되어 있는 것도 볼 수 있다.  

PES spectrum에서 electronic energy의 vibration energy와의 상호작용도 볼 수 있다. vibrational energy간의 energy level은 electronic energy 보다 훨씬 작기 때문에, electronic level간의 transition은 vibraional level간의 transition 또한 포함하게 되어, multiple peaks로 나타나게 된다. __bonding에 밀접하게 관여하는 orbital일 수록 vibrational fine peaks (multiple peaks)를 나타내게 된다.__


# Polar Bonds
Heteronuclear diatomic molecules의 경우에는 서로 다른 nuclear charge를 가진 atom이 bond를 형성하고 있다. 각각의 오비탈 에너지가 다르기 때문에 MO를 형성했을 때 각 atom의 AO의 MO에 대한 기여도 달라지게 된다. __한 atom의 AO가 MO의 에너지가 더 가깝다면 해당 MO에 더 많은 기여를 하게 되고, 더 큰 coefficeint를 갖는다.__ 일반적으로 AO orbital의 에너지가 12 or 13 eV 이상 차이가 나게되면 거의 상호작용하지 않는다고 생각한다.  

CO의 경우를 예로들어 보자.
먼저 주의할 점은 CO는 C<sub>∞υ</sub> symmetry를 가지고 있지만, 우리는 MO의 형성에 대해서 이야기 하고 있기 때문에 orbital의 symmetry를 고려해야한다. orbital lobe의 sign을 무시한다면, p<sub>x</sub>와 p<sub>y</sub>는 C<sub>2υ</sub> symmetry를 가지는데, __orbital의 point group을 결정할 때만 sign을 무시하고 이후의 과정에 대해서는 모두 고려__ 해야 한다.  

![image-center]({{ 'images/CO_MO_1.PNG' | absolute_url }}){: .align-center}

s와 p<sub>z</sub> orbital은 A<sub>1</sub> (or a<sub>1</sub>) symmetry를 가지고, σ symmetry를 가진 MO를 형성한다. 반면, p<sub>x</sub>와 p<sub>y</sub>는 각각 B<sub>1</sub>, B<sub>2</sub> or (or b<sub>1</sub>, b<sub>2</sub>) symmetry를 가지고 π symmetry를 가진 MO를 형성한다.  

![image-center]({{ 'images/CO_MO_2.PNG' | absolute_url }}){: .align-center}

C 2s와 O 2s는 이미 ~ 13 eV 정도차이가 나기 때문에 MO를 형성할때 큰 interaction이 없을것이라 예상할 수 있다. 실제로 2σ orbital은 O 2s AO과 매우 가깝고, 2σ* 은 C 2s와 매우 가까운 것을 볼 수 있다.
반면 C 2p와 O 2p는 ~ 5 eV 정도 차이가 나므로 보다 강한 interaction이 가능하고 3σ이 어느정도 중간 값에 위치하는 것을 볼 수 있다. 3σ MO의 경우 orbital의 모양을 보면 C의 contribution이 더 커서 C 쪽의 orbital이 더 큰 것을 볼 수 있다 (bigger coefficient). 단순히 Electronegativity만으로 설명을 하려고 하면 이것을 이해가 되지 않는데, MO theory에서는 O 2p orbital의 경우 2σ* ( ,3σ, 3σ* ) 와도 상호작용이 가능하지만, C 2p의 경우엔 3σ 와 3σ* 에만 크게 기여하기 때문에 이와 같은 현상을 설명할 수 있다. 이것은 특히 Metal (M)과의 결합을 설명하는데 있어 매우 중요한데, CO의 3σ MO는 C 쪽에 더 많은 electron이 있기 때문에 O 보다는 C 가 M의 비어있는 orbital과 더 많이 상호작용하게 되고 따라서 M-O-C가 아닌 M-C-O의 binding mode를 갖게 된다.  


# Ionic Compounds
electronegativity의 차이가 극도로 많이 날 경우에는 electron이 more electronegative한 원자로 완전히 전달되고, 높은 에너지를 가진 양이온의 orbital은 비어지게 된다. 하지만 MO theory에서는 이러한 ion pair 또한 covalent compound로 고려될 수 있다.
