---
layout: "post"
title: "P5. Quantum Operations - Part I"
---
We had looked at two quantum transformations so far in the previous blog post.

- Closed system unitary evolution: It is a linear map from set of density operators to another set of density operator.

$$
\begin{equation}
\begin{split}
\mathcal{U}: \mathcal{S}(H) \rightarrow \mathcal{S}(H) \quad \\
\rho \rightarrow U \rho U^{+} \quad \\
\end{split}
\end{equation}
$$  

The evolution preserves positivity, and trace one properties of final state $U \rho U^{+}$. The trace of final state is

$$
Tr\{ U \rho U^{+} \} = Tr\{U^{+} U \rho \} = Tr\{\rho \} = 1
$$

Since $\rho$ is positive semi-definite, it can be factored as below to prove positivity of final state.

$$
U \rho U^{+} = (U \sqrt\rho) (\sqrt\rho U^{+}) \geqslant 0 
$$

- Measurement:  It is another linear map from from set of density operators to another set of density operator.

$$
\begin{equation}
\begin{split}
\mathcal{M}: \mathcal{S}(H) \rightarrow \mathcal{S}(H) \quad \quad \quad \\
\rho \rightarrow \sum_{i=1}^{d} M_{i} \rho M_{i}^{+} \quad \\
\end{split}
\end{equation}
$$  

The measuremnt also preserves positivity, and trace one properties of final state $\sum_{i=1}^{d} M_{i} \rho M_{i}^{+}$. The trace of final state is

$$
Tr\{ \sum_{i=1}^{d} M_{i} \rho M_{i}^{+} \} = Tr\{ \sum_{i=1}^{d} M_{i}^{+} M_{i} \rho  \} = Tr\{\rho \} = 1
$$

Since $\rho$ is positive semi-definite, it can be factored as below to prove positivity of final state.

$$
\sum_{i=1}^{d} M_{i} \rho M_{i}^{+} = \sum_{i=1}^{d} (M_{i} \sqrt\rho) (\sqrt\rho M_{i}^{+}) \geqslant 0 
$$

Both closed system unitary evolution and measurement preserves positivity and trace one properties of quantum system. Are these the only quantum transformations possible? Are there any other quantum transformations that need to be looked at? 

All the quantum transformations that exist should be a linear map from density operator to density operator 

$$
\begin{equation}
\begin{split}
\mathcal{E}: \mathcal{S}(H) \rightarrow \mathcal{S}(H) \\
\rho \rightarrow \mathcal{E}(\rho) \\
\end{split}
\end{equation}
$$  

preserving trace $Tr(\mathcal{E}(\rho)) = 1$ and positivity $\mathcal{E}(\rho) \geqslant 0 $. The general quantum transformation should satisfy complete positivity in addition to positive which we shall look at in the later post.

#### Open Quantum system:
We have overlooked another important quantum system (i.e) open quantum system. How does open quantum system that interacts with its surrounding environment evolve? Does open quantum system evolve unitarily? The open quantum system evolution is called Quantum operations or Quantum channel or Quantum noisy channel. The open quantum system evolution is non-reversible and loses information in the process.

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

The above equation is called Choi-Krauss representation or Operator-Sum representation of quantum operations. The $$E_{i}=\langle e_{i}\|_{E} U_{SE}\|e_{0}\rangle_{E}$$ are called Krauss operators and they satisfy 

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


