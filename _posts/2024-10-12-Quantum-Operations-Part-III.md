---
layout: "post"
title: "P7. Quantum Operations - Part III"
---

In this post, we shall look at few examples of quantum channels/operations such as bit-flip channel, phase-flip channel, etc.

#### 1) **Bit flip channel:**
The bit-flip channel is represented by Krauss operators $( \sqrt{1-p}I, \sqrt{p}X)$, where $p$ is bit-flip error probability. The bit-flip channel acting on input density operator $\rho$ transforms it to

$$
\begin{equation}
\begin{split}
\rho_{out} = \sum_{i=1}^{2} E_{i} \rho E_{i}^{+}  \quad  \quad \quad \quad  \\
= (1-p) \rho + p X \rho X^{+}  \\
= (1-p) \rho + p X \rho X \quad  \\
\end{split}
\end{equation}
$$  

The system stays in the same state $\rho$ with probability (1-p) and flips to $X \rho X$ with probability p. Let us consider bit-flip channel effect on general two-qubit quantum system Bloch sphere represented is $\rho = \frac{I + r_{x} X + r_{y} Y + r_{z} Z\}{2}$. The two-qubit quantum system Bloch sphere is compactly denoted as $(r_{x},r_{y},r_{z})$. 

$$  
\begin{equation}
\begin{split}
\rho_{out} = (1-p) \rho + p X \rho X \qquad \qquad \qquad \qquad \qquad \qquad \qquad \qquad \qquad \qquad \qquad \\
= (1-p) \left( \frac{I + r_{x} X + r_{y} Y + r_{z} Z\}{2} \right) + p X \left( \frac{I + r_{x} X + r_{y} Y + r_{z} Z\}{2} \right) X \qquad \quad \quad \\
= (1-p) \left( \frac{I + r_{x} X + r_{y} Y + r_{z} Z\}{2} \right) + p \left( \frac{X X + r_{x} X X X + r_{y} X Y X + r_{z} X Z X \}{2} \right)  \\
= (1-p) \left( \frac{I + r_{x} X + r_{y} Y + r_{z} Z\}{2} \right) + p \left( \frac{I + r_{x} X - r_{y} Y - r_{z} Z \}{2} \right) \qquad \qquad \quad \\
= \frac{I + r_{x} X + (1-2p)r_{y} Y + (1-2p)r_{z} Z\}{2} \qquad \qquad \qquad \qquad \qquad \qquad \quad \\
\end{split}
\end{equation}
$$  

The bit-flip channel has transformed two-qubit Bloch's sphere co-ordinates from 

$$
{ r_{x}, r_{y}, r_{z} } \to { r_{x}, (1-2p)r_{y}, (1-2p)r_{z} }
$$

The bit-flip error probability p increases with time and hence final state of qubit quantum system $ r_{x},0},0$.

#### 2) **Phase flip channel:**

#### 1) **Depolarizing channel:**

#### 1) **Amplitude-damping channel:**
