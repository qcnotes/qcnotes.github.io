---
layout: "post"
title: "P5. Quantum Operations"
---
We had looked at two quantum transformations of a system so far in the previous blog post.

- Closed system unitary evolution that is reversible and preserves information.
- Measurement that is non-reversible, probabilistic, and loses information in the process.

Are these the only quantum transformations possible? Are there any other quantum transformations that need to be looked at? We have overlooked another important quantum system (i.e) open quantum system. How does open quantum system that interacts with its surrounding environment evolve? Does open quantum system evolve unitarily?  

We would look at open quantum system evolution in this blog post. The open quantum system evolution is called Quantum operations or Quantum channel or Quantum noisy channel.  

Let us consider a system S with its Hilbert space $H_{S}$. The quantum system S is open system, and it interact with environment E. Let E's Hilbert space be $H_{E}$ and $\|e_{i}\rangle_{E}$ be its orthonormal basis. We can safely assume that the composite system S & E is closed quantum system, and it evolves unitarily $U_{SE}$ as depicted in the below figure.  

![quantum operation image](/assets/images/quantum_operations.jpg)   

*Fig.1 Quantum operations* 

We are however interested in the system S’s final state $\varepsilon(\rho)$ post evolution. The unitary evolution has entangled quantum system S & E and to obtain state of system s, the environment E must be traced out from the composite system.  

The composite state of system S & E is  

$$
\sigma_{SE} = U_{SE}(\rho_{S} \otimes |e_{0}\rangle_{E} \langle e_{0}|_{E})U_{SE}^{+}  \qquad \\
$$

By tracing out the environment, we obtain evolved state of  system S as,  

$$
\begin{equation}
\begin{split}
\varepsilon(\rho) = Tr_{E}\{\sigma_{SE}\} \qquad \qquad \qquad \qquad \qquad \qquad \\
= Tr_{E}\{U_{SE}(\rho_{S} \otimes |e_{0}\rangle_{E} \langle e_{0}|_{E})U_{SE}^{+}\} \qquad \qquad \\
=\sum_{i=1}^{N} \langle e_{i}|_{E} U_{SE}(\rho_{S} \otimes |e_{0}\rangle_{E} \langle e_{0}|_{E}) U_{SE}^{+} |e_{i}\rangle_{E} \quad \quad \\
=\sum_{i=1}^{N} (\langle e_{i}|_{E} U_{SE} |e_{0}\rangle_{E}) \rho_{S}  (\langle e_{0}|_{E} U_{SE}^{+} |e_{i}\rangle_{E}) \quad \quad \quad \\
=\sum_{i=1}^{N} E_{i} \rho_{S} E_{i}^{+} \qquad \qquad \qquad \qquad \qquad \quad \quad \\
\end{split}
\end{equation}
$$

The above equation is called Choi-Krauss representation or Operator-Sum representation of quantum operations. The $$E_{i}=\langle e_{i}\|_{E} U_{SE}\|e_{0}\rangle_{E}$$ are called Krauss operators and they satisfy 

$$
\begin{equation}
\begin{split}
\sum_{i=1}^{N} E_{i}^{+} E_{i} = \sum_{i=1}^{N} (\langle e_{0}|_{E} U_{SE}^{+} |e_{i}\rangle_{E})(\langle e_{i}|_{E} U_{SE} |e_{0}\rangle_{E}) \\
= \langle e_{0}|_{E} U_{SE}^{+} (\sum_{i=1}^{N} |e_{i}\rangle_{E} \langle e_{i}|_{E}) U_{SE} |e_{0}\rangle_{E} \\
= \langle e_{0}|_{E} U_{SE}^{+} (I) U_{SE} |e_{0}\rangle_{E}  \qquad \qquad \quad \\
= \langle e_{0}|_{E} (U_{SE}^{+} U_{SE}) |e_{0}\rangle_{E}  \qquad \qquad \quad \\
= \langle e_{0}|_{E} |e_{0}\rangle_{E}  \qquad \qquad  \qquad \qquad \\
= I  \qquad \qquad  \qquad \qquad  \qquad \qquad  \qquad \qquad \\
\end{split}
\end{equation}
$$


