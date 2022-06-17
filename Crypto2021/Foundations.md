# Foundations

## 1. White Box Traitor Tracing

Traitor tracing aims to identify the source of leaked decryption keys. Since the ``traitor'' can try to hide their key within obfuscated code in order to evade tracing, the tracing algorithm should work for general, potentially obfuscated, decoder \emph{programs}. In the setting of such general decoder programs, prior work uses \emph{black box} tracing: the tracing algorithm ignores the implementation of the decoder, and instead traces just by making queries to the decoder and observing the outputs.
	
We observe that, in some settings, such black box tracing leads to consistency and user privacy issues. On the other hand, these issues do not appear inherent to \emph{white box} tracing, where the tracing algorithm actually inspects the decoder implementation. We therefore develop new white box traitor tracing schemes providing consistency and/or privacy. Our schemes can be instantiated under various assumptions ranging from public key encryption to indistinguishability obfuscation, with different trade-offs. To the best of our knowledge, ours is the first work to consider white box tracing in the general decoder setting.



***

## 2. Does Fiat-Shamir Require a Cryptographic Hash Function?

The Fiat-Shamir transform is a general method for reducing interaction in public-coin protocols by replacing the random verifier messages with deterministic hashes of the protocol transcript. The soundness of this transformation is usually heuristic and lacks a formal security proof. Instead, to argue security, one can rely on the random oracle methodology, which informally states that whenever a random oracle soundly instantiates Fiat-Shamir, a hash function that is ``sufficiently unstructured'' (such as fixed-length SHA-2) should suffice. Finally, for some special interactive protocols, it is known how to (1) isolate a concrete security property of a hash function that suffices to instantiate Fiat-Shamir and (2) build a hash function satisfying this property under a cryptographic assumption such as Learning with Errors.

In this work, we abandon this methodology and ask whether Fiat-Shamir truly requires a cryptographic hash function. Perhaps surprisingly, we show that in two of its most common applications --- building signature schemes as well as (general-purpose) non-interactive zero-knowledge arguments --- there are sound Fiat-Shamir instantiations using extremely simple and non-cryptographic hash functions such as sum-mod-$p$ or bit decomposition. In some cases, we make idealized assumptions (i.e., we invoke the generic group model), while in others, we prove soundness in the plain model.

On the negative side, we also identify important cases in which a cryptographic hash function is provably necessary to instantiate Fiat-Shamir. We hope this work leads to an improved understanding of the precise role of the hash function in the Fiat-Shamir transformation.



***

## 3. Composition with Knowledge Assumptions

Zero-knowledge succinct non-interactive arguments (zk-SNARKs) rely on knowledge assumptions for their security. Meanwhile, as the complexity and scale of cryptographic systems continues to grow, the composition of secure protocols is of vital importance. The current gold standards of composable security, the Universal Composability and Constructive Cryptography frameworks cannot capture knowledge assumptions, as their core proofs of composition prohibit white-box extraction. In this paper, we present a formal model allowing the composition of knowledge assumptions. Despite showing impossibility for the general case, we demonstrate the model’s usefulness when limiting knowledge assumptions to few instances of protocols at a time. We finish by providing the first instance of a simultaneously succinct and composable zk-SNARK, by using existing results within our framework.



***

## 4. Non-Interactive Batch Arguments for NP from Standard Assumptions

We study the problem of designing *non-interactive batch arguments* for NP. Such an argument system allows an efficient prover to prove multiple $\npol$ statements, with size much smaller than the combined witness length. 

We provide the first construction of such an argument system for NP in the common reference string model based on standard cryptographic assumptions. Prior works either require non-falsifiable assumptions (or the random oracle model) or can only support private verification.


At the heart of our result is a new *dual mode* interactive batch argument system for NP. We show how to apply the correlation-intractability framework for Fiat-Shamir -- that has primarily been applied to proof systems -- to such interactive arguments.



***

## 5. Targeted Lossy Functions and Applications

Lossy trapdoor functions, introduced by Peikert and Waters (STOC '08), can be initialized in one of two indistinguishable modes: in injective mode, the function preserves all information about its input, and can be efficiently inverted given a trapdoor, while in lossy mode, the function loses some information about its input. Such functions have found countless applications in cryptography, and can be constructed from a  variety of Cryptomania assumptions.  In this work, we introduce \emph{targeted lossy functions (TLFs)}, which relax lossy trapdoor functions along two orthogonal dimensions. Firstly,  they do not require an inversion trapdoor in injective mode. Secondly, the lossy mode of the function is initialized with some target input, and the function is only required to lose information about this particular target. The injective and lossy modes should be indistinguishable even given the target.  We  construct TLFs from Minicrypt assumptions, namely, injective pseudorandom generators, or even one-way functions under a natural relaxation of injectivity.  We then generalize TLFs to  incorporate \emph{branches}, and construct \emph{all-injective-but-one} and \emph{all-lossy-but-one} variants. We show a wide variety of applications of targeted lossy functions. In several cases, we get the first Minicrypt constructions of primitives that were previously only known under Cryptomania assumptions.  Our applications include:
        \begin{itemize}
        	\item  \emph{Pseudo-entropy functions}
                  from one-way functions.
        	\item Deterministic leakage-resilient message-authentication codes and improved leakage-resilient symmetric-key encryption from one-way functions. 
        	\item Extractors for \emph{extractor-dependent sources} 
        	       from one-way functions. 
        	\item Selective-opening secure symmetric-key encryption from one-way functions. 
        	\item A new construction of CCA PKE from (exponentially secure) trapdoor functions and injective pseudorandom generators. 
        \end{itemize}
        We also discuss a fascinating connection to distributed point functions.



***

## 6. The $t$-wise Independence of Substitution-Permutation Networks

This paper promotes and continues a research program aimed at {\em proving} the security of block ciphers such as AES against important and well-studied classes of attacks. In particular, we initiate the study of (almost) $t$-wise independence of concrete block-cipher  construction paradigms such as substitution-permutation networks and key-alternating ciphers. This is a meaningful target, as sufficiently strong (almost) pairwise independence already suffices to resist (truncated) differential attacks and linear cryptanalysis. Our results are two-fold.

\begin{enumerate}
\item 
Our first result concerns substitution-permutation networks (SPNs) that model block ciphers such as AES. We prove the {\em almost pairwise-independence} of an SPN instantiated with a concrete S-box such as the patched inverse function $x \mapsto x^{-1}$ as well as an appropriate linear mixing layer, given sufficiently many rounds and independent sub-keys. Our proof relies on a {\em characterization} of S-box computation on input differences in terms of sampling output differences from certain sub-spaces, and a new randomness extraction lemma (which we prove with Fourier-analytic techniques) that establishes when such sampling yields uniformity. 

\item 
Secondly, we show that  instantiating a key-alternating cipher (which can be thought of as a degenerate case of SPNs) with most permutations gives us (almost) $t$-wise independence in $t + o(t)$ rounds. In order to do this, we use the probabilistic method to develop two new lemmas, an independence-amplification lemma and a distance amplification lemma, that allow us to reason about the evolution of key-alternating ciphers. 

\end{enumerate}