---
layout: "post"
title: "P7. Quantum Operations - Part III"
---

In this post, we shall look at few examples of quantum channels/operations such as bit-flip channel, phase-flip channel, etc.

#### 1) **Bit flip channel:**
The bit-flip channel is represented by Krauss operators $( \sqrt{1-p}I, \sqrt{p}X)$, where $p$ is bit-flip error probability. The bit-flip channel acting on density matrix $\rho$ transforms it to

$$
\begin{equation}
\begin{split}
\rho_{out} = \sum_{i=1}^{2} E_{i} \rho E_{i}^{+}  \quad  \quad \quad \quad  \\
= (1-p) \rho + p X \rho X^{+}  \\
= (1-p) \rho + p X \rho X \quad  \\
\end{split}
\end{equation}
$$  

The system stays in the same state $\rho$ with probability (1-p) and flips to $X \rho X$ with probability p. 

Let us consider effect of bit-flip channel on general qubit Bloch sphere $\rho = \frac{I + r_{x} X + r_{y} Y + r_{z} Z}{2}$. The compact notation for qubit Bloch sphere is $(r_{x},r_{y},r_{z})$. 

$$
\begin{equation}
\begin{split}
\rho_{out} = (1-p) \left(\frac{I + r_{x} X + r_{y} Y + r_{z} Z}{2} \right) + p X \left(\frac{I + r_{x} X + r_{y} Y + r_{z} Z}{2} \right) X \qquad \qquad \quad  \\
= (1-p) \left(\frac{I + r_{x} X + r_{y} Y + r_{z} Z}{2} \right) + p \left(\frac{XX + r_{x} XXX + r_{y} XYX + r_{z} XZX}{2} \right) \quad \quad  \\
= (1-p) \left(\frac{I + r_{x} X + r_{y} Y + r_{z} Z}{2} \right) + p \left(\frac{I + r_{x} X - r_{y} Y - r_{z} Z}{2} \right) \qquad \qquad \qquad \\
= \left(\frac{I + r_{x} X + (1-2p)r_{y} Y + (1-2p)r_{z} Z}{2} \right) \qquad \qquad \qquad \qquad \qquad \qquad \quad \quad \\
\end{split}
\end{equation}
$$  

The bit-flip channel has transformed qubit Bloch's sphere co-ordinates from 

$$
\left( r_{x}, r_{y}, r_{z} \right) \to \left( r_{x}, (1-2p)r_{y}, (1-2p)r_{z} \right)
$$

The bit-flip error probability p increases from (0->1/2) with time and hence final state of qubit would be $(r_{x},0,0)$. All the coordiates disappear except $r_{x}$. The geometrical representation of bit-flip channel is depicted below. 

#### 2) **Phase flip channel:**
The phase-flip channel is represented by Krauss operators $( \sqrt{1-p}I, \sqrt{p}Z)$, where $p$ is phase-flip error probability. The phase-flip channel acting on density matrix $\rho$ transforms it to

$$
\begin{equation}
\begin{split}
\rho_{out} = \sum_{i=1}^{2} E_{i} \rho E_{i}^{+}  \quad  \quad \quad \quad  \\
= (1-p) \rho + p Z \rho Z^{+}  \\
= (1-p) \rho + p Z \rho Z \quad  \\
\end{split}
\end{equation}
$$  

The system stays in the same state $\rho$ with probability (1-p) and flips to $Z \rho Z$ with probability p.

Following similar argument as bit-flip channel, the phase-flip channel would transfor qubit Bloch's sphere co-ordinates as given below,

$$
\left( r_{x}, r_{y}, r_{z} \right) \to \left( (1-2p)r_{x}, (1-2p)r_{y}, r_{z} \right)
$$

The final state of qubit would be $(0, 0, r_{z})$. All the coordiates disappear except $r_{z}$. The geometrical representation of bit-flip channel is depicted below.

#### 1) **Depolarizing channel:**
The depolarizing channel is represented by Krauss operators $( \sqrt{1-3p/4}I, \sqrt{p/4}X, \sqrt{p/4}Y, \sqrt{p/4}Z)$, where $p$ is phase-flip error probability. The depolarizign channel acting on density matrix $\rho$ transforms it to

#### 1) **Amplitude-damping channel:**
