## Zero-Knowledge

## 1. Witness Authenticating NIZKs and Applications

We initiate the study of witness authenticating NIZK  proof systems (WA-NIZKs), in which one can use a witness $w$ of a statement $x$ to identify whether a valid proof for $x$ is indeed generated using $w$.  Such a new identification functionality also puts new requirements on soundness that (1) no adversary can generate a valid proof that will not be identified by any witness; (2) or forge a proof using her valid witness to frame others. 

To work around the obvious obstacle towards conventional zero-knowledgeness, we define entropic zero-knowledgeness that requires the proof to leak no partial information, if the witness is unpredictable, or more precisely, has sufficient computational entropy. 
	
We give a formal treatment of this new primitive. The modeling turns out to be quite involved and multiple subtle  points arise and particular cares are required. We present general constructions from standard assumptions. We also demonstrate three applications in non-malleable (perfect one-way) hash, group signatures with verifier-local revocations and plaintext-checkable public-key encryption. Our WA-NIZK provides a new tool to advance the state of the art in all these applications.



***

## 2. Towards a Unified Approach to Black-Box Constructions of Zero-Knowledge Proofs

General-purpose zero-knowledge proofs for all NP languages greatly simplify secure protocol design. However, they inherently require the code of the underlying relation. If the relation contains black-box calls to a cryptographic function, the code of that function must be known in order to use the ZK proof, even if both the relation as well as the proof require only black-box access to the function. Rosulek (CRYPTO'12) shows that non-trivial proofs for even simple statements, such as membership in the range of a one-way function, require non-black-box access.

We propose an alternative approach to bypass Rosulek's impossibility result. Instead of asking for a ZK proof directly for the given one-way function f, we seek to construct a new one-way function F given only black-box access to f, and an associated ZK protocol for proving non-trivial statements, such as range membership, over its output. We say that F, along with its proof system, is a proof-based one-way function. We similarly define proof-based versions of other primitives, specifically, pseudorandom generators and collision-resistant hash functions.

We show how to construct proof-based versions of each of the aforementioned primitives from their ordinary counterparts under mild restrictions over the input. More specifically,
\begin{itemize}
\item 
We first show that if the input is entirely chosen by the prover, then proof-based pseudorandom generators cannot be constructed from ordinary ones in a black-box manner, thus establishing that some restrictions over the input are necessary.
\item 
We next present black-box constructions handling inputs of the form  (x,r) where r is chosen uniformly by the verifier. This is similar to the restrictions in the widely used Goldreich-Levin theorem. The associated ZK proofs support range-membership over the output as well as arbitrary predicates over prefixes of the input.
\end{itemize}

Our results open up the possibility that general-purpose ZK proofs for relations that require black-access to the aforementioned primitives may be possible in future without violating their black-box nature, by instantiating them using proof-based primitives instead of ordinary ones.



***

## 3. Compressing Proofs of k-Out-Of-n Partial Knowledge

In an (honest-verifier) zero-knowledge proof of partial knowledge, introduced by Cramer, Damg{\aa}rd and Schoenmakers (CRYPTO 1994), a prover knowing witnesses for some $k$-subset of $n$ given public statements can convince the verifier of this claim without revealing which $k$-subset.
The accompanying solution cleverly combines $\Sigma$-protocol theory and linear secret sharing, and achieves linear communication complexity for general $k,n$.
Especially the ``one-out-of-$n$'' case $k=1$ has seen myriad applications during the last decades, e.g., in electronic voting, ring signatures, and confidential transaction systems in general.

In this paper we focus on the discrete logarithm (DL) setting, where the prover claims knowledge of DLs of $k$-out-of-$n$ given elements. 
Groth and  Kohlweiss (EUROCRYPT 2015) have shown how to solve the special case $k=1$ %, yet arbitrary~$n$, 
with {\em logarithmic} (in $n$) communication, instead of linear as prior work. However, their method %, which is original, 
takes explicit advantage of $k=1$ and does not generalize to $k&gt;1$ without losing all advantage over prior work.
Alternatively, an {\em indirect} approach for solving the considered problem is by translating the $k$-out-of-$n$ relation into a circuit and then applying recent advances in communication-efficient circuit ZK. Indeed, for the $k=1$ case this approach has been highly optimized, e.g., in ZCash.

Our main contribution is a new, simple honest-verifier zero-knowledge proof protocol for proving knowledge of $k$ out of $n$ DLs with {\em logarithmic} communication and {\em for general $k$ and $n$}, without requiring any generic circuit ZK machinery.
Our solution  %deploys a novel twist on 
puts forward a novel extension of the
{\em compressed} $\Sigma$-protocol theory (CRYPTO 2020), which we then utilize to compress a %carefully chosen adaptation of the CRYPTO 1994 approach 
new $\Sigma$-protocol for proving knowledge of $k$-out-of-$n$ DL's down to logarithmic size. The latter $\Sigma$-protocol is inspired by the CRYPTO 1994 approach, but a careful re-design of the original protocol is necessary for the compression technique to apply. 
Interestingly, {\em even for $k=1$ and general $n$} our approach improves prior {\em direct} approaches as it reduces prover complexity without increasing the communication complexity.
Besides the conceptual simplicity, 
we also identify regimes of  
practical relevance where our approach achieves asymptotic and concrete improvements, e.g., in proof size and prover complexity, over the generic approach based on circuit-ZK. 

Finally, we show various extensions and generalizations of our core result. For instance, we extend our protocol to proofs of partial knowledge of Pedersen (vector) commitment openings, and/or to include a proof that the witness satisfies some additional constraint, and we show how to extend our results to non-threshold access structures.



***

## 4. Mac'n'Cheese: Zero-Knowledge Proofs for Boolean and Arithmetic Circuits with Nested Disjunctions

Zero knowledge proofs are an important building block in many cryptographic applications.
    Unfortunately, when the proof statements become very large, existing
    zero-knowledge proof systems easily reach their limits: either the computational
    overhead, the memory footprint, or the required bandwidth exceed levels that
    would be tolerable in practice.

    We present an interactive zero-knowledge proof system for boolean and
    arithmetic circuits, called Mac'n'Cheese, with a focus on supporting large
    circuits. Our work follows the commit-and-prove paradigm instantiated using
    information-theoretic MACs based on vector oblivious linear evaluation to
    achieve high efficiency. We additionally show how to optimize disjunctions,
    with a general OR transformation for proving the disjunction of $m$
    statements that has communication complexity proportional to the longest
    statement (plus an additive term logarithmic in $m$). These disjunctions can
    further be \emph{nested}, allowing efficient proofs about complex statements
    with many levels of disjunctions. We also show how to make Mac'n'Cheese
    non-interactive (after a preprocessing phase) using the Fiat-Shamir
    transform, and with only a small degradation in soundness.
    
    We have implemented the online phase of Mac'n'Cheese and achieve a runtime of 144~ns per AND
    gate and 1.5~$\mu$s per multiplication gate in $\mathbb{F}_{2^{61}-1}$ when run over a network
    with a 95~ms latency and a bandwidth of 31.5~Mbps. In addition, we show that
    the disjunction optimization improves communication as expected: when
    proving a boolean circuit with eight branches and each branch containing
    roughly 1 billion multiplications, Mac'n'Cheese requires only 75 more bytes to
    communicate than in the single branch case.


***

## 5. Time- and Space-Efficient Arguments from Groups of Unknown Order

We construct public-coin time- and space-efficient zero-knowledge arguments for NP. For every time T and space S non-deterministic RAM computation, the prover runs in time T * polylog(T) and space S * polylog(T), and the verifier runs in time n * polylog(T), where n is the input length. Our protocol relies on hidden order groups, which can be instantiated without a trusted setup using class groups, and can heuristically be made non-interactive using the Fiat-Shamir transform.

Our proof builds on DARK (Bunz et al., Eurocrypt 2020), a recent succinct and efficiently verifiable polynomial commitment scheme. We show how to implement a variant of DARK in a time- and space-efficient way. Along the way we:

1. Identify a significant gap in the proof of security of Dark.

2. Give a non-trivial modification of the DARK scheme that overcomes the aforementioned gap. The modified version also relies on significantly weaker cryptographic assumptions than those in the original DARK scheme. Our proof utilizes ideas from the theory of integer lattices in a novel way.

3. Generalize Pietrzak's (ITCS 2019) proof of exponentiation (PoE) protocol to work with general groups of unknown order (without relying on any cryptographic assumption).

In proving these results, we develop general-purpose techniques for working with (hidden order) groups, which may be of independent interest.