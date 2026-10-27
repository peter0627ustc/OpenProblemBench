# ORB-MATH-19: The Collatz (3n+1) conjecture, equivalently the nonvanishing of the arrival coefficients in Masetti's iterative functional equation

The source (G. Masetti, arXiv:2305.10117, 2023, math.GM preprint) reformulates the Collatz conjecture — every trajectory of the map sending an odd $n$ to $3n+1$ and an even $n$ to $n/2$ eventually reaches $1$ — as a coefficient-nonvanishing problem. For each starting value $k\ge 1$, the unique analytic solution $A_k$ of a linear iterative functional equation (with positive real weights $w_b, w_f$ satisfying $|w_b|+|w_f|<1$) has coefficients that encode the trajectory from $k$, and the conjecture becomes: the arrival coefficient $a_{k,1}=A'_k(0)$, which aggregates the weighted visits of the trajectory to the state $1$, is nonzero for every $k\ge 1$. The equivalence holds for positive weights, so the open core is exactly the Collatz conjecture itself, one of the most famous open problems in mathematics. It remains open: Tao proved that almost all orbits attain almost bounded values and computational verification now covers all starting values below $2^{71}$, but no proof or counterexample exists.

## Background

The Collatz map $\mathrm{Col}:\mathbb{N}\to\mathbb{N}$ sends an odd $n$ to $3n+1$ and an even $n$ to $n/2$. The Collatz conjecture (also called the $3n+1$ problem) asserts that for every starting value $k\ge 1$ the trajectory $d_{k,0}=k$, $d_{k,i}=\mathrm{Col}(d_{k,i-1})$ eventually reaches $1$ (Lagarias, 1985). It is one of the most notorious open problems in number theory: computational verification now covers all $k<2^{71}$ (Barina, 2020 and 2025), and Tao (2022) proved that almost all orbits, with respect to logarithmic density (a measure of the size of sets of positive integers in which each integer $n$ carries weight $1/n$), attain almost bounded values — but no proof or counterexample is known.

The source (Masetti, 2023) reformulates the conjecture through generating functions. A generating function of a sequence $(c_n)$ is the power series $\sum_n c_n x^n$ whose coefficients store the sequence. Masetti defines the arrival sequence $(a_{k,n})$, which marks the states the trajectory from $k$ can arrive at: the state $n$ is visited exactly when $n=k$, or when a visited state maps into $n$; the predecessors of $n$ under $\mathrm{Col}$ are $2n$ (which halves to $n$) and, when $3\mid(n-1)$ with $(n-1)/3$ odd, also $(n-1)/3$ (which the $3m+1$ step sends to $n$). This yields the recurrence

$$
a_{k,n} \;=\; \delta_{n,k} \;+\; a_{k,2n} \;+\; \mathbf{1}\bigl[3\mid(n-1)\ \text{and}\ (n-1)/3\ \text{odd}\bigr]\,a_{k,(n-1)/3},
$$

in which $\delta_{n,k}$ is the Kronecker delta (equal to $1$ when $n=k$ and $0$ otherwise), $\mathbf{1}[\cdot]$ is the indicator function of the bracketed condition, and the statement "the trajectory from $k$ reaches $1$" becomes "$a_{k,1}\neq 0$". Because this recurrence refers both to smaller and larger indices, it is not a well-founded recursion; the source therefore embeds it in a linear iterative functional equation (an equation in which the unknown function is evaluated at transformed arguments of its variable). With real weights $w_b$ (backward) and $w_f$ (forward) the equation reads

$$
A_k(x) \;=\; w_b\,\frac{A_k(\sqrt{x})+A_k(-\sqrt{x})}{2} \;+\; w_f\,x\,\frac{A_k(x^3)-A_k(-x^3)}{2} \;+\; x^k,
$$

whose formal coefficients reproduce the arrival sequence when $w_b=w_f=1$. For $|w_b|+|w_f|<1$ the equation has a unique analytic solution within the bounded analytic functions on the unit disc, given by a Neumann series — the operator geometric series $\sum_{n\ge 0}H^n=(I-H)^{-1}$ for the operator $H=w_b H_1+w_f H_2$ built from the two compositions above. Unfolding this series shows that $H$ maps the monomial $x^m$ to $w_b x^{m/2}$ when $m$ is even and to $w_f x^{3m+1}$ when $m$ is odd — exactly one Collatz step on the exponent — so the solution is the weighted trajectory generating function $A_k(x)=\sum_{i\ge 0}W_i x^{d_{k,i}}$, where $W_i$ is the running product of the weights along the trajectory. Consequently $a_{k,1}=A'_k(0)=\sum_{i:\,d_{k,i}=1}W_i$ is a convergent, positively weighted sum over the visits of the trajectory to $1$; after the first visit, the cycle $1\to 4\to 2\to 1$ contributes a geometric tail with ratio $w_b^2w_f$. For positive real weights this sum is nonzero exactly when the trajectory from $k$ reaches $1$, which is the content of the source's claim that its coefficient conjecture is equivalent to the Collatz conjecture; the source's Section 5 identity $(1-w_b^2w_f)a_{5,1}=w_b^3a_{5,8}$ follows from the same computation.

Functional-equation reformulations of Collatz have precedent: Berg and Meinardus (1994) connected the problem to functional equations for generating functions, Burckel (1994) studied related congruential functions, and Neklyudov (2021) developed an operator-theoretic approach; none resolved the conjecture. The source's Section 7 catalogs further blocked routes toward the coefficient conjecture: closed-form or integral representations of $A_k$; Lagrange-transform substitutions (blocked at the exponent-$1/2$ substitution relevant to the square-root composition); Mellin-transform substitutions (which fail under the negative scaling exponents arising in the compositions); a Dirichlet-series analog $D_k(s)=\sum_n a_{k,n}n^{-s}$ (a Dirichlet series is a series $\sum_n c_n n^{-s}$ in the variable $s$, named after the arithmetic functions it classically encodes), which has yielded no analytic control; and injectivity of $A_k$ near $0$.

## Problem Statement

Prove, or refute, the following two equivalent statements.

(1) Standard form (Lagarias, 1985): for every integer $k\ge 1$, the trajectory of the Collatz map $\mathrm{Col}(n)=3n+1$ for odd $n$ and $\mathrm{Col}(n)=n/2$ for even $n$, started at $k$, eventually reaches $1$.

(2) Arrival-coefficient form (Masetti, 2023): fix any positive real weights $w_b, w_f$ with $|w_b|+|w_f|<1$, and for each $k\ge 1$ let $A_k$ be the unique analytic solution of the iterative functional equation (unique within the bounded analytic functions on the unit disc; equivalently, the solution given by the convergent Neumann series described in the background)

$$
A_k(x) = w_b\,\frac{A_k(\sqrt{x})+A_k(-\sqrt{x})}{2} + w_f\,x\,\frac{A_k(x^3)-A_k(-x^3)}{2} + x^k.
$$

Then the arrival coefficient

$$
a_{k,1} \;=\; A'_k(0) \;=\; [x^1]\,A_k(x)
$$

is nonzero for every $k\ge 1$; here $[x^1]$ denotes the coefficient of $x^1$ in the power series expansion.

The two statements are equivalent for positive weights: the coefficient $a_{k,1}$ is a positively weighted sum over the visits of the trajectory from $k$ to the state $1$, so it vanishes exactly when that trajectory never reaches $1$. In particular, statement (2) is not weaker than the Collatz conjecture, and any resolution of either statement — including a nontrivial cycle or a divergent trajectory refuting it — resolves the other. An answer that establishes (2) only for a restricted class of starting values (for example, a density-one set of $k$, or all $k$ below some bound) does not resolve the problem; the quantifier over all $k\ge 1$ is part of the claim. A closed-form or integral representation of $A_k$, analytic control of the Dirichlet-series analog $D_k(s)=\sum_n a_{k,n}n^{-s}$, or a proof of injectivity of $A_k$ near $0$ are documented intermediate routes, not required deliverables: the objective to be evaluated is the uniform nonvanishing of $a_{k,1}$ (equivalently, that every Collatz trajectory reaches $1$).

## References

1. Giulio Masetti, A new conjecture equivalent to Collatz conjecture, arXiv:2305.10117 (2023), https://arxiv.org/abs/2305.10117
2. Terence Tao, Almost all orbits of the Collatz map attain almost bounded values, Forum of Mathematics, Pi 10 (2022), Paper No. e12, DOI 10.1017/fmp.2022.8, arXiv:1909.03562, https://arxiv.org/abs/1909.03562
3. David Barina, Convergence verification of the Collatz problem, The Journal of Supercomputing 77(3) (2021) 2681–2688, DOI 10.1007/s11227-020-03368-x, https://doi.org/10.1007/s11227-020-03368-x
4. David Barina, Improved verification limit for the convergence of the Collatz conjecture, The Journal of Supercomputing 81(7) (2025), DOI 10.1007/s11227-025-07337-0, https://doi.org/10.1007/s11227-025-07337-0
5. Jeffrey C. Lagarias, The 3x+1 problem and its generalizations, The American Mathematical Monthly 92(1) (1985) 3–23, DOI 10.2307/2322189, https://doi.org/10.2307/2322189
6. Lothar Berg and Günter Meinardus, Functional equations connected with the Collatz problem, Results in Mathematics 25(1–2) (1994) 1–12, DOI 10.1007/BF03323136, https://doi.org/10.1007/BF03323136
7. S. Burckel, Functional equations associated with congruential functions, Theoretical Computer Science 123(2) (1994) 397–406, DOI 10.1016/0304-3975(94)90136-8, https://doi.org/10.1016/0304-3975(94)90136-8
8. Mikhail Neklyudov, Functional analysis approach to the Collatz conjecture, arXiv:2106.11859 (2021, revised 2022), https://arxiv.org/abs/2106.11859
