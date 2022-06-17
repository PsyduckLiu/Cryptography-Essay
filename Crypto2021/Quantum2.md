# Quantum Cryptography 2

## 1. New Approaches for Quantum Copy-Protection

Quantum copy protection uses the unclonability of quantum states to construct quantum software that provably cannot be pirated. Copy protection would be immensely useful, but unfortunately little is known about how to achieve it in general. In this work, we make progress on this goal, by giving the following results: 

* We show how to copy protect any program that cannot be learned from its input/output behavior, relative to a classical oracle. This improves on Aaronson (CCC 2009), which achieves the same relative to a quantum oracle. By instantiating the oracle with post-quantum candidate obfuscation schemes, we obtain a heuristic construction of copy protection. 
* We show, roughly, that any program which can be watermarked can be copy detected, a weaker version of copy protection that does not prevent copying, but guarantees that any copying can be detected. Our scheme relies on the security of the assumed watermarking, plus the assumed existence of public key quantum money. Our construction is general, applicable to many recent watermarking schemes.



***

## 2. Hidden Cosets and Applications to Unclonable Cryptography

In 2012, Aaronson and Christiano introduced the idea of hidden subspace states to build public-key quantum money [STOC '12]. Since then, this idea has been applied to realize several other cryptographic primitives which enjoy some form of unclonability.
    
In this work, we propose a generalization of hidden subspace states to hidden coset states. We study different unclonable properties of coset states and several applications:

* We show that, assuming indistinguishability obfuscation (iO), hidden coset states possess a certain direct product hardness property, which immediately implies a tokenized signature scheme in the plain model. Previously, a tokenized signature scheme was known only relative to an oracle, from a work of Ben-David and Sattath [QCrypt '17].
  
* Combining a tokenized signature scheme with extractable witness encryption, we give a construction of an unclonable decryption scheme in the plain model. The latter primitive was recently proposed by Georgiou and Zhandry [ePrint '20], who gave a construction relative to a classical oracle.
  
* We conjecture that coset states satisfy a certain natural monogamy-of-entanglement property. Assuming this conjecture is true, we remove the requirement for extractable witness encryption in our unclonable decryption construction. As potential evidence in support of the conjecture, we prove a weaker version of this monogamy property, which we believe will still be of independent interest. 

* Finally, we give the first construction of a copy-protection scheme for pseudorandom functions (PRFs) in the plain model. Our scheme is secure either assuming iO and extractable witness encryption, or iO, LWE and the conjectured monogamy property mentioned above. This is the first example of a copy-protection scheme with provable security in the plain model for a class of functions that is not evasive.



***

## 3. On Tight Quantum Security of HMAC and NMAC in the Quantum Random Oracle Model

HMAC and NMAC are the most basic and important constructions to convert Merkle-Damgrd hash functions into message authentication codes (MACs) or pseudorandom functions (PRFs).
In the quantum setting, at CRYPTO~2017, Song and Yun showed that HMAC and NMAC are quantum pseudorandom functions (qPRFs) under the standard assumption that the underlying compression function is a qPRF.
Their proof guarantees security up to $O(2^{n/5})$ or $O(2^{n/8})$ quantum queries when the output length of HMAC and NMAC is $n$ bits.
However, there is a gap between the provable security bound and a simple distinguishing attack that uses $O(2^{n/3})$ quantum queries. 
This paper settles the problem of closing the gap.
We show that the tight bound of the number of
quantum queries to distinguish HMAC or NMAC from a random function
is $\Theta(2^{n/3})$ in the quantum random oracle model,
where compression functions are modeled as quantum random oracles.
To give the tight quantum bound,
based on an alternative formalization of Zhandry's compressed oracle technique,
we introduce a new proof technique focusing on the symmetry of quantum query records.



***

## 4. Quantum Collision Attacks on Reduced SHA-256 and SHA-512

In this paper, we for the first time show dedicated quantum collision attacks on SHA-256 and SHA-512.
The attacks reach 38 and 39 steps, respectively, which significantly improve the classical attacks for 31 and 27 steps.
Both attacks adopt the framework of the previous work that converts many semi-free-start collisions into a 2-block collision, and are faster than the generic attack in the cost metric of time-space tradeoff.
We observe that the number of required semi-free-start collisions can be reduced in the quantum setting, which allows us to convert the previous classical 38 and 39 step semi-free-start collisions into a collision.
The idea behind our attacks is simple and will also be applicable to other cryptographic hash functions.