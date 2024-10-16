# DLQ-captures-the-complexity-of-learning-with-SGD
This project contains codes for the project: "On the Complexity of Learning Sparse Functions with Statistical and Gradient Queries" (https://arxiv.org/abs/2407.05622)

Consider learning sparse functions on the boolean hypercube $\boldsymbol{x}\in \\{-1,+1\\}^d$, i.e. depends on a sparse support $\boldsymbol{z}$ of $P \ll d$ coordinates. The function is given by the link function $\mu_{y \mid \boldsymbol{z}}: \mathbb{R}^P \to \mathbb{R}$. Then for any loss function $\ell: \mathbb{R} \times \mathcal{Y} \to \mathbb{R}$, our paper charcterizes the **"leap complexity"** exponent denoted by $\mathsf{Leap}_{\ell} $. A general conjectural picture is that $\ell$-SGD with the loss $\ell$ on a two-layer neural of width $M=O(d)$ (that is $O(d)$ parameters) learns the function in the number of iterations (also corresponds to the number of samples): 

$d^{ \text{min}\\{\mathsf{Leap}_{\ell}-1, 1\\} }$
 
See the discussion in the paper as to how this relates to the lower bound complexity on the overall runtime given by Differiatale Learning Queries (DLQ). The paper proves this theorem for the case of $\mathsf{Leap}_{\ell}=1$ (e.g. there is a staircase structure for the detectable sets with the sepcified loss). We verify this by taking an instance:
1. For $\ell_1(u,y)=|u-y|$ the absolute value loss and an anpther synthetic loss $\ell_3(u,y)=(u-y)^2+|u-y|^3$, we have the leap exponent of one, but for the squared loss $\ell_2(u,y)=(u-y)^2$, we have the leap of three. Run `ell1.ipynb`, `ell2.ipynb` and `ell3.ipynb` to generate the plots.
2. For higher leaps, we consider the 3-order parity for which for any $\ell \in \\{ \ell_1, \ell_2, \ell_3\\}$, we have that $\mathsf{Leap}_\ell=3$ and the $\ell$-SGD iteration complexity is $\propto d^2$ for all the losses. Execute `ell1_parity.ipynb`, `ell2_parity.ipynb` and `ell3_parity.ipynb` to generate the plots.
