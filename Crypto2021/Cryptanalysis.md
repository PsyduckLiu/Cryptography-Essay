# Cryptanalysis

## 1. Differential-Linear Cryptanalysis from an Algebraic Perspective

The differential-linear cryptanalysis is an important cryptanalytic tool in cryptography, and has been extensively researched since its discovery by Langford and Hellman in 1994. There are nevertheless very few methods to study the middle part where the differential and linear trail connect. In this paper, we study differential-linear cryptanalysis from an algebraic perspective. We first introduce a technique called Differential Algebraic Transitional Form (DATF) for differential-linear cryptanalysis, then develop a new theory of estimation of the differential-linear bias and techniques for key recovery in differential-linear cryptanalysis.

The techniques are applied to the CAESAR and LWC finalist ASCON, the AES finalist Serpent, and the eSTREAM finalist Grain v1. The bias of the differential-linear approximation is estimated for ASCON and Serpent. The theoretical estimates of the bias are more accurate than that obtained by the Differential-Linear Connectivity Table (Bar-On et al., EUROCRYPT 2019), and the techniques can be applied with more rounds. Our general techniques can also be used to estimate the bias of Grain v1 in differential cryptanalysis, and have a markedly better performance than the Differential Engine tool tailor-made for the cipher. The improved key recovery attacks on round-reduced variants of these ciphers are then proposed. To the best of our knowledge, they are thus far the best known cryptanalysis of Serpent, as well as the best differential-linear cryptanalysis of ASCON and the best initialization analysis of Grain v1. The results have been fully verified by experiments. Notably, security analysis of Serpent is one of the most important applications of differential-linear cryptanalysis in the last two decades. The results in this paper update the differential-linear cryptanalysis of Serpent-128 and Serpent-256 with one more round after the work of Biham, Dunkelman and Keller in 2003.



***

## 2. Meet-in-the-Middle Attacks Revisited: Key-recovery, Collision, and Preimage Attacks

At EUROCRYPT 2021, Bao et al. proposed an automatic method for systematically exploring the configuration space of meet-in-the-middle (MITM) preimage attacks. We further extend it into a constraint-based framework for finding exploitable MITM characteristics in the context of key-recovery and collision attacks by taking the subtle peculiarities of both scenarios into account. Moreover, to perform attacks based on MITM characteristics with nonlinear constrained neutral words, which have not been seen before, we present a procedure for deriving the solution spaces of neutral words without solving the corresponding nonlinear equations or increasing the overall time complexities of the attack. We apply our method to concrete symmetric-key primitives, including SKINNY, ForkSkinny, Romulus, Saturnin, Grostl, and Whirlpool. As a result, we identify the first 23-round key-recovery attack on SKINNY-n-3n and the first 24-round key-recovery attack on ForkSkinny-n-3n in the single-key model with extremely low memories. Moreover, improved (pseudo) preimage or collision attacks on Whirlpool and Grostl are obtained. The source code for generating these attacks is publicly available.



***

## 3. Revisiting the Security of DbHtS MACs: Beyond-Birthday-Bound in the Multi-User Setting

Double-block Hash-then-Sum (\textsf{DbHtS}) MACs are a class of MACs that aim for achieving beyond-birthday-bound security, including \textsf{SUM-ECBC}, \textsf{PMAC\_Plus}, \textsf{3kf9} 
and \textsf{LightMAC\_Plus}. Recently Datta et al. (FSE'19), and then Kim et al. (Eurocrypt'20) prove that \textsf{DbHtS} constructions are secure beyond the birthday bound in the single-user setting. 
However, by a generic reduction, their results degrade to (or even worse than) the birthday bound in the multi-user setting. 

In this work, we revisit the security of \textsf{DbHtS} MACs in the multi-user setting. We propose a generic framework to prove beyond-birthday-bound security for \textsf{DbHtS} constructions. 
We demonstrate the usability of this framework with applications to key-reduced variants of \textsf{DbHtS} MACs, including \textsf{2k-SUM-ECBC}, \textsf{2k-PMAC\_Plus} and \textsf{2k-LightMAC\_Plus}. Our results show that the security of these constructions will not degrade as the number of users grows. On the other hand, our results also indicate that these constructions are secure beyond the birthday bound in both single-user and multi-user setting without additional domain separation, which are used in prior works to simplify the analysis.

Moreover, we find a severe flaw in \textsf{2kf9}, which is proved to be secure beyond the birthday bound by Datta et al. (FSE'19). We can successfully forge a tag with probability 1 without making any queries. We go further to show attacks with birthday-bound complexity on several variants of \textsf{2kf9}.



***

## 4. Thinking Outside the Superbox

Designing a block cipher or cryptographic permutation can be approached in many different ways. One such approach, popularized by AES, consists in grouping the bits along the S-box boundaries, e.g., in bytes, and in consistently processing them in these groups. This aligned approach leads to hierarchical structures like superboxes that make it possible to reason about the differential and linear propagation properties using combinatorial arguments. In contrast, an unaligned approach avoids any such grouping in the design of transformations. However, without hierarchical structure, sophisticated computer programs are required to investigate the differential and linear propagation properties of the primitive. In this paper, we formalize this notion of alignment and study four primitives that are exponents of different design strategies. We propose a way to analyze the interactions between the linear and the nonlinear layers w.r.t. the differential and linear propagation, and we use it to systematically compare the four primitives using non-trivial computer experiments. We show that alignment naturally leads to different forms of clustering, e.g., of active bits in boxes, of two-round trails in activity patterns, and of trails in differentials and linear approximations.



***

## 5. Cryptanalysis of Full LowMC and LowMC-M with Algebraic Techniques

In this paper, we revisit the difference enumeration techniques for LowMC and develop new algebraic techniques to achieve efficient key-recovery attacks with negligible memory complexity. \mbox{Benefiting} from our technique to reduce the memory complexity, we could significantly improve the attacks on LowMC when the block size is much larger than the key size and even break LowMC with such a kind of parameter. On the other hand, with our new key-recovery technique, we could significantly improve the time to retrieve the full key if given only a single pair of input and output messages together with the difference trail that they take, which was stated as an interesting question by Rechberger et al. in ToSC 2018. Combining both the techniques, with only 2 chosen plaintexts, we could break 4 rounds of LowMC adopting a full S-Box layer with block size of 129, 192 and 255 bits, respectively, which are the 3 recommended parameters for Picnic3, an alternative \mbox{third-round} candidate in NIST's Post-Quantum Cryptography competition. We have to emphasize that our attacks do not indicate that Picnic3 is broken as the Picnic use-case is very different and an attacker cannot even freely choose 2 plaintexts to encrypt for a concrete LowMC instance. However, such parameters are deemed as secure in the latest LowMC. Moreover, much more rounds of seven instances of the backdoor cipher \mbox{LowMC-M} as proposed by Peyrin and Wang in CRYPTO 2020 can be broken without finding the backdoor by making full use of the allowed $2^{64}$ data. The above mentioned attacks are all achieved with negligible memory.



***

## 6. The Cost to Break SIKE: A Comparative Hardware-Based Analysis with AES and SHA-3

This work presents a detailed study of the classical security of the post-quantum supersingular isogeny key encapsulation (SIKE) protocol using a realistic budget-based cost model that considers the actual computing and memory costs that are needed for cryptanalysis. In this effort, we design especially-tailored hardware accelerators for the time-critical multiplication and isogeny computations that we use to model an ASIC-powered instance of the van Oorschot-Wiener (vOW)
parallel collision search algorithm. We then extend the analysis to AES and SHA-3 in the context of the NIST post-quantum cryptography standardization process to carry out a parameter analysis based on our cost model. This analysis, together with the state-of-the-art quantum security
analysis of SIKE, indicates that the current SIKE parameters offer higher practical security than currently believed, closing an open issue on the suitability of the parameters to match NIST's security levels. In addition, we explore the possibility of using significantly smaller primes to enable
more efficient and compact implementations with reduced bandwidth. Our improved cost model and analysis can be applied to other cryptographic settings and primitives, and can have implications for other post-quantum candidates in the NIST process.



***

## 7. Improved torsion-point attacks on SIDH variants

SIDH is a post-quantum key exchange algorithm based on the presumed difficulty of finding isogenies between supersingular elliptic curves. However, the exact hardness assumption upon which SIDH relies is not the pure isogeny problem; attackers are also provided with the restriction of the secret isogeny to a subgroup of the curve. Petit [28] leverages this information to break overstretched variants of SIDH in polynomial time, thus demonstrating that exploiting torsion-point information can lead to efficient attacks in some cases. The contribution of this paper is twofold: First, we revisit the techniques of [28] and show how to additionally exploit information coming from a dual and a Frobenius isogeny. We give the full range of parameters to which our attacks apply, an especially interesting instance of which is n-party group key agreement [2]. For 6 or more parties our attack runs in polynomial time and for 3 or more parties our quantum attack improves on the best known asymptotic complexity. We also provide a Magma implementation of our attack for 6 parties. Second, we construct SIDH variants designed to be weak against our attacks; this includes trapdoor choices of starting curve as well as trapdoor choices of base field prime. We stress that our results do not reveal any weakness in the NIST submission SIKE [17].

