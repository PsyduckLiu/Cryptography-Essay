# Low-Complexity Cryptography 

## 1. Low-Complexity Weak Pseudorandom Functions in AC0[MOD2]

A *weak pseudorandom function* (WPRF) is a keyed function $f_k:\{0,1\}^n\to\{0,1\}$ such that, for a random key $k$, a collection of samples $(x, f_k(x))$, for {\em uniformly random} inputs $x$, cannot be efficiently distinguished from totally random input-output pairs $(x,y)$. We study WPRFs in AC0[MOD2], the class of functions computable by AC0 circuits with parity gates, making the following contributions. 

- *Between Lapland and Cryptomania.* We show that WPRFs in AC0[MOD2] imply a variant of the Learning Parity with Noise (LPN) assumption. This gives an unconditional version of an earlier conditional result of Akavia et al. (ITCS 2014). We further show that WPRFs in a subclass of AC0[mod 2] that includes a recent WPRF candidate by Boyle et al. (FOCS 2020) imply, under a seemingly weak additional conjecture, public-key encryption. 

- *WPRF by sparse polynomials.* We propose the first WPRF candidate that can be computed by sparse multivariate polynomials over $\F_2$. We prove that it has subexponential security against linear and algebraic attacks.

- *WPRF in AC0 ◦ MOD2.* We study the existence of WPRFs computed by AC0 circuits \emph{over} parity gates. We propose a modified version of a previous WPRF candidate of Akavia et al., and prove that it resists the algebraic attacks that were used by Bogdanov and Rosen (ECCC 2017) to break the original candidate in quasipolynomial time. We give evidence against the possibility of using {\em public} parity gates and relate this question to other conjectures.



***

## 2. MPC-Friendly Symmetric Cryptography from Alternating Moduli: Candidates, Protocols, and Applications

We study new candidates for symmetric cryptographic primitives that leverage alternation between linear functions over $\Z_2$ and $\Z_3$ to support fast protocols for secure multiparty computation (MPC). This continues the study of weak pseudorandom functions of this kind initiated by Boneh et al. (TCC 2018) and Cheon et al. (ePrint 2020).

We make the following contributions. 
Candidates. We propose new designs of symmetric primitives based on alternating moduli. These include candidate one-way functions, pseudorandom generators, and weak pseudorandom functions in which the key, the  input and the output are all over $\Z_2$. We propose concrete parameters based on cryptanalysis. 

Protocols. We provide a unified approach for securely evaluating modulus-alternating primitives in different MPC models. For the original candidate of Boneh et al., our protocols obtain roughly 2x improvement in all performance measures. We report efficiency benchmarks of an optimized implementation.

Applications. We showcase the usefulness of our candidates for a variety of applications. This includes short "Picnic-style" signature schemes, as well as protocols for oblivious pseudorandom functions, hierarchical key derivation, and distributed key generation for function secret sharing.



***

## 3. No Time to Hash: On Super-Efficient Entropy Accumulation

Real-world random number generators (RNGs) cannot afford to use (slow) cryptographic hashing every time they refresh their state R with a new entropic input X. Instead, they use ``super-efficient'' simple entropy-accumulation procedures, such as

R &lt;-  rot_{alpha, n}(R)  XOR  X

where rot_{alpha,n} rotates an n-bit state R by some fixed number alpha. For example, Microsoft's RNG uses alpha=5 for n=32 and alpha=19 for n=64. Where do these numbers come from? Are they good choices? Should rotation be replaced by a better permutation pi of the input bits?

In this work we initiate a rigorous study of these pragmatic questions, by modeling the sequence of successive entropic inputs X_1,X_2, ... as independent (but otherwise adversarial) samples from some natural distribution family D. We show a simple but surprisingly powerful connection between entropy accumulation and understanding the Fourier spectrum of distributions in D. Our contribution is as follows.

- We define 2-monotone distributions as a rich family D that includes relevant real-world distributions (Gaussian, exponential, etc.), but avoids trivial impossibility results.
  
- For any alpha with gcd(alpha,n)=1, we show that rotation accumulates Omega(n) bits of entropy from n independent samples X_1,...,X_n from any (unknown) 2-monotone distribution with entropy k &gt; 1.

- However, we also show some choices of alpha perform much better than others for a given n. E.g., we show alpha=19 is one of the best choices for n=64; in contrast, alpha=5 is good, but generally worse than alpha=7, for n=32.

- More generally, given a permutation pi and k &gt; 1, we define a simple parameter, the covering number C_{pi,k}, and show that it characterizes the number of steps before the rule 

(R_1,...,R_n) &lt;- (R_{pi(1)},..., R_{pi(n)}) XOR X 

accumulates nearly n bits of entropy from independent, 2-monotone samples of min-entropy k each.

- We build a simple permutation pi^*, which achieves nearly optimal C_{pi^*,k} \approx n/k for all values of k simultaneously, and experimentally validate that it compares favorably with all rotations rot_{alpha,n}.