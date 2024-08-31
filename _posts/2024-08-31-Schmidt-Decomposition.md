---
layout: post
title: "P3. Schmidt Decomposition"
categories: misc
---

Let $\|\psi\rangle_{AB}$ be a pure state of composite system A and B. The pure state $\|\psi\rangle_{AB}$ can be decomposed into  

$$ |\psi\rangle_{AB} = \sum_{i=1}^{d} \lambda_{i} |i\rangle_{A} |i\rangle_{B} $$  

where, d is Schmidt rank, $\lambda_{i}$ are Schmidt coefficients, $\|i\rangle_{A}$ and $\|i\rangle_{B}$ are Schmidt basis.

## Proof:

Let $\{ \|j\rangle_{A} \}$ be any $n$ orthonormal basis of system A and and $\{ \|k\rangle_{B} \}$ be any $m$ orthonormal basis system B. Then, any pure state $\|\psi\rangle_{AB}$ of composite system can be expressed interms of orthonormal basis of A and B as

$$ |\psi\rangle_{AB} = \sum_{j,k} \alpha_{j,k} |j\rangle_{A} |k\rangle_{B} $$  

where, $\sum_{j=1,k=1}^{n,m} \|\alpha_{j,k}\|^{2}=1$.

Let us arrange $\alpha_{j,k}$ in a matrix form and decompose it using Singular Value Decomposition (SVD) as

$$
\alpha = 
\begin{bmatrix}
    \alpha_{1,1}       & \alpha_{1,2} & \dots & \alpha_{1,m} \\
    \alpha_{2,1}       & \alpha_{2,2} & \dots & \alpha_{2,m} \\
     \vdots & \vdots & \ddots & \vdots \\
    \alpha_{n,1}       & \alpha_{n,2} & \dots & \alpha_{n,m}
\end{bmatrix}
= U \Lambda V^{+}=\sum_{i=1}^{d} \lambda_{i} u_{i}  v_{i}^{+}
$$

A particular values of matrix can be expression as $\alpha_{j,k} = \sum_{i=1}^{d} \lambda_{i} u_{j,i}  v_{k,i}^{*}$ and substituting this values in Eq. (2)

$$
\begin{equation}
\begin{split}
|\psi\rangle_{AB} = \sum_{j,k} \{ \sum_{i=1}^{d} \lambda_{i} u_{j,i}  v_{k,i}^{*} \} |j\rangle_{A} |k\rangle_{B} \qquad  \\
 =  \sum_{i=1}^{d} \lambda_{i}  \{ \sum_{j} u_{j,i} |j\rangle_{A} \} \{\sum_{k} v_{k,i}^{*} |k\rangle_{B} \} \\
 = \sum_{i=1}^{d} \lambda_{i} |i\rangle_{A} |i\rangle_{B} \qquad \qquad \qquad \quad \\
\end{split}
\end{equation}
$$  

*Note: I don't understand the reason for arranging $\alpha_{j,k}$ it matrix form. This matrix arrangement has introduced artificial constrain on the dimension of composite system.
