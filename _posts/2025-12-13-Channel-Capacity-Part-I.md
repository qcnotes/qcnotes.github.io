---
layout: "post"
title: "P9. Channel Capacity Part-I"
---
In this post, we shall look at the deterministic channel use case where both the transmitter and receiver have a full knowledge about it. The fading propagation channel use case will be explained in the subsequent blog post.

Let us consider a MIMO wireless system with $M$ transmit antenna and $N$ receive antenna.  The transmitter sends complex symbol vector $x \in C^{M}$ through its $M$ transmit antenna, and after propagation through the wireless channel $H \in C^{N,M}$, the receiver receives $y \in C^{N}$ complex vector through its $N$ receive antenna as,

$$
y = Hx + z
$$

where, $z \sim NC(0,I)$ is circularly symmetric complex gaussian random vector with zero mean and identity covariance. The total transmit power is constrained to $= P$, (i.e) $Tr(E(xx’)) = Tr(Q) = E(x’x) = P$. The propagation channel matrix $H \sim NC(0,I)$ is also a circularly symmetric complex gaussian random matrix with zero mean and identity covariance.

What is the capacity of a MIMO wireless system with a deterministic channel matrix H, where both the transmitter and receiver have complete knowledge of the matrix?

Consider the capacity expression that maximizes the mutual information between channel input and output for all input distribution $f(x)$ with positive definite covariance matrix $Q \ge 0$ and $Tr(Q)=P$ as,

$$
\begin{equation}
\begin{split}
C 
&= \underset{f(X),Q≥0,Tr(Q)=P}{max}I(X;Y) \\
&= \underset{f(X),Q≥0,Tr(Q)=P}{max} \left ( H(Y)-H(Y/X) \right )\\
&= \underset{f(X),Q≥0,Tr(Q)=P}{max} \left ( H(Y)-H(Z) \right )
\end{split}
\end{equation}
$$

The maximization of right expression is equivalent to maximization of entropy of $Y$ since entropy of complex gaussian noise vector $Z$ is fixed for a given noise covariance matrix $I$.

$$
\begin{equation}
\begin{split}
C 
&= \underset{f(X),Q≥0,Tr(Q)=P}{max} \left ( H(Y)-log(det(\pi e I_{N} )) \right )
\end{split}
\end{equation}
$$

We know that circularly symmetric gaussian random vector is entropy maximizer. Therefore, $Y$ must be circularly symmetric gaussian random vector to maximize the entropy and in turn the capacity. For $y$ to be circularly symmetric complex gaussian vector, the transmitted symbol vector $x$ must be circularly symmetric gaussian random vector with covariance matrix $Q$ satisfying $Tr(E(xx’)) = Tr(Q) = P$. Then the covariance matrix of received vector y is given as

$$
Q_y=E(yy')=I_N + HQH'.
$$

Therefore the capacity expression becomes,

$$
\begin{equation}
\begin{split}
C 
&= \underset{Q≥0,Tr(Q)=P}{max} \left ( log( det(\pi e (I_N + HQH')) ) - log( det(\pi e I_{N}) ) \right ) \\
&= \underset{Q≥0,Tr(Q)=P}{max} \left ( log\left( \frac{ det(\pi e (I_N + HQH')) }{det(\pi e I_{N})} \right) \right ) \\
&= \underset{Q≥0,Tr(Q)=P}{max} \left ( log\left( det( (I_N + HQH')) \right) \right) \\
\end{split}
\end{equation}
$$

We still must maximize over all the circularly symmetric complex gaussian random vector $x$ with covariance matrix $Q$ satisfying power constraint $Tr(Q)=P$.

To simplify further, let us consider singular value decomposition of channel matrix $H=U \Lambda V'$, where $U$ is eigen vectors of $HH’$, $V$ is eigen vector of $H’H$ and $\Lambda$ is a square root of eigen value of $HH’$ or $H’H$ matrix. Substituting the SVD of $H$ in the capacity expression and using $det(I+AB)=det(I+BA)$ equivalence, we get

$$
\begin{equation}
\begin{split}
C 
&= \underset{Q≥0,Tr(Q)=P}{max} \left ( log\left( det( (I_N + UΛV'QVΛU')) \right) \right) \\
&= \underset{Q≥0,Tr(Q)=P}{max} \left ( log\left( det( (I_M + ΛV'QVΛ)) \right) \right) \\
\end{split}
\end{equation}
$$

Let $\widetilde{Q}=V'QV$ and the unitary matrix V multiplication does not change the statistics of $\widetilde{Q}$ matrix, and $Tr(\widetilde{Q})=Tr(V'QV)=Tr(Q)$. 

Therefore, 

$$
\begin{equation}
\begin{split}
C 
&= \underset{\widetilde{Q}≥0,Tr(\widetilde{Q})=P}{max} \left ( log\left( det( (I_M + Λ\widetilde{Q}Λ)) \right) \right) \\
\end{split}
\end{equation}
$$

The determinant inequality $det⁡(\widetilde{Q})≤\prod_{i=1}^{M}\widetilde{Q}_{ii}$  is satisfied with equality if and only if $\widetilde{Q}$ is diagonal matrix, and it can be used to maximize the capacity expression as

$$
\begin{equation}
\begin{split}
C 
&= \underset{diag(\widetilde{Q})≥0,Tr(\widetilde{Q})=P}{max} \left ( log \left( \prod_{i=1}^{M} \left( 1+\widetilde{Q}_{ii} \lambda_i^2 \right) \right) \right ) \\
&= \underset{diag(\widetilde{Q})≥0,Tr(\widetilde{Q})=P}{max} \left ( \sum_{i=1}^{M} log\left( 1+\widetilde{Q}_{ii} \lambda_i^2 \right) \right ) \\
\end{split}
\end{equation}
$$

We still must maximize over all the circularly symmetric complex gaussian random vector $x$ with diagonal covariance matrix $diag(\widetilde{Q}_{ii})$ satisfying the constraint $Tr(\widetilde{Q})=P$. The log is concave function, and convex optimization can be used to find $\widetilde{Q}$.

Let us consider Lagrange multiplier of capacity expression with constraint,

$$
\begin{equation}
\begin{split}
\bigtriangledown = \sum_{i=1}^{M} log\left( 1 + \widetilde{Q}_{ii} \lambda_i^2 \right) - \mu\left( \sum_{i=1}^{M} \widetilde{Q}_{ii} -P \right)
\end{split}
\end{equation}
$$

Differentiating and simplifying,

$$
\begin{equation}
\begin{split}
\frac{d\bigtriangleup}{d\widetilde{Q}_{jj}} = \frac{\lambda_j^2}{1+\widetilde{Q}_{jj} \lambda_j^2}-\mu=0 \\
\widetilde{Q}_{jj}  = \frac{1}{\mu} - \frac{1}{\lambda_j^2} \ge 0 \\
\widetilde{Q}_{jj}  = \left (\frac{1}{\mu} - \frac{1}{\lambda_j^2} \right )^{+} \\
\end{split}
\end{equation}
$$

Substituting in constraint expression,

$$
\begin{equation}
\begin{split}
\sum_{j=1}^{M} \widetilde{Q}_{jj}  = \sum_{j=1}^{M} \left (\frac{1}{\mu} - \frac{1}{\lambda_j^2} \right )^{+} = P \\
\end{split}
\end{equation}
$$

$$
\begin{equation}
\begin{split}
\frac{1}{\mu} = \frac{P}{M} + \frac{1}{M} \sum_{j=1}^{M}  \frac{1}{\lambda_j^2}; & \text{and} & \widetilde{Q}_{jj}  = \left (\frac{1}{\mu} - \frac{1}{\lambda_j^2} \right )^{+} \\
\end{split}
\end{equation}
$$

This is well known water filling algorithm to allocate power to transmit antenna. The larger eigen values $\lambda_j$ indicates good channel condition (i.e) smaller $1/\lambda_j^{2}$ value is subtracted from  $1/μ$, and hence larger power is allocated to it. Similarly, smaller eigen values $\lambda_j$ indicates bad channel condition i.e larger $1/\lambda_j^{2}$ value is subtracted from  $1/μ$, and hence smaller power is allocated to it.

![water filling algorithm](/assets/images/channel_capacity/water_filling_algo.jpg){: width="50%" .align-center}

The maximum capacity with power allocation according to water filling (substitute $\widetilde{Q}_{jj}$ in Eq.8),

$$
\begin{equation}
\begin{split}
C 
&=  \sum_{i=1}^{M} log\left( \frac{\lambda_i^2}{\mu} \right) \\
\end{split}
\end{equation}
$$

Reference:
- E. Telatar, “Capacity of multi-antenna Gaussian channels,” Europ. Trans. Telecommun., ETT, vol. 10, no. 6, pp. 585–596, Nov. 1999.
