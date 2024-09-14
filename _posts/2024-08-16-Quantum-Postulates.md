---
layout: "post"
title: "P1. Quantum Postulates"
---

#### 1) **State postulate:**
Every quantum system A is associated with Hilbert space $H_A$. The state of quantum system is described by positive linear map   

  $$\rho: H_A \to H_A$$  

such that,  

  $$\rho >= 0, Tr(\rho) = 1$$  

These conditions are required to ensure probability axioms. This postive linear map is known as Density operator. 

#### 2) **Evolution postulate:** 
The closed quantum system evolves unitarily as  

$$\rho' = U \rho U^{+}$$  

where, U is unitary operator and $\rho'$ is new state after evolution. Again, the unitary condition is required to ensure probability axioms.  
#### 3) **Measurement postulate:**
The measurement of quantum system is probabilistic in nature and it is represented by matrices $\\{M_i\\}$ satisfying the condition  

$$\sum_{i=1}^{d} M_{i}^{+} M_i=1$$  

These measurements are known as Positive Operator Valued Measure(POVM). The probability of measuring outcome $i$ is $p(i)=tr(M_{i} \rho M_{i}^{+})$ and state of quantum system after measurement is  

$$\rho_{i}' = \frac{M_{i} \rho M_{i}^{+}}{tr(M_{i} \rho M_{i}^{+})}$$  

#### 4) **Composite system postulate:**
Let A and B be two quantum systems associated with corresponding Hilbert space $H_A$ and $H_B$. The associated Hilbert space of composite system $A \otimes B$ is $H_A \otimes H_B$.  
The state of composite system is described as  

$$\rho_{AB}: H_A \otimes H_B \to H_A \otimes H_B$$ 

