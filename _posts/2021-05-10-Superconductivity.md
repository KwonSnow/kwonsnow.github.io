---
title: "Superconductivity"
date: 2021-05-10T08:08:50-04:00
category: Solid state physics
tags:
  - Superconductivity
---


# Superconducting transition temperature (T<sub>c</sub>)

Tc from the first principle calculations  

[npj Comput Mater 2020, 6, 94](https://doi.org/10.1038/s41524-020-00365-9)  
VASP + QuantumEspresso(QE)  

When you know the Tc for parent materials  
## McMillan formula
<p><span class="math inline">\(T_{c}=\frac{\Theta_{D}}{1.45} \exp \left[\frac{-1.04(1+\lambda)}{\lambda-\mu^{*}(1+0.62 \lambda)}\right]\)</span></p>
three parameters: Debye temperature, (Θ<sub>D</sub>), electron-phonon mass enhacement factor (1+λ) and the Coulomb electron-electron interaction strength which is acoounted by the Coulomb pseudopotential, μ*.  
μ* has been given by the Bennemann-Garland equation  
<p><span class="math inline">\(\mu^{*}=0.13 \frac{N\left(E_{F}\right)}{1+N\left(E_{F}\right)}\)</span></p>
DOS using McMillan formula  
Θ<sub>D</sub> is known from [67] and the electron-phonon mass enhancement factor (1+λ) can be estimated by following expression  
<p><span class="math inline">\(\frac{\gamma}{\gamma_{b}}=1+\lambda\)</span></p>  
where the γ and γ<sub>b</sub> [mJ/mol·K<sup>2</sup>] are the experimental and theoretical Sommerfeld constant, γ<sub>b</sub> is given by  
<p><span class="math inline">\(\gamma_{b}=\frac{1}{3} \pi^{2} k_{B}^{2} N\left(E_{F}\right)=(2.359) N\left(E_{F}\right)\)</span></p>
According to the nearly free electron model, the normal-state electronic heat capacity (C<sub>e</sub>) is proportional to absolute temperature that can be represented by C<sub>e</sub> = γ<sub>b</sub>T. Therefore, from DOS, one can estimate the values of bare Sommerfeld constant (γ<sub>b</sub>) and electron-phonon mass enhacement factor (1+λ) with the assist of experimental values of γ.
[Comput. Mater. Sci. 2021, 190, 110254](https://doi.org/10.1016/j.commatsci.2020.110254)
