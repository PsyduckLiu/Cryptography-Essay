# Encryption

## 1. Broadcast Encryption with Size N^{1/3} and More from k-Lin

We present the first pairing-based ciphertext-policy attribute-based encryption (CP-ABE) scheme for the class of degree 3 polynomials with compact parameters: the public key, ciphertext and secret keys comprise O(n) group elements, where n is input length for the function. As an immediate corollary, we obtain a pairing-based broadcast encryption scheme for N users with O(N^1/3)- sized parameters, giving the first significant parameter improvements in pairing- based broadcast encryption in over a decade. All of our constructions achieve adaptive security against unbounded collusions, and rely on the (bilateral) k-Lin assumption in prime-order bilinear groups.



***

## 2. Fine-grained Secure Attribute-based Encryption

Fine-grained cryptography is constructing cryptosystems in a setting where an adversary’s resource is a-prior bounded and an honest party has less resource than an adversary. Currently, only simple form of encryption schemes, such as secret-key and public-key encryption, are constructed in this setting.
In this paper, we enrich the available tools in fine-grained cryptography by proposing the first fine-grained secure attribute-based encryption (ABE) scheme. Our construction is adaptively secure under the widely accepted worst-case assumption, $NC1 \subsetneq \oplus L/poly$, and it is presented in a generic manner using the notion of predicate encodings (Wee, TCC’14). By properly instantiating the underlying encoding, we can obtain different types of ABE schemes, including identity-based encryption. Previously, all of these schemes were unknown in fine-grained cryptography. Our main technical contribution is constructing ABE schemes without using pairing or the Diffie-Hellman assumption. Hence, our results show that, even if one-way functions do not exist, we still have ABE schemes with meaningful security. For more application of our techniques, we construct an efficient (quasi-adaptive) non-interactive zero-knowledge (QA-NIZK) proof system.



***

## 3. Multi-Input Quadratic Functional Encryption from Pairings

We construct the first multi-input functional encryption (MIFE) scheme for quadratic functions from pairings. Our construction supports polynomial number of users, where user $i$, for $i \in [n]$, encrypts input $\bfx_i \in \mbZ^m$ to obtain ciphertext $\ct_i$, the key generator provides a key $\sk_\bfc$ for vector $\bfc \in \mbZ^{({mn})^2}$ and decryption, given $\ct_1,\ldots,\ct_n$ and $\sk_\bfc$, recovers $\ip{\bfc}{\bfx \otimes \bfx}$ and nothing else. We achieve  indistinguishability-based (selective) security against unbounded collusions under the standard bilateral matrix Diffie-Hellman assumption. All previous MIFE schemes either support only inner products (linear functions) or rely on strong cryptographic assumptions such as indistinguishability obfuscation or multi-linear maps.



***

## 4. Functional Encryption for Turing Machines with Dynamic Bounded Collusion from LWE

The classic work of Gorbunov, Vaikuntanathan and Wee (CRYPTO 2012) and follow-ups provided constructions of bounded collusion Functional Encryption (FE) for circuits from mild assumptions. In this work, we improve the state of affairs for bounded collusion FE in several ways:

\begin{enumerate}
\item {\it New Security Notion.} We introduce the notion of  {\it dynamic} bounded collusion FE, where the declaration of collusion bound is delayed to the time of encryption. This enables the encryptor to dynamically choose the collusion bound for different ciphertexts depending on their individual level of sensitivity. Hence, the ciphertext size grows linearly with its own collusion bound and the public key size is independent of collusion bound. In contrast, all prior constructions have public key and ciphertext size that grow at least linearly with a fixed bound $Q$.

\item {\it CPFE for circuits with Dynamic Bounded Collusion.} We provide the first CPFE schemes for circuits enjoying dynamic bounded collusion security. 
By assuming identity based encryption (IBE), we construct CPFE for circuits of {\it unbounded} size satisfying {\it non adaptive} simulation based security. By strengthening the underlying assumption to IBE with receiver selective opening security, we obtain CPFE for circuits of {\it bounded} size, output length and depth enjoying {\it adaptive} simulation based security. Moreover, we show that IBE is a necessary assumption for these primitives.  \\
Moreover, by relying on the Learning With Errors (LWE) assumption, we obtain the first {\it succinct} CPFE for circuits, i.e. supporting circuits with unbounded size, but fixed output length and depth. This scheme achieves {\it adaptive} simulation based security. 

\item {\it KPFE for circuits with dynamic bounded collusion.} We provide the first KPFE for circuits of unbounded size, but bounded depth and output length satisfying dynamic bounded collusion security. Our construction relies on LWE and achieves {\it adaptive} simulation based security. This improves the security of succinct KPFE by Goldwasser et al. \cite{GKPVZ13a}. 

\item {\it KP and CP FE for TM/NL with dynamic bounded collusion.} We provide the first KPFE and CPFE constructions of bounded collusion functional encryption for Turing machines in the public key setting from LWE. Our constructions achieve non-adaptive simulation based security. Both the input and the machine in our construction can be of {\it unbounded} polynomial length but the ciphertext size grows with the upper bound on the running time of the Turing machine on the given input. Given RAM access to the ciphertext, the scheme enjoys input specific decryption time.

We provide a variant of the above scheme that satisfies {\it adaptive} security, but at the cost of supporting a smaller class of computation, namely Nondeterministic Logarithmic-space (NL). Since NL contains Nondeterministic Finite Automata (NFA), this result subsumes {\it all} prior work of bounded collusion FE for uniform models from standard assumptions \cite{AMY19,AS17}. 

\end{enumerate}



***

## 5. Receiver-Anonymity in Rerandomizable RCCA-Secure Cryptosystems Resolved

In this work, we resolve the open problem raised by Prabhakaran and Rosulek at CRYPTO 2007, and present the first anonymous, rerandomizable, Replayable-CCA (RCCA) secure public key encryption scheme. This solution opens the door to numerous privacy-oriented applications with a highly desired RCCA security level. At the core of our construction is a non-trivial extension of smooth projective hash functions (Cramer and Shoup, EUROCRYPT 2002), and a modular generic framework developed for constructing Rand-RCCA-secure encryption schemes with receiver-anonymity. The framework gives an enhanced abstraction of the original Prabhakaran and Rosulek’s scheme (which was the first construction of Rand-RCCA-secure encryption in the standard model), where the most crucial enhancement is the first realization of the desirable property of receiver-anonymity, essential to privacy settings. It also serves as a conceptually more intuitive and generic understanding of RCCA security, which leads, for example, to new implementations of the notion. Finally, note that (since CCA security is not applicable to the privacy applications motivating our work) the concrete results and the conceptual advancement presented here, seem to substantially expand the power and relevance of the notion of Rand-RCCA-secure encryption.