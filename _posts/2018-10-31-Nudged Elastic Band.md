---
title: "Nudged Elastic Band (NEB) method"
date: 2019-10-17T08:08:50-04:00
category: DFT
tags:
  - Quantum Mechanics
  - DFT
  - VASP
  - NEB
  - optimizer
---

# Optimizer
## Force-based optimizer
### quasi-Newton algorithm (RMM-DIIS)  
IBRION = 1  : quasi-Newton algorithm (RMM-DIIS)  
POTIM : the step size in the steepest descent step  
NFREE : s how many ionic steps are stored in the iteration history  

### damped molecular dynamics  
IBRION = 3  : damped molecular dynamics
<p><span class="math inline">\(\ddot{\vec{x}}=-2 \alpha \vec{F}-\mu \dot{\vec{x}}\)</span></p>
SMASS : dampling factor μ  
POTIM : controls α  
  
## Others
IBRION = 2 : conjugate gradient


## CI-NEB
