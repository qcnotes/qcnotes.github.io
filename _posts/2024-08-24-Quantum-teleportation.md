---
layout: post
title: "Quantum Teleportation New"
categories: misc
---

## Quantum Teleportation:  
The transfer protocal of an arbitrary quantum state from Alice to Bob is called Quantum teleportation. This protocol requires additional resource in the form of shared entangled Bell state and 2-bit classical communication between them.  

  
Let u assume Alice possess an arbitrary quantum state $|\psi\rangle = \alpha|0\rangle+\beta|1\rangle$ and wants to transfer it to Bob. Alice & Bob share Bell state $|\phi^+\rangle=(|00\rangle+|11\rangle)/\sqrt{2}$ and now they have been separated apart.  

The quantum teleportation circuit shown below transfers the quantum state $|\psi\rangle$ from Alice to Bob. Let us look into the mathematical details of quantum teleportation algorithm.  
<div align="center">  

![image](/assets/images/quantum_teleportation.jpeg)

</div>

### Composite state at position (1)  
$$ |A_1 A_2 B\rangle = |\psi\rangle \otimes |\phi^+\rangle $$  

$$|A_1 A_2 B\rangle  = \frac{\alpha}{\sqrt{2}}|000\rangle + \frac{\alpha}{\sqrt{2}}|011\rangle + \frac{\beta}{\sqrt{2}}|100\rangle + \frac{\beta}{\sqrt{2}}|111\rangle$$  

### Composite state at position (2)  
$$|A_1 A_2 B\rangle  = \frac{\alpha}{\sqrt{2}}|000\rangle + \frac{\alpha}{\sqrt{2}}|011\rangle + \frac{\beta}{\sqrt{2}}|110\rangle + \frac{\beta}{\sqrt{2}}|101\rangle$$  

### Composite state at position (3)  
$$|A_1 A_2 B\rangle  = \frac{\alpha}{2}|000\rangle + \frac{\alpha}{2}|100\rangle + \frac{\alpha}{2}|011\rangle + \frac{\alpha}{2}|111\rangle + \frac{\beta}{2}|010\rangle - \frac{\beta}{2}|110\rangle + \frac{\beta}{2}|001\rangle - \frac{\beta}{2}|101\rangle$$

$$= \frac{1}{2}|00\rangle (\alpha|0\rangle+\beta|1\rangle) + \frac{1}{2}|01\rangle (\alpha|1\rangle+\beta|0\rangle) + \frac{1}{2}|10\rangle (\alpha|0\rangle-\beta|1\rangle) + \frac{1}{2}|11\rangle (\alpha|1\rangle-\beta|0\rangle)$$  

### Composite state at position (4)  
The measurement outcome of two qubit of A are  

<div align="center">
  
A's measurement  | Measurement Probability  | B's state   
:--------------  | :----------------------  | :---------------------
$\|00\rangle$    |     $\frac{1}{4}$        | $(\alpha\|0\rangle+\beta\|1\rangle)$
$\|01\rangle$    |     $\frac{1}{4}$        | $(\alpha\|1\rangle+\beta\|0\rangle)$
$\|10\rangle$    |     $\frac{1}{4}$        | $(\alpha\|0\rangle-\beta\|1\rangle)$
$\|11\rangle$    |     $\frac{1}{4}$        | $(\alpha\|1\rangle-\beta\|0\rangle)$
</div>

### Composite state at position (5)  
Alice communicates its measurement outcome to Bob who inturn apply X and Z gate to its qbit to receive the intended state $|\psi\rangle = \alpha|0\rangle+\beta|1\rangle$ from Alice. 

