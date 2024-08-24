---
layout: post
title: "Quantum Teleportation"
categories: misc
---

The transfer protocal of an arbitrary quantum state from Alice to Bob is called Quantum teleportation. This protocol requires additional resource in the form of shared entangled Bell state and 2-bit classical communication between them.  

Let us assume Alice possess an arbitrary quantum state $\|\psi\rangle = \alpha\|0\rangle+\beta\|1\rangle$ and wants to transfer it to Bob. Alice & Bob share a entangled Bell state $\|\phi^+\rangle=(\|00\rangle+\|11\rangle)/\sqrt{2}$ and now they have been separated apart.  

The quantum teleportation circuit shown below transfers the quantum state $\|\psi\rangle$ from Alice to Bob. Let us look into the mathematical details of quantum teleportation algorithm.  

![image](/assets/images/quantum_teleportation.jpeg)

### Composite state at position (1)
The state at position (1) is tensor product three input qubits $\|\psi\rangle \text{and} \|\phi^+\rangle$  

$$ |A_1 A_2 B\rangle = |\psi\rangle \otimes |\phi^+\rangle \qquad \qquad \qquad \qquad \qquad \qquad \qquad \qquad \quad $$  

$$ = \frac{\alpha}{\sqrt{2}}|000\rangle + \frac{\alpha}{\sqrt{2}}|011\rangle + \frac{\beta}{\sqrt{2}}|100\rangle + \frac{\beta}{\sqrt{2}}|111\rangle$$  

### Composite state at position (2)  
Alice applies CNOT gate to two of its input qubits and the state at position (2) is given as  

$$|A_1 A_2 B\rangle  = \frac{\alpha}{\sqrt{2}}|000\rangle + \frac{\alpha}{\sqrt{2}}|011\rangle + \frac{\beta}{\sqrt{2}}|110\rangle + \frac{\beta}{\sqrt{2}}|101\rangle$$  

### Composite state at position (3)  
Alice applies Hadamard gate to its first input qubits and the state at position (3) is given as  

$$|A_1 A_2 B\rangle  = \frac{\alpha}{2}|000\rangle + \frac{\alpha}{2}|100\rangle + \frac{\alpha}{2}|011\rangle + \frac{\alpha}{2}|111\rangle + \frac{\beta}{2}|010\rangle - \frac{\beta}{2}|110\rangle + \frac{\beta}{2}|001\rangle - \frac{\beta}{2}|101\rangle \qquad  \qquad \qquad \qquad  $$  

Collecting identical terms of first two qubits,

$$= \frac{1}{2}|00\rangle (\alpha|0\rangle+\beta|1\rangle) + \frac{1}{2}|01\rangle (\alpha|1\rangle+\beta|0\rangle) + \frac{1}{2}|10\rangle (\alpha|0\rangle-\beta|1\rangle) + \frac{1}{2}|11\rangle (\alpha|1\rangle-\beta|0\rangle)$$  

The above expression has four terms and first two qubits of Alice are in computation basis form. Alice can perform measurement in computation basis to collapse to one of the terms in the above expression. Though the Bob's qubit has collapsed and he still has knowledge of its state unless Alice communicates its measurement output to Bob. In that case, Bob is certain about it state and he can perform some quantum operation to receive $\|\psi\rangle$.

### Composite state at position (4)  
The measurement outcome of Alice qubit and corresponding Bob's states are  

Alice's measurement $(m_0,m_1)$  | Measurement Probability  | Bob's state   | Bob's Action to recover required state
:--------------  | :----------------------  | :--------------------- | :---------------------
$\|00\rangle$    |     $\frac{1}{4}$        | $(\alpha\|0\rangle+\beta\|1\rangle)$ | Nothing to be done
$\|01\rangle$    |     $\frac{1}{4}$        | $(\alpha\|1\rangle+\beta\|0\rangle)$ | Apply X gate
$\|10\rangle$    |     $\frac{1}{4}$        | $(\alpha\|0\rangle-\beta\|1\rangle)$ | Apply Z gate
$\|11\rangle$    |     $\frac{1}{4}$        | $(\alpha\|1\rangle-\beta\|0\rangle)$ | Apply X gate, and then Z gate


### Composite state at position (5)  
Alice communicates its measurement outcome $(m_0,m_1)$ to Bob who inturn apply X and Z gate to its qubit to recover the intended state $|\psi\rangle = \alpha|0\rangle+\beta|1\rangle$. 

