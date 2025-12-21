---
layout: "post"
title: "P10. Channel Capacity Part-II"
---

In this blog post, we shall look at a fading propagation channel capacity. The channel is assumed to be changing for every use of channel. If propagation channel is changing every use, then the channel capacity is also changing for every use. We must in this case compute the expected channel capacity.

Let us consider wireless MIMO system model mentioned in the previous post. The expected capacity of changing propagation channel is given as,

$$
\begin{equation}
\begin{split}
C
&= \underset{Q≥0,Tr(Q)=P}{max} E_{H}\left ( log\left( det(I_N + HQH') \right) \right) \\
\end{split}
\end{equation}
$$

where, the expectation is w.r.t to $H$, the input symbols $x$ is a circularly symmetric complex gaussian random vector with zero mean and covariance $Q=E(xx')$. The total transmit power is constrained to atmost $P$, (i.e) $Tr(Q) = E(x’x) = P$.

How to prove below maximation with respect to input distribution? 
The channel capacity is achieved for circularly symmetric complex gaussian input symbol $x$ with zero mean and covariance $Q=E(xx')=(P/M)I_M$. The channel capacity is given by,

$$
\begin{equation}
\begin{split}
C
&= E_{H}\left ( log\left( det \left( I_N + \frac{P}{M}HH' \right ) \right) \right) \\
\end{split}
\end{equation}
$$

\underline{Special cases}:

1) For a sufficiently large number of transmit antenna (i.e., $M\to \infty$): The expression $(HH')/M \to I_N$ as $M \to \infty$. Therefore, the above capacity expression becomes,

$$
\begin{equation}
\begin{split}
C
&= E_{H}⁡ \left ( log(det(I_N+P×I_N)) \right ) \\
\end{split}
\end{equation}
$$

The expectation can be removed since it does not depend on H anymore. Therefore,

$$
\begin{equation}
\begin{split}
C
&= log \left ( det \left ( I_N+P×I_N \right ) \right ) \\
&= log \left (1+P \right )^N \\
&= N×log \left (1+P \right )
\end{split}
\end{equation}
$$

The channel capacity increases linearly with number of receive antenna $N$.

2) For a sufficiently large number of received antenna (i.e., $N\to \infty$): The expression $(H'H)/N \to I_N$ as $N \to \infty$. Can the capacity expression be simplified?

3) How does capacity behaves when number of receive and transmit antenna are equal, i.e., $N=M$.
