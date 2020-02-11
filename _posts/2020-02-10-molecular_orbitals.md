---
title: "Molecular orbitals"
date: 2020-01-29T08:08:50-04:00
category: Inorganic Chemistry
tags:
  - Inorganic Chemistry
  - Molecular orbitals
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

여기서 Atomic orbital(AO)의 부호(sign)는 임의적이다.

Bonding MO는 두 AO의 합으로 두 원자핵 사이의 electron concentration을 증가시키고, 에너지를 낮다.  
Antibonding MO는는 두 AO의 차로 두 wave function의 상쇄로 인해 zero electron density, 즉 node가 생기고, 에너지가 높다. 이러한 antibonding MO의 electron은 두 원자 사이에 반발력을 일으킨다.  
Nonbonding orbital도 가능한데, 한 원자의 AO symmetry가 다른 원자의 AO symmetry와 맞지 않거나, 우연히 MO의 에너지가 AO의 에너지가 같은 경우이다.  
__어떤 상황에서든 MO의 수는 AO의 수와 같다.__

# Molecular orbitals from p orbitals
두 원자핵을 연결하는 축을 z축으로 정의하자. 이 경우 p<sub>z</sub> orbital끼리 빼야, σ orbital을 이루고, 더하면 σ* orbital을 만든다.

![image-center]({{ 'images/p_orbital_interaction.PNG' | absolute_url }}){: .align-center}

같거나 반대의 sign을 가진 orbital overlap의 기여가 같으면, bonding과 antibonding의 효과가 상쇄되어 MO를 만들지 않는다. 즉, 한 원자의 AO symmetry properties가 다른 원자의 어떠한 AO와도 맞지 않으면(do not match), nonbonding orbital이라고 한다.

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






