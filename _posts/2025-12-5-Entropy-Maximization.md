---
layout: "post"
title: "P8. Entropy Maximization"
---

**Theorem:**

Let us consider a complex random vector $x \in C^{n}$ with zero mean and satisfies $Q = \mathbf{E}(xx^{H})$. Then, the entropy of $x$ satisfies $H_{p}(x) \leq log(det(\pi e Q))$ with equality if and only if x is a circularly symmetric complex Gaussian random vector with zero mean and covariance Q.

The expression $log(det(\pi e Q))$ is capacity of circularly symmetric complex Gaussian random vector with probability density function $\gamma_Q(x)=\frac{1}{det(\pi Q)}e^{-x \inv(Q) x^{H}}

**Proof:**
Let us consider the difference between cross entropy $H(p,\gamma_Q)$ and $H(p)$ or minor variation of Kullback-Leibler divergence expression

$$
\begin{equation}
\begin{split}
-D(p||\gamma_Q(x))= -\int p(x)log\left(\frac{p(x)}{\gamma_Q(x)}\right)dx = H(p) - H(\gamma_Q(x)) \\
= \int p(x)log\left(\frac{\gamma_Q(x)}{p(x)}\right)dx \qquad \qquad \qquad \qquad \quad \\
\end{split}
\end{equation}
$$  
