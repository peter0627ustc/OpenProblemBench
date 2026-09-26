# ORB-MATH-05: Binary Goldbach conjecture: is every even integer greater than 2 a sum of two primes?

The strong (binary) Goldbach conjecture, originating in the 1742 correspondence between Christian Goldbach and Leonhard Euler, asserts that every even integer greater than 2 can be written as the sum of two primes. Despite substantial partial results — Helfgott's proof of the ternary Goldbach conjecture, Chen's theorem on primes plus almost-primes, density-zero bounds on the exceptional set, and computational verification up to 4×10^18 — the conjecture in its full unrestricted form remains open. This record audits the literature status of the conjecture as surfaced by a 2024 paper on density versions of the problem, which itself addresses only almost-all and density-restricted variants.

## Background

In a 1742 letter to Leonhard Euler, Christian Goldbach proposed a statement about representing integers as sums of primes; the form that has become canonical, confirmed by Euler as a natural restatement, is that every even integer greater than 2 is the sum of two primes (equivalently, every even integer $n\ge 4$ is $p+q$ with $p,q$ prime, where equal primes are allowed, e.g. $4=2+2$). This is called the strong or binary Goldbach conjecture; it implies the weak (ternary) conjecture that every odd integer greater than 5 is the sum of three primes.

The central tool for such additive problems is the circle method (Hardy and Littlewood's technique of expressing the number of representations as an integral over the unit circle of a generating function, then estimating contributions from major arcs near rational points with small denominator and minor arcs elsewhere). Vinogradov used it in 1937 to prove the ternary statement for all sufficiently large odd numbers, and Harald Helfgott completed the ternary conjecture in 2013 by strengthening both the major-arc and minor-arc estimates and verifying the remaining finite range computationally. The circle method does not directly settle the binary problem: for a two-prime sum the major arcs dominate the analysis in a way that requires distribution information about primes that current techniques cannot supply.

The best approximations to the binary conjecture are of three kinds. First, Chen's theorem (Chen Jing-run, 1973) states that every sufficiently large even integer is the sum of a prime and a $P_2$-number, i.e. an integer with at most two prime factors (counted with multiplicity); this remains the strongest result of the prime-plus-almost-prime type. Second, results on the exceptional set — the set of even integers up to $x$ that are not a sum of two primes — show it is small: Montgomery and Vaughan (1975) proved it has size bounded by $O(x^{1-\delta})$ for some $\delta>0$, so that the conjecture holds for almost all even integers (all except a set of natural density zero); subsequent work has shrunk the exponent but never shown the exceptional set is empty or bounded. Third, the conjecture has been verified by computation for all even integers up to $4\cdot 10^{18}$ (Oliveira e Silva, Herzog, Pardi, 2014). A common heuristic explanation for the difficulty is the parity barrier of sieve theory: standard sieve methods cannot distinguish numbers with an odd number of prime factors from those with an even number, and so cannot by themselves certify a number with exactly one prime factor.

The immediate source of this candidate record is a 2024 paper of Alsetri and Shao on density versions of the binary Goldbach problem: if $A$ is a subset of the primes whose relative density in every reduced residue class (a congruence class $a \bmod m$ with $\gcd(a,m)=1$) is at least $\delta>1/2$, then almost all even integers are sums of two elements of $A$; the threshold $1/2$ is best possible. That work, like the almost-all results before it, leaves the original conjecture untouched, and its authors explicitly frame it against the still-unresolved classical problem.

## Problem Statement

Prove or disprove the binary (strong) Goldbach conjecture: every even integer $n$ with $n\ge 4$ (equivalently, every even integer greater than 2) can be written as $n=p+q$ where $p$ and $q$ are both prime (the two primes may be equal, as in $4=2+2$). A resolution must cover all even integers without exception — partial results such as validity for almost all even integers, validity for sufficiently large even integers with a prime plus an almost-prime, or verification up to any finite bound do not settle the question.

The verification contract below evaluates answers to this statement. It does not narrow or redefine the research question.

Known solving difficulties:

- Circle-method obstruction: for a two-prime sum the expected main term sits entirely on the major arcs, and estimating it requires level-of-distribution information about the primes (input of Vinogradov/sieve type beyond what is currently provable, essentially Hardy–Littlewood conjectures on primes in arithmetic progressions or short intervals).
- Parity barrier of sieve theory: linear sieves cannot distinguish integers with an odd from an even number of prime factors, so no current sieve framework can certify that the second summand has exactly one prime factor; Chen's theorem is the known limit of this approach.
- The problem is universal over all even integers, so finite computation, almost-all results, and density-restricted results (as in Alsetri–Shao 2024) are structurally insufficient; a solution needs an argument controlling every even integer, including the sparse residual cases that exceptional-set estimates leave out.
- A disproof would require finding an even integer with no two-prime representation; heuristics (the expected number of representations grows like a constant multiple of $n/\log^2 n$ in the Hardy–Littlewood prediction) and verification to 4·10^18 make this outcome appear extremely unlikely, though not logically excluded.

## Current Progress

- Status: `ready`

Source fidelity: the LKM record drawn from Alsetri–Shao (arXiv:2405.18576; published in Acta Arithmetica 218 (2025), 285–295, DOI 10.4064/aa240615-19-9) was checked against the arXiv page directly. It is accurate: the paper proves almost-all and density-restricted variants (relative density δ > 1/2 in every reduced residue class suffices for almost all even integers to lie in A+A, and 1/2 is sharp) and does not address the full conjecture. One attribution correction: the open problem is the classical Goldbach–Euler problem of 1742, not a question posed by that paper; the record's formulation is therefore aligned with the standard authoritative statement rather than attributed to the cited 2024 work. No conflation of adjacent results was found in the LKM paraphrase.

Helfgott (arXiv:1305.2897, major arcs, 2013; arXiv:1205.5252, minor arcs, 2012) completely resolved the ternary (weak) Goldbach conjecture: every odd integer greater than 5 is a sum of three primes. Since the binary conjecture implies but is not implied by the ternary one, this landmark does not settle the binary problem.

Chen's theorem (Sci. Sinica 16 (1973), 157–176; reprint DOI 10.1142/9789812776600_0021) remains the strongest prime-plus-almost-prime result: every sufficiently large even integer is a prime plus a number with at most two prime factors. Fifty years of subsequent sieve work has not improved 'at most two' to 'exactly one', largely due to the parity barrier.

Montgomery–Vaughan (Acta Arithmetica 27 (1975), 353–370, DOI 10.4064/aa-27-1-353-370) proved the exceptional set of non-representable even integers up to x has size O(x^{1−δ}), i.e. density zero; later authors have reduced the exponent further, and the 2024 Alsetri–Shao paper extends almost-all statements to density-restricted prime subsets. All of these leave a possibly unbounded exceptional set, so the universal statement over all even integers remains untouched.

Oliveira e Silva, Herzog, and Pardi (Mathematics of Computation 83 (2014), 2033–2060, DOI 10.1090/S0025-5718-2013-02787-1) verified the conjecture empirically for all even integers up to 4·10^18 with no counterexample; finite verification cannot decide a universal statement over all even integers.

Coverage and status: retrieval combined direct arXiv and Crossref verification of the cited works with web searches for 2024–2026 proof claims. No proof or counterexample of the binary conjecture has been announced or accepted as of August 2026; standard reference summaries of the problem consistently list the strong conjecture as open. Uncertainty: an unnoticed preprint claim could exist, but nothing in the accepted literature resolves it. The surviving open core is the conjecture itself in full generality.

## Scientific Significance

Affected-field significance: `high`.

A proof would directly change the core knowledge of additive number theory: it would resolve the oldest open problem in the field (dating to 1742), and any successful technique would have to overcome the parity barrier of sieve theory or extend the circle method beyond its current reach for two-prime problems, changing the field's core methods and capabilities. A disproof via counterexample would be an equally direct and fundamental revision of the widely believed heuristics for prime sums. The impact is direct, not indirect.

## References

1. Ali Alsetri and Xuancheng Shao, "Density versions of the binary Goldbach problem", Acta Arithmetica 218 (2025), 285–295, DOI 10.4064/aa240615-19-9; preprint arXiv:2405.18576 (2024), https://arxiv.org/abs/2405.18576
2. H. A. Helfgott, "Major arcs for Goldbach's problem" (2013), arXiv:1305.2897, https://arxiv.org/abs/1305.2897
3. H. A. Helfgott, "Minor arcs for Goldbach's problem" (2012), arXiv:1205.5252, https://arxiv.org/abs/1205.5252
4. T. Oliveira e Silva, S. Herzog, and S. Pardi, "Empirical verification of the even Goldbach conjecture and computation of prime gaps up to 4⋅10¹⁸", Mathematics of Computation 83 (2014), 2033–2060, DOI 10.1090/S0025-5718-2013-02787-1, https://doi.org/10.1090/S0025-5718-2013-02787-1
5. Jing-run Chen, "On the representation of a larger even integer as the sum of a prime and the product of at most two primes", Sci. Sinica 16 (1973), 157–176; reprint in The Goldbach Conjecture (World Scientific, Series in Pure Mathematics, 2002), pp. 275–294, DOI 10.1142/9789812776600_0021, https://doi.org/10.1142/9789812776600_0021
6. H. L. Montgomery and R. C. Vaughan, "The exceptional set of Goldbach's problem", Acta Arithmetica 27 (1975), 353–370, DOI 10.4064/aa-27-1-353-370, https://doi.org/10.4064/aa-27-1-353-370
