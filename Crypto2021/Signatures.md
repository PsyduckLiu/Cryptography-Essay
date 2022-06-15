# Signatures

## 1. Threshold Schnorr with Stateless Deterministic Signing from Standard Assumptions

门限签名、Schnorr's signature scheme、zero-knowledge from garbled circuits (ZKGC) 

Schnorr's signature scheme permits an elegant threshold signing protocol due to its linear signing equation. However each new signature consumes fresh randomness, which can be a major attack vector in practice. Sources of randomness in deployments are frequently either unreliable, or require state continuity, i.e. reliable fresh state resilient to rollbacks. State continuity is a notoriously difficult guarantee to achieve in practice, due to system crashes caused by software errors, malicious actors, or power supply interruptions (Parno et al., S&P '11). This is a non-issue for Schnorr variants such as EdDSA, which is specified to derive nonces deterministically as a function of the message and the secret key. However, it is challenging to translate these benefits to the threshold setting, specifically to construct a threshold Schnorr scheme where signing neither requires parties to consume fresh randomness nor update long-term secret state.

In this work, we construct a dishonest majority threshold Schnorr protocol that enables such stateless deterministic nonce derivation using standardized block ciphers. Our core technical ingredients are new tools for the zero-knowledge from garbled circuits (ZKGC) paradigm to aid in verifying correct nonce derivation:
- A mechanism based on UC Commitments that allows a prover to commit once to a witness, and prove an unbounded number of statements online with only cheap symmetric key operations.

- A garbling gadget to translate intermediate garbled circuit wire labels to arithmetic encodings.

A proof per our scheme requires only a small constant number of exponentiations.



***

## 2. Two-Round Trip Schnorr Multi-Signatures via Delinearized Witnesses

多方签名、Schnorr-based signature scheme、algebraic group model (AGM) 、random oracle model (ROM)

We construct a two-round Schnorr-based signature scheme (DWMS)   by delinearizing two pre-witnesses supplied by each signer. DWMS is a secure signature scheme in the algebraic group model (AGM) and the random oracle model (ROM) under the assumption of the hardness of the one-more discrete logarithm problem and the 2-entwined sum problem that we introduce in this paper. Our new m-entwined sum problem tweaks the k-sum problem in a scalar field using the associated group. We prove the hardness of our new problem in the AGM assuming the hardness of the discrete logarithm problem in the associated group.  We believe that our new problem simplifies the security proofs of multi-signature schemes that use the delinearization of witnesses.



***

## 3. MuSig2: Simple Two-Round Schnorr Multi-Signatures

多方签名、Schnorr-based signature scheme

Multi-signatures enable a group of signers to produce a single signature on a given message. Recently, Drijvers et al. (S&P’19) showed that all thus far proposed two-round multi-signature schemes in the DL setting (without pairings) are insecure under concurrent signing sessions. While Drijvers et al. propose a secure two-round scheme, this efficiency in terms of rounds comes with the price of having less compact signatures: the signatures are more than twice as large as Schnorr signatures, which are becoming popular in cryptographic systems due to their practicality (e.g., they will likely be adopted by Bitcoin). If one needs a multi-signature scheme that can be used as a drop-in replacement for Schnorr signatures, then one is forced to resort either to a three-round scheme or to sequential signing sessions, both of which are undesirable options in practice.

In this work, we propose MuSig2, a simple and highly practical two-round multi-signature scheme. Our scheme is the first that simultaneously i) is secure under concurrent signing sessions, ii) supports key aggregation, iii) outputs ordinary Schnorr signatures, iv) needs only two communicaion rounds, and v) has similar signer complexity as ordinary Schnorr signatures. Furthermore, our scheme is the first multi-signature scheme in the DL setting that supports preprocessing of all but one rounds, effectively enabling a non-interactive signing process without forgoing security under concurrent sessions. We prove the security of MuSig2 in the random oracle model, and the security of a more efficient variant in the combination of the random oracle and the algebraic group model. Both our proofs rely on a weaker variant of the OMDL assumption.



***

## 4. Tighter Security for Schnorr Identification and Signatures: A High-Moment Forking Lemma for ${\Sigma}$-Protocols

Schnorr-based signature scheme

The Schnorr identification and signature schemes have been amongst the most influential cryptographic protocols of the past three decades. Unfortunately, although the best-known attacks on these two schemes are via  discrete-logarithm computation, the known approaches for basing their security on the hardness of the discrete logarithm problem encounter the ``square-root barrier''. In particular, in any group of order $p$ where Shoup's generic hardness result for the discrete logarithm problem is believed to hold (and is thus used for setting concrete security parameters), the best-known $t$-time attacks on the Schnorr identification and signature schemes  have success probability $t^2/p$, whereas existing proofs of security only rule out attacks with success probabilities $(t^2/p)^{1/2}$ and $(q_{\Hash} \cdot t^2/p)^{1/2}$, respectively, where $q_{\Hash}$ denotes the number of random-oracle queries issued by the attacker.

We establish tighter security guarantees for identification and signature schemes which result from $\Sigma$-protocols with special soundness based on the hardness of their underlying relation, and in particular for Schnorr's schemes based on the hardness of the discrete logarithm problem. We circumvent the square-root barrier by introducing a high-moment generalization of the classic forking lemma, relying on the assumption that the underlying relation is ``$d$-moment hard'': The success probability of any algorithm in the task of producing a witness for a random instance is dominated by the $d$-th moment of the algorithm's running time. 

In the concrete context of the discrete logarithm problem, already Shoup's original proof  shows that the discrete logarithm problem is $2$-moment hard in the generic-group model, and thus our assumption can be viewed as a highly-plausible strengthening of the discrete logarithm assumption in any group where no better-than-generic algorithms are currently known. Applying our  high-moment forking lemma in this context shows that, assuming the $2$-moment hardness of the discrete logarithm problem, any $t$-time attacker breaks the security of the Schnorr identification and signature schemes with probabilities at most $(t^2/p)^{2/3}$ and $(q_\Hash \cdot t^2/p)^{2/3}$, respectively.



***

## 5. DualRing: Generic Construction of Ring Signatures with Efficient Instantiations

环签名、Schnorr identification scheme

We introduce a novel generic ring signature construction, called DualRing, which can be built from several canonical identification schemes (such as Schnorr identification). DualRing differs from the classical ring signatures by its formation of two rings: a ring of commitments and a ring of challenges. It has a structural difference from the common ring signature approaches based on accumulators or zero-knowledge proofs of the signer index. Comparatively, DualRing has a number of unique advantages.

Considering the DL-based setting by using Schnorr identification scheme, our DualRing structure allows the signature size to be compressed into logarithmic size via an argument of knowledge system such as Bulletproofs. We further improve on the Bulletproofs argument system to eliminate about half of the computation while maintaining the same proof size. We call this Sum Argument and it can be of independent interest. This DL-based construction, named DualRing-EC, using Schnorr identification with Sum Argument has the shortest ring signature size in the literature without using trusted setup.

Considering the lattice-based setting, we instantiate DualRing by a canonical identification based on M-LWE and M-SIS. In practice, we achieve the shortest lattice-based ring signature, named DualRing-LB, when the ring size is between 4 and 2000. DualRing-LB is also 5x faster in signing and verification than the fastest lattice-based scheme by Esgin et al. (CRYPTO'19).



***

## 6. Compact Ring Signatures from Learning With Errors

环签名、learning with errors (LWE)

Ring signatures allow a user to sign a message on behalf of a ''ring'' of signers, while hiding the true identity of the signer. As the degree of anonymity guaranteed by a ring signature is directly proportional to the size of the ring, an important goal in cryptography is to study constructions that minimize the size of the signature as a function of the number of ring members. 

In this work, we present the first compact ring signature scheme (i.e., where the size of the signature grows logarithmically with the size of the ring) from the (plain) learning with errors (LWE) problem. The construction is in the standard model and it does not rely on a trusted setup or on the random oracle heuristic. In contrast with the prior work of Backes \etal~[EUROCRYPT'2019], our scheme does not rely on bilinear pairings, which allows us to show that the scheme is post-quantum secure assuming the quantum hardness of LWE. 

At the heart of our scheme is a new construction of compact and statistically witness-indistinguishable ZAP arguments for NP $\cap$ coNP, that we show to be sound based on the plain LWE assumption. Prior to our work, statistical ZAPs (for all of NP) were known to exist only assuming \emph{sub-exponential} LWE. We believe that this scheme might find further applications in the future.