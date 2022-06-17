# Quantum Cryptography 1

## 1. A Black-Box Approach to Post-Quantum Zero-Knowledge in Constant Rounds

zero-knowledge

In a recent seminal work, Bitansky and Shmueli (STOC '20) gave the first construction of a constant round zero-knowledge argument for NP secure against quantum attacks. However, their construction has several drawbacks compared to the classical counterparts. Specifically, their construction only achieves computational soundness, requires strong assumptions of quantum hardness of learning with errors (QLWE assumption) and the existence of quantum fully homomorphic encryption (QFHE), and relies on non-black-box simulation. In this paper, we resolve these issues at the cost of weakening the notion of zero-knowledge to what is called ϵ-zero-knowledge. Concretely, we construct the following protocols:

- We construct a constant round interactive proof for NP that satisfies statistical soundness and black-box ϵ-zero-knowledge against quantum attacks assuming the existence of collapsing hash functions, which is a quantum counterpart of collision-resistant hash functions. Interestingly, this construction is just an adapted version of the classical protocol by Goldreich and Kahan (JoC '96) though the proof of ϵ-zero-knowledge property against quantum adversaries requires novel ideas.

- We construct a constant round interactive argument for NP that satisfies computational soundness and black-box ϵ-zero-knowledge against quantum attacks only assuming the existence of post-quantum one-way functions.

At the heart of our results is a new quantum rewinding technique that enables a simulator to extract a committed message of a malicious verifier while simulating verifier's internal state in an appropriate sense.

 

***

## 2. On the Concurrent Composition of Quantum Zero-Knowledge

zero-knowledge、concurrent composition setting

We study the notion of zero-knowledge secure against quantum polynomial-time verifiers (referred to as quantum zero-knowledge) in the concurrent composition setting. 

Despite being extensively studied in the classical setting, concurrent composition in the quantum setting has hardly been studied. \par We initiate a formal study of concurrent quantum zero-knowledge. Our results are as follows:

- Bounded Concurrent QZK for NP and QMA: Assuming post-quantum one-way functions, there exists a quantum zero-knowledge proof system for NP in the bounded concurrent setting. In this setting, we fix a priori the number of verifiers that can simultaneously interact with the prover. Under the same assumption, we also show that there exists a quantum zero-knowledge proof system for QMA in the bounded concurrency setting.

- Quantum Proofs of Knowledge: Assuming quantum hardness of learning with errors (QLWE), there exists a bounded concurrent zero-knowledge proof system for NP satisfying quantum proof of knowledge property. 
Our extraction mechanism simultaneously allows for extraction probability to be negligibly close to acceptance probability (extractability) and also ensures that the prover's state after extraction is statistically close to the prover's state after interacting with the verifier (simulatability).
Even in the standalone setting, the seminal work of [Unruh EUROCRYPT'12], and all its followups, satisfied a weaker version of extractability property and moreover, did not achieve simulatability. Our result yields a proof of {\em quantum knowledge} system for QMA with better parameters than prior works.



***

## 3. Multi-theorem Designated-Verifier NIZK for QMA

Learning with Errors Assumption、non-interactive zero-knowledge(NIZK)、QMA

We present a designated-verifier non-interactive zero-knowledge argument system for QMA with multi-theorem security under the Learning with Errors Assumption. All previous such protocols for QMA are only single-theorem secure. We also relax the setup assumption required in previous works. We prove security in the malicious designated-verifier (MDV-NIZK) model (Quach, Rothblum, and Wichs, EUROCRYPT 2019), where the setup consists of a mutually trusted random string and an untrusted verifier public key. Our main technical contribution is a general compiler that given a NIZK for NP and a quantum sigma protocol for QMA generates an MDV-NIZK protocol for QMA.



***

## 4. On the Round Complexity of Secure Quantum Computation

round complexity

We study the round complexity of maliciously-secure quantum computation in the two-party (2PQC) and multi-party (MPQC) settings. Prior to our work, no constant-round protocols for maliciously-secure 2PQC or MPQC were known. We achieve the following results.

1. Two-Message 2PQC with One-Sided Output. We construct a two-message protocol for two-party quantum computation in the common random string (CRS) model where one party receives output, assuming quantum-secure two-message oblivious transfer (OT). Such an OT protocol is known from the quantum hardness of Learning with Errors (QLWE). Combined with a reusable malicious designated-verifier non-interactive zero-knowledge (MDV-NIZK) argument for NP, the protocol gives an MDV-NIZK for QMA where the prover only requires one copy of the witness state.

2. Constant-Round 2PQC and MPQC. We give the first constructions of maliciously-secure constant-round protocols for two-party and multi-party quantum computation in the CRS model where all parties receive output. 

- Assuming two-message OT in the CRS model, we obtain a three-message protocol for 2PQC and a five-round protocol for MPQC. The five-round protocol only requires three rounds of online communication, giving three-round MPQC in a quantum pre-processing model from two-message OT. 

- Assuming sub-exponentially secure QLWE, we obtain a three-round protocol for 2PQC and a four-round protocol for MPQC, both of which only require two online rounds of communication. This gives two-round MPQC in a quantum pre-processing model from sub-exponential LWE.

3. Preliminary Investigation of Two-Round Protocols. We perform a preliminary investigation into barriers and possible approaches for two-round secure quantum computation without pre-processing. We provide evidence that protocols admitting a natural class of simulators do not exist, and also give a proof-of-concept protocol for two-round MPQC in the common reference string model from virtual black-box (VBB) obfuscation of quantum circuits.



***

## 5. Round Efficient Secure Multiparty Quantum Computation with Identifiable Abort

A recent result by **Dulek et al. (EUROCRYPT 2020)** showed a secure protocol for computing any quantum circuit even without the presence of an honest majority. Their protocol, however, is susceptible to a ``denial of service'' attack and allows even a single corrupted party to force an abort. We propose the first quantum protocol that admits security-with-identifiable-abort, which allows the honest parties to agree on the identity of a corrupted party in case of an abort.

Additionally, our protocol is the first to have the property that the number of rounds where quantum communication is required is independent of the circuit complexity. Furthermore, if there exists a post-quantum secure classical protocol whose round complexity is independent of the circuit complexity, then our protocol has this property as well. Our protocol is secure under the assumption that **classical quantum-resistant fully homomorphic encryption schemes** with decryption circuit of logarithmic depth exist.



***

## 6. One-Way Functions Imply Secure Computation in a Quantum World

We prove that quantum-hard one-way functions imply simulation-secure quantum oblivious transfer (QOT), which is known to suffice for secure computation of arbitrary quantum functionalities. Furthermore, our construction only makes black-box use of the quantum-hard one-way function.

Our primary technical contribution is a construction of extractable and equivocal quantum bit commitments based on the black-box use of quantum-hard one-way functions in the standard model. Instantiating the Crépeau-Kilian (FOCS 1988) framework with these commitments yields simulation-secure quantum oblivious transfer.



***

## 7. Impossibility of Quantum Virtual Black-Box Obfuscation of Classical Circuits

Virtual black-box obfuscation is a strong cryptographic primitive: it encrypts a circuit while maintaining its full input/output functionality. A remarkable result by Barak et al. (Crypto 2001) shows that a general obfuscator that obfuscates classical circuits into classical circuits cannot exist. A promising direction that circumvents this impossibility result is to obfuscate classical circuits into quantum states, which would potentially be better capable of hiding information about the obfuscated circuit. We show that, under the assumption that Learning With Errors (LWE) is hard for quantum computers, this quantum variant of virtual black-box obfuscation of classical circuits is generally impossible. On the way, we show that under the presence of dependent classical auxiliary input, even the small class of classical point functions cannot be quantum virtual black-box obfuscated.