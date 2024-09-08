---
layout: page
title: "P4. Quantum Purification"
---

#### **Schmidt Decomposition:**
By Schmidt Decomposition, the pure state $\|\psi\rangle_{AB}$ of composite system A & B can be decomposed as

$$|\psi\rangle_{AB} = \sum_{i=1}^{d} \lambda_{i} |i\rangle_{A} |i\rangle_{B}$$

where, $\lambda_{i}$ are Schmidt coefficients, $d$ is Schmidt rank, $\|i\rangle_{A}$ & $\|i\rangle_{B}$ are Schmidt basis. We have seen that, the state of individual systems A & B are mixed states as provided below even though the composite system was pure state.

$$\rho_{A} = \sum_{i=1}^{d} \lambda_{i}^2 |i\rangle_{A} \langle i|_{A}, \quad \rho_{B} = \sum_{i=1}^{d} \lambda_{i}^2 |i\rangle_{B} \langle i|_{B} $$

Can any mixed state of smaller system A be associated with pure state in larger composite quantum system A & B? Quantum purification provides the answer.  

#### **Quantum purification:**

Quantum purification is a mathematical construct to associate a pure state $\|\psi\rangle_{AR}$ in larger composite system A & R to any mixed state $\rho_{A}$ of smallar system A. Let $\rho_{A}$ be mixed state of quantum system A with dimenstion $n$. Since $\rho_{A}$ is positive density operator, it has spectral decomposition

$$\rho_{A} = \sum_{i=1}^{n} p_{i} |e_{i}\rangle_{A} \langle e_{i}|_{A}$$

where, $p_{i}$ are eigen values, and $\|e_{i}\rangle_{A}$ are eigen states of system A. Let us consider another reference system R with the same dimension as A. Let $\|f_{i}\rangle_{A}$ be any orthonormal basis of system R. We can construct a pure state in composite system A & R as

$$|\psi\rangle_{AR} = \sum_{i=1}^{n} \sqrt{p_{i}} |e_{i}\rangle_{A} |f_{i}\rangle_{R}$$

If we trace out R from composite system, we get

$$ \rho_{A} = Tr_R (|\psi\rangle_{AR} \langle \psi|_{AR} ) $$

The pure state association is not unique since orthonormal basis of system R is not unique. We can select different orthonormal basis and get different pure state in larger composite system.

*Note: what is the physical signicance of quantum purification?
