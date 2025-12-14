---
layout: "post"
title: "P9. Channel Capacity Part-I"
---

Let us consider a MIMO wireless system with $M$ transmit antenna and $N$ receive antenna.  The transmitter sends complex symbol vector $x \in C_{M}$ through its $M$ transmit antenna, and after propagation through the wireless channel matrix $H ~ NC(0,1)$, the receiver receives $y \in C_{N}$ complex vector through its $N$ receive antenna as,

$$
y = Hx + z
$$

where, $z ~ NC(0,1)$ is circularly symmetric complex gaussian random vector with zero mean and identity covariance. The transmitter total transmit power is restricted to less than P, (i.e) achieved with Tr(E(xx’)) = Tr(Q) = E(x’x) = P. The channel matrix H is also a circularly symmetric complex gaussian random vector with zero mean and identity covariance.
In this post, we shall look at the deterministic channel matrix use case which both the transmitter and receiver has a full knowledge about. The fading propagation channel use case will be explained in the subsequent blog post.

What would be the capacity of MIMO wireless system with deterministic channel matrix H?
C=⏟max┬█(p(x)  with@Q≥0,Tr(Q)=P)⁡〖I(X;Y)〗=⏟max┬█(p(x)  with@Q≥0,Tr(Q)=P)⁡{H(Y)-H(Y/X)}
=⏟max┬█(p(x)  with@Q≥0,Tr(Q)=P)⁡{H(Y)-H(Z)}
The maximization of right expression is equivalent to maximization of entropy of Y since entropy of complex gaussian noise vector is fixed for a given noise covariance matrix I. 
=⏟max┬█(p(x)  with@Q≥0,Tr(Q)=P)⁡{H(Y)-log(det(πeI_N ))}
We know that circularly symmetric gaussian random vector is entropy maximizer. Therefore, Y must be circularly symmetric gaussian random vector to maximize the entropy and in turn the capacity. For Y to be circularly symmetric complex gaussian, the transmitted symbol vector x must be circularly symmetric gaussian random vector with covariance matrix Q satisfying Tr(E(xx’)) = E(Q) = P. Then the covariance matrix of received vector y is 
Q_y=E(yy^' )=HQH^'+I_r.
Therefor the capacity expression becomes,
=⏟max┬(Q≥0,Tr(Q)=P)⁡{log(det(πe(I_N+HQH^' )))-log(det(πeI_N ))}
=⏟max┬(Q≥0,Tr(Q)=P)⁡{log(det(πe(I_N+HQH^' ))/det(πeI_N ) )}=⏟max┬(Q≥0,Tr(Q)=P)⁡{log(det(I_N+HQH^' ))}

We still must maximize over all the circularly symmetric complex gaussian random vector x with covariance matrix Q satisfying power constraint Tr(Q)=P.
To simplify further, let us consider singular value decomposition of channel matrix H=UAV ‘, where U is eigen vectors of HH’, V is eigen vector of H’H and Lamba is square root of eigen value of HH’ or H’H matrix. Substituting the SVD of H in the capacity expression and using det(I+AB)=det(I+BA) equivalence, we get 
C=⏟max┬(Q≥0,Tr(Q)=P)⁡{log(det(I_N+UΛV'QVΛU^' ))}=⏟max┬(Q≥0,Tr(Q)=P)⁡{log(det(I_M+ΛV'QVΛ))}
Let Q ̃=V'QV and the unitary matrix V multiplication does not change the statistics of Q matrix, and Tr(Q ̃ )=Tr(V'QV)=Tr(Q). Therefore, 
C=⏟max┬(Q ̃≥0,Tr(Q ̃ )=P)⁡{log(det(I_M+ΛQ ̃Λ))}
The determinant inequality “det⁡(Q ̃ )≤∏_(i=1)^M▒Q ̃_ii  is satisfied with equality if and only if Q ̃ is diagonal matrix” can be used to simplify maximize the capacity expression as
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
