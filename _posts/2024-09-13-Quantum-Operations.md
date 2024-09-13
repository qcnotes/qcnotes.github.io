---
layout: "post"
title: "P5. Quantum Operations"
---
We had looked at two transformations of quantum system so far in the previous blog post.

- Closed system unitary evolution that is reversible and preserves information.
- Measurement that is non-reversible, probabilistic, and loses information in the process.

Are these the only quantum transformations possible? Are there any other quantum transformations that need to be looked at? We have overlooked another important quantum system (i.e) open quantum system. How does open quantum system that interacts with its surrounding environment evolve? Does open quantum system evolve unitarily?  

We would look at open quantum system evolution in this blog post. The open quantum system evolution is called Quantum operations or Quantum channel or Quantum noisy channel.  

Let us consider a system A with its Hilbert space $H_{A}$. The quantum system A is open system, and it interact with environment E. Let E's Hilbert space be $H_{E}$. We can safely assume that the composite system A & E is closed quantum system, and it evolves unitarily $U_{AE}$ as depicted in the below figure.  

Figure  

We are however interested in the system A’s evolution and it's the final state $\varepsilon(\rho)$ post evolution. The unitary evolution has entangled quantum system A & E and to obtain state of system A, the environment E must be traced out from the composite system.  

Equation
