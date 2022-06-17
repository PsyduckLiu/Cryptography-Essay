# Secret Sharing

## 1. Upslices, Downslices, and Secret-Sharing with Complexity of $1.5^n$

A secret-sharing scheme allows to distribute a secret $s$ among $n$ parties such that only some predefined ``authorized'' sets of parties can reconstruct the secret, and all other ``unauthorized'' sets learn nothing about $s$.  The collection of authorized/unauthorized sets is be captured by a monotone function $f:\{0,1\}^n\rightarrow \{0,1\}$. In this paper, we focus on monotone functions that all their min-terms are sets of size $a$, and on their duals -- monotone functions whose max-terms are of size $b$. We refer to these classes as $(a,n)$-\emph{upslices} and $(b,n)$-\emph{downslices}, and note that these natural families correspond to monotone $a$-regular DNFs and monotone $(n-b)$-regular CNFs. We derive the following results.

\begin{enumerate}
    \item (General downslices) Every downslice can be realized with total share size of $1.5^{n+o(n)}&lt;2^{0.585 n}$. Since every monotone function can be cheaply decomposed into $n$ downslices, we obtain a similar result for general access structures improving the previously known $2^{0.637n+o(n)}$ complexity of Applebaum, Beimel, Nir and Peter (STOC 2020). We also achieve a minor improvement in the exponent of linear secrets sharing schemes. 

    \item (Random mixture of upslices) Following, Beimel and Farr{\`{a}}s (TCC 2020) who studied the complexity of random DNFs with constant-size terms, we consider the following general distribution $F$ over monotone DNFs: For each width value $a\in [n]$, uniformly sample $k_a$ monotone terms of size $a$, where $\vec{k}=(k_1,\ldots,k_n)$ is an arbitrary vector of non-negative integers. We show that, except with exponentially small probability, $F$ can be realized with share size of $2^{0.5 n+o(n)}$ and can be linearly realized with an exponent strictly smaller than $2/3$. Our proof also provides a candidate distribution for the ``exponentially-hard'' access structure. 
\end{enumerate}

We use our results to explore connections between several seemingly unrelated questions about the complexity of secret-sharing schemes such as worst-case vs. average-case, linear vs. non-linear, and primal vs. dual access structures. We prove that, in at least one of these settings, there is a significant gap in secret-sharing complexity.



***

## 2. Asymptotically-Good Arithmetic Secret Sharing over Z/p^{\ell}Z with Strong Multiplication and Its Applications to Efficient MPC

The current paper studies information-theoretically secure multiparty computation (MPC) over rings $\Z/p^{\ell}\Z$. This is a follow-up research of recent work on MPC over rings $\Z/p^{\ell}\Z$. In the work of \cite[TCC2019]{tcc}, a protocol based on the Shamir secret sharing over $\Z/p^{\ell}\Z$ was presented. As in the field case, its limitation is that the share size has to grow as the number of players increases. Then several MPC protocols were developed in \cite[Asiacrypt 2020]{asiacrypt} to overcome this limitation. However, the MPC protocols in \cite[Asiacrypt 2020]{asiacrypt} suffer from several drawbacks: (i) the offline multiplication gate has super-linear communication complexity;
(ii) the share size is doubled for the most important case, namely over $\Z/2^{\ell}\Z$ due to infeasible lifting of self-orthogonal codes from fields to rings; (iii) most importantly, the BGW model could not be applied via the secret sharing given in \cite[Asiacrypt 2020]{asiacrypt} due to lack of strong multiplication.

Our contribution in this paper is three fold. Firstly, we overcome all the drawbacks in \cite{tcc,asiacrypt} mentioned above. Secondly, we establish an arithmetic secret sharing with strong multiplication, which is the most important primitive in the BGW model. Thirdly, we lift Reverse Multiplication Friendly Embeddings (RMFE) from fields to rings, with same (linear) complexity. Note that RMFE has become a standard technique for amortized communication complexity in MPC, as in \cite[CRYPTO'18]{crypto2018} and \cite[CRYPTO'19]{dn19}.

To obtain our theoretical results, we use the existence of lifts of curves over rings, then use the known results stating that Riemann-Roch spaces are free modules. To make our scheme practical, we start from good algebraic geometry codes over finite fields obtained from existing computational techniques. Then we present, and implement, an efficient algorithm to Hensel-lift the generating matrix of the code, such that the multiplicative conditions are preserved over rings. Existence of this specific lift is guaranteed by the previous theory. On the other hand, a random lifting of codes over from fields to Galois rings does not preserve multiplicativity in general. (Notice that our indirect method is motivated by the fact that, following the theory instead, would require to ``preprocess'' the curve under a form with ``smooth" equations, in particular with many variables, before lifting it. But computing on these objects over rings is out of the scope of existing research). Finally we provide efficient elementary methods for sharing and (robust) reconstruction of secrets over rings. As a result, arithmetic secret sharing over $\Z/p^{\ell}\Z$ with strong multiplication can be efficiently constructed and practically applied.



***

## 3. Large Message Homomorphic Secret Sharing from DCR and Applications

We present the first homomorphic secret sharing (HSS) construction that simultaneously (1) has negligible correctness error, (2) supports integers from an exponentially large range, and (3) relies on an assumption not known to imply FHE --- specifically, the Decisional Composite Residuosity (DCR) assumption. This resolves an open question posed by Boyle, Gilboa, and Ishai (Crypto 2016). Homomorphic secret sharing is analogous to fully-homomorphic encryption, except the ciphertexts are shared across two non-colluding evaluators. Previous constructions of HSS either had non-negligible correctness error and polynomial-size plaintext space or were based on the stronger LWE assumption. We also present two applications of our technique: a multi-server ORAM with constant bandwidth overhead, and a rate-$1$ trapdoor hash function with negligible error rate.



***

## 4. Traceable Secret Sharing and Applications

Consider a scenario where Alice stores some secret data $s$ on $n$ servers using a $t$-out-of-$n$ secret sharing scheme. Trudy (the collector) is interested in the secret data of Alice and is willing to pay for it. Trudy publishes an advertisement on the internet which describes an elaborate cryptographic scheme to collect the shares from the $n$ servers. Each server who decides to submit its share is paid a hefty monetary reward and is guaranteed ``immunity" from being caught or prosecuted in a court for violating its service agreement with Alice. Bob is one of the servers and sees this advertisement. On examining the collection scheme closely, Bob concludes that there is no way for Alice to prove anything in a court that he submitted his share. Indeed, if Bob is rational, he might use the cryptographic scheme in the advertisement and submit his share since there are no penalties and no fear of being caught and prosecuted. Can we design a secret sharing scheme which Alice can use to avoid such a scenario?

We introduce a new primitive called as \textit{Traceable Secret Sharing} to tackle this problem. In particular, a traceable secret sharing scheme guarantees that a cheating server always runs the risk of getting traced and prosecuted by providing a valid evidence (which can be examined in a court of law) implicating its dishonest behavior. We explore various definitional aspects and show how they are highly non-trivial to construct (even ignoring efficiency aspects). We then give an efficient construction of traceable secret sharing assuming the existence of a secure two-party computation protocol. We also show an application of this primitive in constructing traceable protocols for multi-server delegation of computation.



***

## 5. Quadratic Secret Sharing and Conditional Disclosure of Secrets

There is a huge gap between the upper and lower bounds on the share size of secret-sharing schemes for arbitrary $n$-party access structures, and consistent with our current knowledge the optimal share size can be anywhere between polynomial in $n$ and exponential in $n$. For linear secret-sharing schemes, we know that the share size for almost all $n$-party access structures must be exponential in $n$. Furthermore, most constructions of efficient secret-sharing schemes are linear. We would like to study larger classes of secret-sharing schemes  with two goals.  On one hand, we want to prove lower bounds for larger classes of secret-sharing schemes, possibly shedding some light on the share size of general secret-sharing schemes. On the other hand, we want to construct efficient secret-sharing schemes for access structures that do not have efficient linear secret-sharing schemes. Given this motivation, Paskin-Cherniavsky and Radune (ITC'20) defined and studied a new class of secret-sharing schemes in which the shares are generated by applying  (low-degree) polynomials to the secret and some random field elements. The special case $d=1$ corresponds to linear and multi-linear secret sharing schemes. 

We define and study two additional classes of polynomial secret-sharing schemes: (1) schemes in which for every authorized set the reconstruction of the secret is done using polynomials and (2) schemes in which both sharing and reconstruction are done by polynomials. For linear secret-sharing schemes, schemes with linear sharing and schemes with linear reconstruction are  equivalent.  We give evidence that for polynomial secret-sharing schemes, schemes with polynomial sharing are probably stronger than schemes with polynomial reconstruction. We also prove lower bounds on the share size for schemes with polynomial reconstruction. On the positive side, we provide constructions of secret-sharing schemes and conditional disclosure of secrets (CDS) protocols with polynomials of degree-$2$ sharing and reconstruction.   
We extend a construction of Liu et al. (CRYPTO'17) and construct a degree-$2$ $k$-server CDS protocols for a function $f:[N]^k\rightarrow \set{0,1}$ with message size $O(N^{(k-1)/3})$. We also show how to transform our degree-$2$ $k$-server CDS protocol to a robust CDS protocol, and use the robust CDS protocol 
to construct degree-$2$ secret-sharing schemes for arbitrary access structures with share size $O(2^{0.716n})$;
this is better than  the best known share size of $O(2^{0.762n})$ for linear secret-sharing schemes and worse than the best known share size of $O(2^{0.637n})$ for general secret-sharing schemes.



***

## 6. Constructing Locally Leakage-resilient Linear Secret-sharing Schemes

Innovative side-channel attacks have repeatedly falsified the assumption that cryptographic implementations are opaque black-boxes. Therefore, it is essential to ensure cryptographic constructions' security even when information leaks via unforeseen avenues. One such fundamental cryptographic primitive is the secret-sharing schemes, which underlies nearly all threshold cryptography. Our understanding of the leakage-resilience of secret-sharing schemes is still in its preliminary stage. 

This work studies locally leakage-resilient linear secret-sharing schemes. An adversary can leak $m$ bits of arbitrary local leakage from each $n$ secret shares. However, in a locally leakage-resilient secret-sharing scheme, the leakage's joint distribution reveals no additional information about the secret. 

For every constant $m$, we prove that the Massey secret-sharing scheme corresponding to a random linear code of dimension $k$ (over sufficiently large prime fields) is locally leakage-resilient, where $k/n &gt; 1/2$ is a constant. The previous best construction by Benhamouda, Degwekar, Ishai, Rabin (CRYPTO--2018) needed $k/n &gt; 0.907$. A technical challenge arises because the number of all possible $m$-bit local leakage functions is exponentially larger than the number of random linear codes. Our technical innovation begins with identifying an appropriate pseudorandomness-inspired family of tests; passing them suffices to ensure leakage-resilience. We show that most linear codes pass all tests in this family. This Monte-Carlo construction of linear secret-sharing scheme that is locally leakage-resilient has applications to leakage-resilient secure computation. 

Drawing inspiration from the technical approach above, we prove the leakage-resilience of Shamir's secret-sharing scheme for $k\geq 0.8675 n$. Furthermore, we highlight a crucial bottleneck for all the analytical approaches in this line of work. Benhamouda et al. introduced an analytical proxy to study the leakage-resilience of secret-sharing schemes; if the proxy is small, then the scheme is leakage-resilient. However, we present a one-bit local leakage function demonstrating that the converse is false, motivating the need for new analytically well-behaved functions that capture leakage-resilience more accurately. 

Technically, the analysis involves probabilistic and combinatorial techniques and (discrete) Fourier analysis. The family of new ``tests'' capturing local leakage functions, we believe, is of independent and broader interest.