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

Let us consider effect of bit-flip channel on general qubit Bloch sphere $\rho = \frac{I + r_{x} X + r_{y} Y + r_{z} Z}{2}$. 

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

The compact notation for qubit Bloch sphere is $(r_{x},r_{y},r_{z})$. The bit-flip channel has transformed qubit Bloch's sphere co-ordinates from 

$$
\left( r_{x}, r_{y}, r_{z} \right) \to \left( r_{x}, (1-2p)r_{y}, (1-2p)r_{z} \right)
$$

The bit-flip error probability p increases (0->0.5) with time and hence final state of qubit would be $(r_{x},0,0)$. All the coordiates disappear except X-axis coordinate $r_{x}$. The convex combination of $\|+\rangle ~ and ~ \|-\rangle$ states which represents X-axis are eigen states of Pauli matrix X and hence it remained unaffected by bit-flip channel. The geometrical representation of bit-flip channel is depicted below. 

![bit-flip channel](/assets/images/quantum_operations_examples/bit_flip_channel.jpg){: width="50%"}

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

Following similar argument as bit-flip channel, the phase-flip channel would transform qubit Bloch's sphere co-ordinates as given below,

$$
\left( r_{x}, r_{y}, r_{z} \right) \to \left( (1-2p)r_{x}, (1-2p)r_{y}, r_{z} \right)
$$

The final state of qubit would be $(0, 0, r_{z})$. All the coordiates disappear except Z-axis $r_{z}$. The convex combination of $\|0\rangle ~ and ~ \|1\rangle$ states which represents Z-axis are eigen states of Pauli matrix Z and hence it remained unaffected by bit-flip channel. The geometrical representation of phase-flip channel is depicted below.

![phase-flip channel](/assets/images/quantum_operations_examples/phase_flip_channel.jpg){: width="50%"}

#### 3) **Depolarizing channel:**
The depolarizing channel is represented by Krauss operators $( \sqrt{1-3p/4}I, \sqrt{p/4}X, \sqrt{p/4}Y, \sqrt{p/4}Z)$, where $p$ is error probability. The depolarizign channel acting on density matrix $\rho$ transforms it to

$$
\begin{equation}
\begin{split}
\rho_{out} = \sum_{i=1}^{2} E_{i} \rho E_{i}^{+}  \qquad  \qquad \qquad \qquad \qquad \qquad \qquad \qquad \qquad \quad \\
= (1-3p/4) \rho + (p/4) X \rho X + (p/4) Y \rho Y + (p/4) Z \rho Z  \qquad \quad \\
\end{split}
\end{equation}
$$  

The phase-flip channel would transform qubit Bloch's sphere co-ordinates as given below,

$$
\left( r_{x}, r_{y}, r_{z} \right) \to \left( (1-p)r_{x}, (1-p)r_{y}, (1-p)r_{z} \right)
$$

All the coordiates disappear converging to center of Bloch sphere as the p increases (0->1) with time. This center of Block sphere is maximally entangled state. The geometrical representation of depolarizing channel channel is depicted below.

![depolarizting channel](/assets/images/quantum_operations_examples/depolarizing_channel.jpg){: width="50%"}

#### 4) **Amplitude-damping channel:**

![amplitude_damping channel](/assets/images/quantum_operations_examples/amplitude_damping_channel.jpg){: width="50%"} 
