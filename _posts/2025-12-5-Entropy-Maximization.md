---
layout: "post"
title: "P8. Entropy Maximization"
---

#### **Theorem:**

Let us consider a complex random vector $x \in C^{n}$ with zero mean and satisfying $Q = \mathbf{E}(xx^{H}), (i.e) Q_{i,j} = \int x_i x_j^{H} p(x) dx $. Then, the entropy of $x$ satisfies $H_{p}(x) \leq log(det(\pi e Q))$ with equality if and only if x is a circularly symmetric complex Gaussian random vector with zero mean and covariance Q.

The expression $H_{\gamma_Q}(x)=log(det(\pi e Q))$ is the capacity of circularly symmetric complex Gaussian random vector with probability density function 

$$ 
\gamma_Q(x)=\frac{1}{det \left(\pi Q\right)} e^{-{x Q^{-1} x^{H}}}, \quad and \quad Q_{i,j} = \int x_i x_j^{H} \gamma_Q(x) dx
$$

#### 1) **Proof:**
Let us consider difference between entropy of x and circularly symmetric Gaussian randon vector,

$$
\begin{equation}
\begin{split}
H_{p}(x) - H_{\gamma_Q}(x)  
&= - \int p(x) log(p(x)) dx + \int \gamma_Q(x) log(\gamma_Q(x)) dx\\
\end{split}
\end{equation}
$$

Since $log(\gamma_Q(x))$ is linear combinations of $x_i x_j^{H}$, the expectation with respect to two probability functions are same, (i.e) $E_{p}\left(log(\gamma_Q(x))\right) = E_{\gamma_Q}\left(log(\gamma_Q(x))\right).$ 

Therefore, the above can be written as,

$$
\begin{equation}
\begin{split}
&= - \int p(x) log(p(x)) dx + \int p(x) log(\gamma_Q(x)) dx\\
&= \int p(x)log\left(\frac{\gamma_Q(x)}{p(x)}\right)dx \\
\end{split}
\end{equation}
$$

Using Jenson't inequality for concave function (since log is a concave function)

$$
\begin{equation}
\begin{split}
&\leq log\left(\int p(x)\frac{\gamma_Q(x)}{p(x)} dx \right) \\
&\leq 0 
\end{split}
\end{equation}
$$

Thus, the entropy of x satisfies required inequality

$$
\begin{equation}
\begin{split}
H_{p}(x) \leq H_{\gamma_Q}(x) \\
\end{split}
\end{equation}
$$

#### 2) **Alternate Proof:**
Let us consider Kullback-Leibler divergence expression (and using Eq.3)

$$
\begin{equation}
\begin{split}
-D(p||\gamma_Q) 
&= -\int p(x)log\left(\frac{p(x)}{\gamma_Q(x)}\right)dx 
&= H_{p}(x) - H_{\gamma_Q}(x) \\
&= \int p(x)log\left(\frac{\gamma_Q(x)}{p(x)}\right)dx  \\
\end{split}
\end{equation}
$$

Using the inequality log(x) <= (x-1)}

$$
\begin{equation}
\begin{split}
&\leq \int p(x) \left(\frac{\gamma_Q(x)}{p(x)}-1\right)dx  \\
&\leq \int \left(\gamma_Q(x) - p(x)\right) dx \\
H_{p}(x) - H_{\gamma_Q}(x) &\leq 0 \\
\end{split}
\end{equation}
$$

Thus, the entropy of x satisfies required inequality

$$
\begin{equation}
\begin{split}
H_{p}(x) \leq H_{\gamma_Q}(x) \\
\end{split}
\end{equation}
$$
