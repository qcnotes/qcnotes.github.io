---
layout: "post"
title: "P5. Quantum Operations - Part I"
---
We had looked at two quantum transformations such as closed system unitary evolution and measurement so far in the previous blog post. Let us evaluate if these two transformations final state satisfies positivity and trace one conditions of quantum state postulate one.

#### 1. Closed system unitary evolution: 
It is a linear map from set of density operators to another set of density operator.

$$
\begin{equation}
\begin{split}
\mathcal{U}: \mathcal{S}(H) \rightarrow \mathcal{S}(H) \quad \\
\rho \rightarrow U \rho U^{+} \quad \\
\end{split}
\end{equation}
$$  

The evolution preserves positivity, and trace one properties of final state $U \rho U^{+}$. The trace of final state is

$$
Tr\{ U \rho U^{+} \} = Tr\{U^{+} U \rho \} = Tr\{\rho \} = 1
$$

Since $\rho$ is positive semi-definite, it can be factored as below to prove positivity of final state.

$$
U \rho U^{+} = (U \sqrt\rho) (\sqrt\rho U^{+}) \geqslant 0 
$$

#### 2.Measurement:  
It is another linear map from from set of density operators to another set of density operator.

$$
\begin{equation}
\begin{split}
\mathcal{M}: \mathcal{S}(H) \rightarrow \mathcal{S}(H) \quad \quad \quad \\
\rho \rightarrow \sum_{i=1}^{d} M_{i} \rho M_{i}^{+} \quad \\
\end{split}
\end{equation}
$$  

The measuremnt also preserves positivity, and trace one properties of final state $\sum_{i=1}^{d} M_{i} \rho M_{i}^{+}$. The trace of final state is

$$
Tr\{ \sum_{i=1}^{d} M_{i} \rho M_{i}^{+} \} = Tr\{ \sum_{i=1}^{d} M_{i}^{+} M_{i} \rho  \} = Tr\{\rho \} = 1
$$

Since $\rho$ is positive semi-definite, it can be factored as below to prove positivity of final state.

$$
\sum_{i=1}^{d} M_{i} \rho M_{i}^{+} = \sum_{i=1}^{d} (M_{i} \sqrt\rho) (\sqrt\rho M_{i}^{+}) \geqslant 0 
$$

Both closed system unitary evolution and measurement preserves positivity and trace one properties of quantum system. Are these the only quantum transformations possible? Are there any other quantum transformations that need to be looked at? We have overlooked another important quantum system (i.e) open quantum system. How does open quantum system that interacts with its surrounding environment evolve? Does open quantum system evolve unitarily? 

All the quantum transformations that exist should be a linear map from density operator to density operator 

$$
\begin{equation}
\begin{split}
\mathcal{E}: \mathcal{S}(H) \rightarrow \mathcal{S}(H) \\
\rho \rightarrow \mathcal{E}(\rho) \\
\end{split}
\end{equation}
$$  

preserving trace $Tr(\mathcal{E}(\rho)) = 1$ and positivity $\mathcal{E}(\rho) \geqslant 0 $. The general quantum transformation should satisfy complete positivity in addition to positivity which we shall look into in the later post.


