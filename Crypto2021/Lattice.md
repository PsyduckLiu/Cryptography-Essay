# Lattice Cryptography

## 1. Subtractive Sets over Cyclotomic Rings: Limits of Schnorr-like Arguments over Lattices

We study when (dual) Vandermonde systems of the form `V_T ⋅ z = s⋅w` admit a solution `z` over a ring `R`, where `V_T` is the Vandermonde matrix defined by a set `T` and where the “slack” `s` is a measure of the quality of solutions. To this end, we propose the notion of `(s,t)`-subtractive sets over a ring `R`, with the property that if `S` is `(s,t)`-subtractive then the above (dual) Vandermonde systems defined by any `t`-subset `T ⊆ S` are solvable over `R`. The challenge is then to find large sets `S` while minimising (the norm of) `s` when given a ring `R`.

By constructing families of `(s,t)`-subtractive sets `S` of size `n = poly(λ)` over cyclotomic rings `R = ZZ[ζ_{p^ℓ}]` for prime `p`, we construct Schnorr-like lattice-based proofs of knowledge for the SIS relation `A ⋅ x = s ⋅ y mod q` with `O(1/n)` knowledge error, and `s=1` in case `p = poly(λ)`. Our technique slots naturally into the lattice Bulletproof framework from Crypto’20, producing lattice-based succinct arguments for NP with better parameters.

We then give matching impossibility results constraining `n` relative to `s`, which suggest that our Bulletproof-compatible protocols are optimal unless fundamentally new techniques are discovered. Noting that the knowledge error of lattice Bulletproofs is `Ω(log k/n)` for witnesses in `R^k` and subtractive set size `n`, our result represents a barrier to practically efficient lattice-based succinct arguments in the Bulletproof framework.

Beyond these main results, the concept of `(s,t)`-subtractive sets bridges group-based threshold cryptography to the lattice settings, which we demonstrate by relating it to distributed pseudorandom functions.



***

## 2. A Compressed Sigma-Protocol Theory for Lattices

We show a {\em lattice-based} solution for commit-and-prove transparent circuit ZK with {\em polylog-communication}, the {\em first} not depending on PCPs.

We start from {\em compressed $\Sigma$-protocol theory} (CRYPTO 2020), which is built around basic $\Sigma$-protocols for opening an arbitrary linear form on a long secret vector that is
compactly committed to. These protocols are first compressed using a recursive ``folding-technique'' adapted from Bulletproofs, at the expense of logarithmic rounds. Proving in ZK that the secret vector satisfies a given constraint -- captured by a circuit -- is then by  (blackbox) reduction to the linear case, via arithmetic secret-sharing techniques adapted from MPC. Commit-and-prove is also facilitated, i.e., when commitment(s) to the secret vector are created ahead of any circuit-ZK proof. On several platforms (incl.\ DL) this leads to logarithmic communication. 
Non-interactive versions follow from Fiat-Shamir.

This abstract modular theory strongly suggests that it should somehow be supported by a lattice-platform {\em as well}. However, when going through the motions and trying to establish low communication (on an SIS-platform), a certain significant lack in current understanding of multi-round protocols is exposed.

Namely, as opposed to the DL-case,  the basic $\Sigma$-protocol in question has {\em poly-small challenge} space. Taking into account the compression-step -- which yields {\em non-constant} rounds -- and the necessity for parallelization to reduce error, there is no known result that the compound protocol admits an efficient knowledge extractor with small error. In fact, we identify a recent related work where this accounts for a gap in the analysis. We resolve the state of affairs here by a combination of two novel results which are fully general and of independent interest.
The first gives a tight analysis of efficient knowledge extraction in case of non-constant rounds combined with poly-small challenge space, whereas the  second shows that parallel repetition indeed forces rapid decrease of knowledge error. 

Moreover, in our present context, arithmetic secret sharing is not defined over a large finite field but over a quotient of a number ring and this forces our careful adaptation of how the linearization techniques are deployed.

We develop our protocols in an abstract framework that is conceptually simple and can be flexibly instantiated. In particular, the framework applies to arbitrary rings and norms. 

As a byproduct, our compressed $\Sigma$-protocol can double as a PoK for an SIS preimage. 
In this mode of operation, it improves the communication-efficiency of the PoK by Bootle et al.\ (CRYPTO 2020).



***

## 3. A New Simple Technique to Bootstrap Various Lattice Zero-Knowledge Proofs to QROM Secure NIZKs

Many of the recent advanced lattice-based Sigma-/public-coin honest verifier (HVZK) interactive protocols based on the techniques developed by Lyubashevsky (Asiacrypt'09, Eurocrypt'12) can be transformed into a non-interactive zero-knowledge (NIZK) proof in the random oracle model (ROM) using the Fiat-Shamir transform. Unfortunately, although they are known to be secure in the __classical__ ROM, existing proof techniques are incapable of proving them secure in the __quantum__ ROM (QROM). Alternatively, while we could instead rely on the Unruh transform (Eurocrypt'15), the resulting QROM secure NIZK will incur a large overhead compared to the underlying interactive protocol. 

In this paper, we present a new simple semi-generic transform that compiles many existing lattice-based Sigma-/public-coin HVZK interactive protocols into QROM secure NIZKs. 
Our transform builds on a new primitive called __extractable linear homomorphic commitment__ protocol. The resulting NIZK has several appealing features: it is not only a proof of knowledge but also straight-line extractable; the proof overhead is smaller compared to the Unruh transform; it enjoys a relatively small reduction loss; and it requires minimal background on quantum computation. To illustrate the generality of our technique, we show how to transform the recent Bootle et al.'s 5-round protocol with an exact sound proof (Crypto'19) into a QROM secure NIZK by increasing the proof size by a factor of 2.6. This compares favorably to the Unruh transform that requires a factor of more than 50.



***

## 4. SMILE: Set Membership from Ideal Lattices with Applications to Ring Signatures and Confidential Transactions

In a set membership proof, the public information consists of a set of elements and a commitment. The prover then produces a zero-knowledge proof showing that the commitment is indeed to some element from the set. This primitive is closely related to concepts like ring signatures and ``one-out-of-many'' proofs that underlie many anonymity and privacy protocols. The main result of this work is a new succinct lattice-based set membership proof whose size is logarithmic in the size of the set. 

We also give transformations of our set membership proof to a ring signature scheme and to a confidential transaction payment system. The ring signature size is also logarithmic in the size of the public key set and has size $16$~KB for a set of $2^5$ elements, and $22$~KB for a set of size $2^{25}$. At an approximately $128$-bit security level, these outputs are between 1.5X and 7X smaller than the current state of the art succinct ring signatures of Beullens et al. (Asiacrypt 2020) and Esgin et al. (CCS 2019).  

We then show that our ring signature, combined with a few other techniques and optimizations, can be turned into a fairly efficient Monero-like confidential transaction system based on the MatRiCT framework of Esgin et al. (CCS 2019).  With our new techniques, we are able to reduce the transaction proof size by factors of about 4X - 10X over the aforementioned work. For example, a transaction with two inputs and two outputs, where each input is hidden among $2^{15}$ other accounts, requires approximately $30$KB in our protocol.



***

## 5. Deniable Fully Homomorphic Encryption from Learning With Errors

We define and construct {\it Deniable Fully Homomorphic Encryption} based on the Learning With Errors (LWE) polynomial hardness assumption. Deniable FHE enables storing encrypted data in the cloud to be processed securely without decryption, maintaining deniability of the encrypted data, as well the prevention of vote-buying in electronic voting schemes where encrypted votes can be tallied without decryption.

Our constructions achieve {\it compactness} independently of the level of deniability- both the size of the public key and the size of the ciphertexts are bounded by a fixed polynomial, independent of the faking probability achieved by the scheme. This is in contrast to all previous constructions of deniable encryption schemes (even without requiring homomorphisms) which are based on polynomial hardness assumptions, originating with the seminal work of Canetti, Dwork, Naor and Ostrovsky (CRYPTO 1997) in which the ciphertext size grows with the inverse of the faking probability. Canetti {\it et al.} argued that this dependence ``seems inherent'', but our constructions illustrate this is not the case. We note that the Sahai-Waters (STOC13) construction of deniable encryption from indistinguishability-obfuscation achieves compactness and can be easily modified to achieve deniable FHE as well, but it requires multiple, stronger sub-exponential hardness assumptions, which are furthermore not post-quantum secure. In contrast, our constructions rely only on the LWE polynomial hardness assumption, as currently required for FHE even without deniability.

The running time of our encryption algorithm depends on the inverse of the faking probability, thus the scheme falls short of achieving simultaneously compactness, negligible deniability probability {\it and} polynomial encryption time. Yet, we believe that achieving compactness is a fundamental step on the way to achieving all properties simultaneously as has been the historical journey for other primitives such as functional encryption. Interestingly, we note that our constructions support large message spaces, whereas previous constructions were bit by bit, and can be run in online-offline model of encryption, where the bulk of computation is independent of the message and may be performed in an offline pre-processing phase. The running time of the online phase, is independent of the faking probability, whereas the offline encryption run-time grows with the inverse of the faking probability. 

At the heart of our constructions is a new way to use bootstrapping to obliviously generate FHE ciphertexts so that it supports faking under coercion.



***

## 6. Counterexamples to New Circular Security Assumptions Underlying iO

We study several strenthenings of classical circular security assumptions which were recently introduced in four new constructions of indistinguishabilty obfuscation from lattice-based primitives: Brakerski-D\"ottling-Garg-Malavolta (Eurocrypt 2020), Gay-Pass (STOC 2021), Brakerski-D\"ottling-Garg-Malavolta (Eprint 2020) and Wee-Wichs (Eprint 2020).

We provide explicit counterexamples to the {\em $2$-circular shielded randomness leakage} assumption of Gay-Pass and the {\em homomorphic pseudorandom LWE samples} conjecture of Wee-Wichs.
Our work suggests a separation between classical circular security of the kind underlying un-levelled fully-homomorphic encryption from the strengthened versions underlying recent iO constructions, showing that they are not (yet) on the same rigorous footing.

 Our counterexamples exploit the flexibility to choose specific implementations of circuits and LWE distributions in the Gay-Pass and Wee-Wichs assumptions. It remains possible that other implementations do result in an unbroken $\iO$ scheme. But our work shows that this will, at least, require refinement of the assumptions. In particular, generic circular security assumptions/definitions are insufficient, and their security is actually sensitive to the specific structure of the leakages involved.



***

## 7. How to Meet Ternary LWE Keys

The LWE problem with its ring variants is today the most prominent candidate for building efficient public key cryptosystems resistant to quantum computers. NTRU-type cryptosystems use an LWE-type variant with small max-norm secrets, usually with ternary coefficients from the set $\{-1,0,1\}$. The presumably best attack on these schemes is a hybrid attack that combines lattice reduction techniques with Odlyzko's Meet-in-the-Middle approach. Odlyzko's algorithm is a classical combinatorial attack that for key space size $S$ runs in time $S^{0.5}$. We substantially improve on this Meet-in-the-Middle approach, using the representation technique developed for subset sum  algorithms. Asymptotically, our heuristic Meet-in-the-Middle attack runs in time roughly $S^{0.25}$, which also beats the $S^{\frac 1 3}$ complexity of the best known quantum algorithm. 

For the round-3 NIST post-quantum encryptions NTRU-Encrypt and NTRU-Prime we obtain non-asymptotic instantiations of our  attack with complexity  roughly $S^{0.35}$. 
As opposed to other combinatorial attacks, our attack benefits from larger LWE field sizes $q$, as they are often used in modern lattice-based signatures. For example, for BLISS signatures we obtain non-asymptotic combinatorial attacks in between $S^{0.31}$ and $S^{0.35}$, for GLP signatures in $S^{0.3}$. 

Our attacks do not invalidate the security claims of the aforementioned schemes. However, they establish improved combinatorial upper bounds for their security. We leave it is an open question whether our new Meet-in-the-Middle attack in combination with lattice reduction can be used to speed up the hybrid attack.



***

## 8. Lattice Reduction with Approximate Enumeration Oracles: Practical Algorithms and Concrete Performance

This work provides a systematic investigation of the use of approximate enumeration oracles in BKZ, building on recent technical progress on speeding-up lattice enumeration: relaxing (the search radius of) enumeration and extended preprocessing which preprocesses in a larger rank than the enumeration rank. First, we heuristically justify that relaxing enumeration with certain extreme pruning asymptotically achieves an exponential speed-up for reaching the same root Hermite factor (RHF). Second, we perform simulations/experiments to validate this and the performance for relaxed enumeration with numerically optimised pruning for both regular and extended preprocessing. 
Upgrading BKZ with such approximate enumeration oracles gives rise to our main result, namely a practical and faster (compared to previous work) polynomial-space lattice reduction algorithm for reaching the same RHF in practical and cryptographic parameter ranges. We assess its concrete time/quality performance with extensive simulations and experiments. As a consequence, we update the extrapolation of the crossover rank between a square-root cost estimate for quantum enumeration using our algorithm and the Core-SVP cost estimate for quantum sieving to 547.



***

## 9. Towards faster polynomial-time lattice reduction

The LLL algorithm is a polynomial-time algorithm for reducing d-dimensional lattice with exponential approximation factor. Currently, the most efficient variant of LLL, by Neumaier and Stehl\'e, has a theoretical running time in $d^4\cdot B^{1+o(1)}$ where $B$ is the bitlength of the
entries, but has never been implemented. This work introduces new asymptotically fast, parallel, yet heuristic, reduction algorithms with their optimized implementations. Our algorithms are recursive and fully exploit fast block matrix multiplication. We experimentally demonstrate that by carefully controlling the floating-point precision during the recursion steps, we can reduce euclidean lattices of rank d in time $\tilde{O}(d^\omega\cdot C)$, i.e., almost a constant number of matrix multiplications, where $\omega$ is the exponent of matrix multiplication and C is the log of the condition number of the matrix. For cryptographic applications, C is close to B, while it can be up to d times larger in the worst case. It improves the running-time of the state-of-the-art implementation fplll by a multiplicative factor of order $d^2\cdot B$. Further, we show that we can reduce structured lattices, the so-called knapsack lattices, in time $\tilde{O}(d^{\omega-1}\cdot C)$ with a progressive reduction strategy. Besides allowing reducing huge lattices, our implementation can break several instances of Fully Homomorphic Encryption schemes based  on large integers in dimension 2,230 with 4 millions of bits.



***

## 10. Lower bounds on lattice sieving and information set decoding

In two of the main areas of post-quantum cryptography, based on lattices and codes, nearest neighbor techniques have been used to speed up state-of-the-art cryptanalytic algorithms, and to obtain the lowest asymptotic cost estimates to date [May--Ozerov, Eurocrypt'15; Becker--Ducas--Gama--Laarhoven, SODA'16]. These upper bounds are useful for assessing the security of cryptosystems against known attacks, but to guarantee long-term security one would like to have closely matching lower bounds, showing that improvements on the algorithmic side will not drastically reduce the security in the future. As existing lower bounds from the nearest neighbor literature do not apply to the nearest neighbor problems appearing in this context, one might wonder whether further speedups to these cryptanalytic algorithms can still be found by only improving the nearest neighbor subroutines.
We derive new lower bounds on the costs of solving the nearest neighbor search problems appearing in these cryptanalytic settings. For the Euclidean metric we show that for random data sets on the sphere, the locality-sensitive filtering approach of [Becker--Ducas--Gama--Laarhoven, SODA 2016] using spherical caps is optimal, and hence within a broad class of lattice sieving algorithms covering almost all approaches to date, their asymptotic time complexity of $2^{0.292d + o(d)}$ is optimal. Similar conditional optimality results apply to lattice sieving variants, such as the $2^{0.265d + o(d)}$ complexity for quantum sieving [Laarhoven, PhD thesis 2016] and previously derived complexity estimates for tuple sieving [Herold--Kirshanova--Laarhoven, PKC 2018]. For the Hamming metric we derive new lower bounds for nearest neighbor searching which almost match the best upper bounds from the literature [May--Ozerov, Eurocrypt 2015]. As a consequence we derive conditional lower bounds on decoding attacks, showing that also here one should search for improvements elsewhere to significantly undermine security estimates from the literature.