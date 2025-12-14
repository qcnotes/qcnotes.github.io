---
layout: "post"
title: "P9. Channel Capacity Part-I"
---
In this post, we shall look at the deterministic channel matrix use case where both the transmitter and receiver have a full knowledge about it. The fading propagation channel use case will be explained in the subsequent blog post.

Let us consider a MIMO wireless system with $M$ transmit antenna and $N$ receive antenna.  The transmitter sends complex symbol vector $x \in C_{M}$ through its $M$ transmit antenna, and after propagation through the wireless channel matrix $H \in C_{N,M}$, the receiver receives $y \in C_{N}$ complex vector through its $N$ receive antenna as,

$$
y = Hx + z
$$

where, $z \sim NC(0,I)$ is circularly symmetric complex gaussian random vector with zero mean and identity covariance. The total transmitter total transmit power is constrained to $\le P$, (i.e) $Tr(E(xx’)) = Tr(Q) = E(x’x) = P$. The channel matrix $H \sim NC(0,I)$ is also a circularly symmetric complex gaussian random matrix with zero mean and identity covariance.

What is the capacity of a MIMO wireless system with a deterministic channel matrix H, where both the transmitter and receiver have complete knowledge of the matrix?

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
&= \underset{Q≥0,Tr(Q)=P}{max} \left ( log\left( det( (I_N + ΛV'QVΛ)) \right) \right) \\
\end{split}
\end{equation}
$$

Let $\widetilde{Q}=V'QV$ and the unitary matrix V multiplication does not change the statistics of $\widetilde{Q}$ matrix, and $Tr($\widetilde{Q})=Tr(V'QV)=Tr(Q)$. 

Therefore, 

$$
\begin{equation}
\begin{split}
C 
&= \underset{\widetilde{Q}≥0,Tr(\widetilde{Q})=P}{max} \left ( log\left( det( (I_N + Λ\widetilde{Q}Λ)) \right) \right) \\
\end{split}
\end{equation}
$$

The determinant inequality $det⁡(\widetilde{Q})≤∏_(i=1)^M▒Q ̃_ii$  is satisfied with equality if and only if $\widetilde{Q}$ is diagonal matrix can be used to simplify maximize the capacity expression as

C=⏟max┬(Q ̃≥0,Tr(Q ̃ )=P & diag)⁡{log(det(I_M+Q ̃_ii Λ_ii^2 ))}
C=⏟max┬(Q ̃≥0,Tr(Q ̃ )=P & diag)⁡{log(∏_(i=1)^M▒(1+Q ̃_ii Λ_i^2 ) )}==⏟max┬(Q ̃≥0,Tr(Q ̃ )=P & diag)⁡{∑_(i=1)^M▒log (1+Q ̃_ii Λ_i^2 )}

We still must maximize over all the circularly symmetric complex gaussian random vector x with diagonal covariance matrix diag(Q ̃_ii) satisfying the constraint Tr(Q ̃)= ∑▒Q ̃_ii =P. The log is concave function, and convex optimization can be used to find Q ̃.
Let us consider Lagrange multiplier of capacity expression with constraint,
∇ =∑_(i=1)^M▒log (1+Q ̃_ii Λ_i^2 )-μ' (∑_i^M▒Q ̃_ii -P)
Differentiating and simplifying,
d∇/(dQ ̃_jj )=(Λ_j^2)/(1+Q ̃_jj Λ_j^2 )-μ^'=0
Q ̃_jj=1/μ^' -1/(Λ_j^2 )≥0
Q ̃_jj=(1/μ^' -1/(Λ_j^2 ))^+ just a representation of positive quantity
Substituting in constraint expression,
∑_i^M▒Q ̃_ii =∑_(i=1)^M▒(1/μ^' -1/(Λ_j^2 ))^+ =P
1/μ^' =P/M+1/M ∑_(i=1)^M▒1/(Λ_j^2 )  and Q ̃_jj=(1/μ^' -1/(Λ_j^2 ))^+
This is well known water filling algorithm to allocate power to the transmit antenna. The larger the eigen values of channel matrix indicates good channel Λ_j^2   (i.e)(smaller value 1/(Λ_j^2 )  is subtracted from  1/μ^' ), and hence larger the power is allocated to that particular antenna. Similarly, the smaller the eigen values of channel matrix indicates bad channel Λ_k^2 i.e (larger value 1/(Λ_j^2 )  is subtracted from  1/μ^' ), and hence smaller power is allocated to that particular antenna.
