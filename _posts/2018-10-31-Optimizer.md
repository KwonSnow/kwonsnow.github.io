---
title: "Optimizer"
date: 2019-10-17T08:08:50-04:00
category: DFT
tags:
  - DFT
  - VASP
  - optimizer
  - ionic minimization
---

# Force-based optimizer
## quasi-Newton algorithm (RMM-DIIS) : IBRION = 1
POTIM : the step size in the steepest descent step  
NFREE : s how many ionic steps are stored in the iteration history  

## damped molecular dynamics : IBRION = 3
<p><span class="math inline">\(\ddot{\vec{x}}=-2 \alpha \vec{F}-\mu \dot{\vec{x}}\)</span></p>
POTIM : controls α  
SMASS : dampling factor μ  
μ=2 is equivalent to a simple steepest descent algorithm  (maximal damping)  
μ=0 corresponds to no damping  

# Others
IBRION = 2 : conjugate gradient  



![image-center]({{ '/images/optimizer.PNG' | absolute_url }}){: .align-center}



