# Codes and Extractors

## 1. Smoothing Out Binary Linear Codes and Worst-case Sub-exponential Hardness for LPN

Learning parity with noise (LPN) is a notorious (average-case) hard problem that has been well studied in learning theory, coding theory and cryptography since the early 90's. It further inspires the Learning with Errors (LWE) problem [Regev, STOC 2005], which has become one of the central building blocks for post-quantum cryptography and advanced cryptographic. Unlike LWE whose hardness can be reducible from worst-case lattice problems, no corresponding worst-case hardness results were known for LPN until very recently. At Eurocrypt 2019, Brakerski et al. [BLVW19] established the first feasibility result that the worst-case hardness of nearest codeword problem (NCP) (on balanced linear code) at the extremely low noise rate $\frac{\log^2 n}{n}$ implies the quasi-polynomial hardness of LPN at the extremely high noise rate $1/2-1/\poly(n)$. It remained open whether a worst-case to average-case reduction can be established for standard (constant-noise) LPN, ideally with sub-exponential hardness.

We start with a simple observation that the hardness of high-noise LPN over large fields is implied by that of the LWE of the same modulus, and is thus reducible from worst-case hardness of lattice problems. We then revisit [BLVW19], which is the main focus of this work. We first expand the underlying binary linear codes (of the NCP) to not only the balanced code considered in [BLVW19] but also to another code (in some sense dual to balanced code). At the core of our reduction is a new variant of smoothing lemma (for both binary codes) that circumvents the barriers (inherent in the underlying worst-case randomness extraction) and admits tradeoffs for a wider spectrum of parameter choices. In addition to the worst-case hardness result obtained in [BLVW19], we show that for any constant $0&lt;c&lt;1$ the constant-noise LPN problem is ($T=2^{\Omega(n^{1-c})},\epsilon=2^{-\Omega(n^{\min(c,1-c)})},q=2^{\Omega(n^{\min(c,1-c)})}$)-hard assuming that the NCP at the low-noise rate $\tau=n^{-c}$ is ($T'={2^{\Omega(\tau n)}}$, $\epsilon'={2^{-\Omega(\tau n)}}$,$m={2^{\Omega(\tau n)}}$)-hard in the worst case, where $T$, $\epsilon$, $q$ and $m$ are time complexity, success rate, sample complexity, and codeword length respectively. Moreover, refuting the worst-case hardness assumption would imply arbitrary polynomial speedups over the current state-of-the-art algorithms for solving the NCP (and LPN), which is a win-win result. Unfortunately, public-key encryptions and collision resistant hash functions need constant-noise LPN with ($T={2^{\omega(\sqrt{n})}}$, $\epsilon'={2^{-\omega(\sqrt{n})}}$,$q={2^{\sqrt{n}}}$)-hardness (Yu et al., CRYPTO 2016 \& ASIACRYPT 2019), which is almost (up to an arbitrary $\omega(1)$ factor in the exponent) what is reducible from the worst-case NCP when $c= 0.5$. We leave it as an open problem whether the gap can be closed or there is a separation in place.



***

## 2. Silver: Silent VOLE and Oblivious Transfer from Hardness of Decoding Structured LDPC Codes

We put forth new protocols for oblivious transfer extension and vector OLE, called \emph{Silver}, for SILent Vole and oblivious transfER. Silver offers extremely high performances: generating 10 million random OTs on one core of a standard laptop requires only 300ms of computation and 122KB of communication. This represents 37% less computation and ~1300x less communication than the standard IKNP protocol, as well as ~4x less computation and ~4x less communication than the recent protocol of Yang et al. (CCS 2020). Silver is \emph{silent}: after a one-time cheap interaction, two parties can store small seeds, from which they can later \emph{locally} generate a large number of OTs \emph{while remaining offline}. Neither IKNP nor Yang et al. enjoys this feature; compared to the best known silent OT extension protocol of Boyle et al. (CCS 2019), upon which we build up, Silver has 19x less computation, and the same communication. Due to its attractive efficiency features, Silver yields major efficiency improvements in numerous MPC protocols.
    

    Our approach is a radical departure from the standard paradigm for building MPC protocols, in that we do \emph{not} attempt to base our constructions on a well-studied assumption. Rather, we follow an approach closer in spirit to the standard paradigm in the design of symmetric primitives: we identify a set of fundamental structural properties that allow us to withstand all known attacks, and put forth a candidate design, guided by our analysis. We also rely on extensive experimentations to analyze our candidate and experimentally validate their properties. In essence, our approach boils down to constructing new families of linear codes with (plausibly) high minimum distance and extremely low encoding time. While further analysis is of course warranted to confidently assess the security of Silver, we hope and believe that initiating this approach to the design of MPC primitives will pave the way to new secure primitives with extremely attractive efficiency features.



***

## 3. Non-Malleable Codes for Bounded Parallel-Time Tampering

Non-malleable codes allow one to encode data in such a way that once a codeword is being tampered with, the modified codeword is either an encoding of the original message, or a completely unrelated one. Since the introduction of this notion by Dziembowski, Pietrzak, and Wichs (ICS '10 and J. ACM '18), there has been a large body of works realizing such coding schemes secure against various classes of tampering functions. It is well known that there is no efficient non-malleable code secure against all polynomial size tampering functions. Nevertheless,  no code which is non-malleable for \emph{bounded} polynomial size attackers is known and obtaining such a code has been a major open problem.

We present the first construction of a non-malleable code secure against  all polynomial size tampering functions that have {bounded} parallel time. This is an even larger class than all bounded polynomial size functions. In particular, this class includes all functions in non-uniform $\mathbf{NC}$ (and  much more). Our construction is in the plain model (i.e., no trusted setup) and relies on several cryptographic assumptions such as keyless hash functions, time-lock puzzles, as well as other standard assumptions. Additionally, our construction has several appealing properties: the complexity of encoding is independent of the class of tampering functions and we can obtain (sub-)exponentially small error.



***

## 4. Improved Computational Extractors and their Applications

Recent exciting breakthroughs have achieved the first two-source extractors that operate in the low min-entropy regime. Unfortunately, these constructions suffer from non-negligible error, and reducing the error to negligible remains an important open problem. In recent work, Garg, Kalai, and Khurana (GKK, Eurocrypt 2020) investigated a meaningful relaxation of this problem to the computational setting, in the presence of a common random string (CRS). In this relaxed model, their work built explicit two-source extractors for a restricted class of unbalanced sources with min-entropy n^{\gamma} (for some constant \gamma) and negligible error, under the sub-exponential DDH assumption.

In this work, we investigate whether computational extractors in the CRS model be applied to more challenging environments. Specifically, we study network extractor protocols (Kalai et al., FOCS 2008) and extractors for adversarial sources (Chattopadhyay et al., STOC 2020) in the CRS model. We observe that these settings require extractors that work well for balanced sources, making the GKK results inapplicable. 

We remedy this situation by obtaining the following results, all of which are in the CRS model and assume the sub-exponential hardness of DDH.

- We obtain ``optimal'' computational two-source and non-malleable extractors for balanced sources: requiring both sources to have only poly-logarithmic min-entropy, and achieving negligible error. To obtain this result, we perform a tighter and arguably simpler analysis of the GKK extractor.
  
- We obtain a single-round network extractor protocol for poly-logarithmic min-entropy sources that tolerates an optimal number of adversarial corruptions. Prior work in the information-theoretic setting required sources with high min-entropy rates, and in the computational setting had round complexity that grew with the number of parties, required sources with linear min-entropy, and relied on exponential hardness (albeit without a CRS).
  
- We obtain an ``optimal'' adversarial source extractor for poly-logarithmic min-entropy sources, where the number of honest sources is only 2 and each corrupted source can depend on either one of the honest sources. Prior work in the information-theoretic setting had to assume a large number of honest sources.



***

## 5. Adaptive Extractors and their Application to Leakage Resilient Secret Sharing

We introduce Adaptive  Extractors, which unlike traditional randomness extractors, guarantee security even when an adversary obtains leakage on the source \textit{after} observing the extractor output. We make a compelling case for the study of such extractors by demonstrating their use in obtaining adaptive leakage in secret sharing schemes. 

Specifically, at FOCS 2020, Chattopadhyay, Goodman, Goyal, Kumar, Li, Meka, Zuckerman, built an adaptively secure leakage resilient secret sharing scheme (LRSS) with both rate and leakage rate being $\mathcal{O}(1/n)$, where $n$ is the number of parties. In this work, we build an adaptively secure LRSS that offers an interesting trade-off between rate, leakage rate, and the total number of shares from which an adversary can obtain leakage. As a special case, when considering $t$-out-of-$n$ secret sharing schemes for threshold $t = \alpha n$ (constant $0&lt;\alpha&lt;1$), we build a scheme with constant rate, constant leakage rate, and allow the adversary leakage from all but $t-1$ of the shares, while giving her the remaining $t-1$ shares completely in the clear. (Prior to this, constant rate LRSS scheme tolerating adaptive leakage was unknown for \textit{any} threshold.)

Finally, we show applications of our techniques to both non-malleable secret sharing and secure message transmission.



***

