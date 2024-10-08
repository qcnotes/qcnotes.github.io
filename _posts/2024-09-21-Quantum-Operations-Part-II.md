---
layout: "post"
title: "P6. Quantum Operations - Part II"
---

How does open quantum system that interacts with its surrounding environment evolve? Does open quantum system evolve unitarily? The open quantum system evolution is called Quantum operations or Quantum channel or Quantum noise channel. The open quantum system evolution is non-reversible and loses information in the process.

Let us consider a system S with its Hilbert space $H_{S}$. The quantum system S is open system, and it interact with environment E. Let E's Hilbert space be $H_{E}$ and $\|e_{i}\rangle_{E}$ be its orthonormal basis. We can safely assume that the composite system S & E is closed quantum system, and it evolves unitarily $U_{SE}$ as depicted in the below figure.  

![quantum operation image](/assets/images/quantum_operations.jpg)   

*Fig.1 Quantum operations* 

We are however interested in the system S’s final state $\varepsilon(\rho_{S})$ post evolution. The unitary evolution has entangled quantum system S & E and to obtain state of system s, the environment E must be traced out from the composite system.  

The composite state of system S & E is  

$$
\sigma_{SE} = U_{SE}(\rho_{S} \otimes |e_{0}\rangle_{E} \langle e_{0}|_{E})U_{SE}^{+}  \qquad \\
$$

By tracing out the environment, we obtain evolved state of  system S as,  

$$
\begin{equation}
\begin{split}
\varepsilon(\rho_{S}) = Tr_{E}\{\sigma_{SE}\} \qquad \qquad \qquad \qquad \qquad \qquad \\
= Tr_{E}\{U_{SE}(\rho_{S} \otimes |e_{0}\rangle_{E} \langle e_{0}|_{E})U_{SE}^{+}\} \qquad \qquad \\
=\sum_{i=1}^{N} \langle e_{i}|_{E} U_{SE}(\rho_{S} \otimes |e_{0}\rangle_{E} \langle e_{0}|_{E}) U_{SE}^{+} |e_{i}\rangle_{E} \quad \quad \\
=\sum_{i=1}^{N} (\langle e_{i}|_{E} U_{SE} |e_{0}\rangle_{E}) \rho_{S}  (\langle e_{0}|_{E} U_{SE}^{+} |e_{i}\rangle_{E}) \quad \quad \quad \\
=\sum_{i=1}^{N} E_{i} \rho_{S} E_{i}^{+} \qquad \qquad \qquad \qquad \qquad \quad \quad \\
\end{split}
\end{equation}
$$

The above equation is called Choi-Kraus representation or Operator-Sum representation of quantum operations. The $$E_{i}=\langle e_{i}\|_{E} U_{SE}\|e_{0}\rangle_{E}$$ are called Kraus operators and they satisfy 

$$
\begin{equation}
\begin{split}
\sum_{i=1}^{N} E_{i}^{+} E_{i} = \sum_{i=1}^{N} (\langle e_{0}|_{E} U_{SE}^{+} |e_{i}\rangle_{E})(\langle e_{i}|_{E} U_{SE} |e_{0}\rangle_{E}) \\
= \langle e_{0}|_{E} U_{SE}^{+} (\sum_{i=1}^{N} |e_{i}\rangle_{E} \langle e_{i}|_{E}) U_{SE} |e_{0}\rangle_{E} \\
= \langle e_{0}|_{E} (U_{SE}^{+} U_{SE}) |e_{0}\rangle_{E} \qquad \qquad \quad \\
= \langle e_{0}|_{E} |e_{0}\rangle_{E} \qquad \qquad \qquad \quad \quad \\
= I \qquad \qquad \qquad \qquad \qquad \quad \quad \\
\end{split}
\end{equation}
$$

The noise in quantum system is represented by Kraus operators $\{E_{i}\}$ satifying $\sum_{i=1}^{N} E_{i}^{+} E_{i} = I$. The noisy open system evolution preserves positivity, and trace one properties. The trace of final state is

$$
Tr\{ \sum_{i=1}^{d} E_{i} \rho E_{i}^{+} \} = Tr\{ \sum_{i=1}^{d} E_{i}^{+} E_{i} \rho  \} = Tr\{\rho \} = 1
$$

Since $\rho$ is positive semi-definite, it can be factored as below to prove positivity of final state.

$$
\sum_{i=1}^{d} E_{i} \rho E_{i}^{+} = \sum_{i=1}^{d} (E_{i} \sqrt\rho) (\sqrt\rho E_{i}^{+}) \geqslant 0 
$$

