---
layout: post
title: "P4. Quantum Purification"
categories: misc
---

By Schmidt Decomposition, the pure state $|\psi\rangle_{AB}$ of composite system A & B can be decomposed as

$$|\psi\rangle_{AB} = \sum_{i=1}^{d} \lambda_{i} |i\rangle_{A} |i\rangle_{B}$$

where, $\lambda_{i}$ are Schmidt coefficients, $d$ is Schmidt rank, $|i\rangle_{A}$ & $|i\rangle_{B}$ are Schmidt basis. We have seen that, the state of individual systems A & B are mixed states even though the composite system was pur state.

$$\rho_{A} = \sum_{i=1}^{d} \lambda_{i}^2 |i\rangle_{A} \langle i|_{A}$$

Can any mixed state of system A be associated with pure state in larger composite quantum system A & B? Quantum purification provides the answer.  

Quantum purification is a mathematical construct to associate a pure state $|\psi\rangle_{AR}$ in larger composite system A & R to any mixed state $\rho_{A}$ of smallar system A. Let $\rho_{A}$ be mixed state of quantum system A with dimenstion $n$. Since $\rho_{A}$ is positive density operator, it has spectral decomposition

$$\rho_{A} = \sum_{i=1}^{n} p_{i} |e\rangle_{A} \langle e|_{A}$$

where, $p_{i}$ are eigen values, and $|e\rangle_{A}$ are eigen states of system A. Let us consider another system R with the same dimension as A. Let $|e\rangle_{A}$ be any orthonormal basis of system R. We can construct a pure state in composite system A & R as

$$|\psi\rangle_{AR} = \sum_{i=1}^{n} \sqrt{p_{i}} |e\rangle_{A} |f\rangle_{R}$$

If we trace out R from $Tr_R\{|\psi\rangle_{AR} \langle \phi|_{AR}\} \text{, then we get} \rho_{A} $. The pure state association is not unique since orthonormal basis of system R is not unique. We can select different orthonormal basis and get different pure state in larger composite system.

*Note: what is the physical signicance of quantum purification.
