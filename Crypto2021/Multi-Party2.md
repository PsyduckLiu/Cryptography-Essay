# Multi-Party Computation 2

## 1. Broadcast-Optimal Two Round MPC with an Honest Majority

This paper closes the question of the possibility of two-round MPC protocols achieving different security guarantees with and without the availability of broadcast in any given round. Cohen et al. (Eurocrypt 2020) study this question in the dishonest majority setting; we complete the picture by studying the honest majority setting.

In the honest majority setting, given broadcast in both rounds, it is known that the strongest guarantee — guaranteed output delivery — is achievable (Gordon et al. Crypto 2015). We show that, given broadcast in the first round only, guaranteed output delivery is still achievable. Given broadcast in the second round only, we give a new construction that achieves identifiable abort, and we show that fairness — and thus guaranteed output delivery — are not achievable in this setting. Finally, if only peer-to-peer channels are available, we show that the weakest guarantee — selective abort — is the only one achievable for corruption thresholds t &gt; 1 and for t = 1 and n = 3. On the other hand, it is already known that selective abort can be achieved in these cases. In the remaining cases, i.e., t = 1 and n &gt; 3, it is known (from the work of Ishai et al. at Crypto 2010, and Ishai et al. at Crypto 2015) that guaranteed output delivery (and thus all weaker guarantees) are possible.



***

## 2. Three-Round Secure Multiparty Computation from Black-Box Two-Round Oblivious Transfer

We give constructions of three-round secure multiparty computation (MPC) protocols for general functions that make {\it black-box} use of a two-round oblivious transfer (OT). For the case of semi-honest adversaries, we make use of a two-round, semi-honest secure OT in the plain model. This resolves the round-complexity of black-box (semi-honest) MPC protocols from minimal assumptions and answers an open question of Applebaum et al. (ITCS 2020). For the case of malicious adversaries, we make use of a two-round maliciously-secure OT in the common random/reference string model that satisfies a (mild) variant of adaptive security for the receiver.



***

## 3. On the Round Complexity of Black-Box Secure MPC

We consider the question of minimizing the round complexity of secure multiparty computation (MPC) protocols that make a black-box use of simple cryptographic primitives in the setting of security against any number of malicious parties. In the plain model, previous black-box protocols required a high constant number of rounds (&gt;15). This is far from the known lower bound of 4 rounds for protocols with black-box simulators. 

When allowing a random oblivious transfer (OT) correlation setup, 2-round protocols making a black-box use of a pseudorandom generator were previously known. However, such protocols were obtained via a round-collapsing ``protocol garbling'' technique that has poor concrete efficiency and makes a non-black-box use of an underlying malicious-secure protocol.

We improve this state of affairs by presenting the following types of black-box protocols. 

a. 4-round ``pairwise MPC'' in the plain model. 
This round-optimal protocol enables each ordered pair of parties to compute a function of both inputs whose output is delivered to the second party. The protocol makes black-box use of any public-key encryption (PKE) with pseudorandom public keys. As a special case, we get a  black-box round-optimal realization of secure (copies of) OT between every ordered pair of parties.
    
b. 2-round MPC from OT correlations. 
This round-optimal protocol makes a black-box use of any general 2-round MPC protocol satisfying an augmented notion of semi-honest security. In the two-party case, this yields new kinds of 2-round black-box protocols.  
    
c. 5-round MPC in the plain model. 
This protocol makes a black-box use of PKE with pseudorandom public keys, and 2-round oblivious transfer with ``semi-malicious'' security. 

A key technical tool for the first result is a novel combination of split-state non-malleable codes (Dziembowski, Pietrzak, and Wichs, JACM '18) with standalone secure {\em two-party} protocols. The second result is based on a new round-optimized variant of the ``IPS compiler'' (Ishai, Prabhakaran and Sahai, Crypto '08). The third result is obtained via a specialized combination of these two techniques.



***

## 4. ATLAS: Efficient and Scalable MPC in the Honest Majority Setting

In this work, we address communication, computation, and round efficiency of unconditionally secure multi-party computation for arithmetic circuits in the honest majority setting. We achieve both algorithmic and practical improvements: 

 - The best known result in the semi-honest setting has been due to Damgard and Nielsen (CRYPTO 2007). Over the last decade, their construction has played an important role in the progress of efficient secure computation. However despite a number of follow-up works, any significant improvements to the basic semi-honest protocol have been hard to come by. We show 33% improvement in communication complexity of this protocol. We show how to generalize this result to the malicious setting, leading to the best known unconditional honest majority MPC with malicious security. 

 - We focus on the round complexity of the Damgard and Nielsen protocol and improve it by a factor of 2. Our improvement relies on a novel observation relating to an interplay between Damgard and Nielsen multiplication and Beaver triple multiplication. An implementation of our constructions shows an execution run time improvement compared to the state of the art ranging from 30% to 50%.



***

## 5. Unconditional Communication-Efficient MPC via Hall's Marriage Theorem

The best known n party unconditional multiparty computation protocols with an optimal corruption threshold communicates O(n) field elements per gate. This has been the case even in the semi-honest setting despite over a decade of research on communication complexity in this setting. Going to the slightly sub-optimal corruption setting, the work of Damgard, Ishai, and Kroigaard (EUROCRYPT 2010) provided the first protocol for a single circuit achieving communication complexity of O(log|C| * n/k) elements per gate. While a number of works have improved upon this result, obtaining a protocol with O(1) field elements per gate has been an open problem.

In this work, we construct the first unconditional multi-party computation protocol evaluating a single arithmetic circuit with amortized communication complexity of O(n/k) or O(1) elements per gate for k=\Omega(n) with corruption threshold t'=(n-1)/2-k+1.



***

## 6. Non-Interactive Secure Multiparty Computation for Symmetric Functions, Revisited: More Efficient Constructions and Extensions

Non-interactive secure multiparty computation (NIMPC) is a variant of secure computation which allows each of $n$ players to send only a single message depending on his input and correlated randomness.
Abelian programs, which can realize any symmetric function, are defined as functions on the sum of the players' inputs over an abelian group and provide useful functionalities for real-world applications.
We improve and extend the previous results in the following ways:
\begin{itemize}
\item We present NIMPC protocols for abelian programs that improve the best known communication complexity.
If inputs take any value of an abelian group $\mathbb{G}$, our protocol achieves the communication complexity $O(|\mathbb{G}|(\log|\mathbb{G}|)^2)$ improving $O(|\mathbb{G}|^2n^2)$ of Beimel et al. (Crypto 2014).
If players are limited to inputs from subsets of size at most $d$, our protocol achieves $|\mathbb{G}|(\log|\mathbb{G}|)^2(\max\{n,d\})^{(1+o(1))t}$ where $t$ is a corruption threshold.
This result improves $|\mathbb{G}|^3(nd)^{(1+o(1))t}$ of Beimel et al. (Crypto 2014), and even $|\mathbb{G}|^{\log n+O(1)}n$ of Benhamouda et al. (Crypto 2017) if $t=o(\log n)$ and $|\mathbb{G}|=n^{\Theta(1)}$.

\item We propose for the first time NIMPC protocols for linear classifiers that are more efficient than those obtained from the generic construction.

\item We revisit a known transformation of Benhamouda et al. (Crypto 2017) from Private Simultaneous Messages (PSM) to NIMPC, which we repeatedly use in the above results.
We reveal that a sub-protocol used in the transformation does not satisfy the specified security.
We also fix their protocol with only constant overhead in the communication complexity.
As a byproduct, we obtain an NIMPC protocol for indicator functions with asymptotically optimal communication complexity with respect to the input length.
\end{itemize}



***

## 7. Efficient Information-Theoretic Multi-Party Computation over Non-Commutative Rings

We construct the first efficient MPC protocol that only requires black-box access to a non-commutative ring $R$.
Previous results in the same setting were efficient only either for a constant number of corruptions or when computing branching programs and formulas.
Our techniques are based on a generalization of Shamir's secret sharing to non-commutative rings, which we derive from the work on Reed Solomon codes by Quintin, Barbier and Chabot (\textit{IEEE Transactions on Information Theory, 2013}).
When the center of the ring contains a set $A = \{\alpha_0, \ldots, \alpha_n\}$ such that $\forall i \neq j, \alpha_i - \alpha_j \in R^*$, the resulting secret sharing scheme is strongly multiplicative and we can generalize existing constructions over finite fields without much trouble.

Most of our work is devoted to the case where the elements of $A$ do not commute with all of $R$, but they just commute with each other.
For such rings, the secret sharing scheme cannot be linear ``on both sides" and furthermore it is not multiplicative. Nevertheless, we are still able to build MPC protocols with a concretely efficient online phase and black-box access to $R$. As an example we consider the ring $\mathcal{M}_{m\times m}(\mathbb{Z}/2^k\mathbb{Z})$, for which when $m &gt; \log(n+1)$, we obtain protocols that require around $\lceil\log(n+1)\rceil/2$ less communication and $2\lceil\log(n+1)\rceil$ less computation than the state of the art protocol based on  Circuit Amortization Friendly Encodings (Dalskov, Lee and Soria-Vazquez, \textit{ASIACRYPT 2020}).

In this setting with a ``less commutative" $A$, our black-box preprocessing phase has a less practical complexity of $\poly(n)$. Due to this, we additionally provide specialized, concretely efficient preprocessing protocols for $R = \mathcal{M}_{m\times m}(\mathbb{Z}/2^k\mathbb{Z})$ that exploit the structure of the matrix ring.