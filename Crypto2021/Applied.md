# Applied Cryptography and Side Channels

## 1. Provable Security Analysis of FIDO2

We carry out the first provable security analysis of the new FIDO2 protocols, the promising FIDO Alliance’s proposal for a standard for passwordless user authentication. Our analysis covers the core components of FIDO2: the W3C’s Web Authentication (WebAuthn) specification and the new Client-to-Authenticator Protocol (CTAP2).

Our analysis is modular. For WebAuthn and CTAP2, in turn, we propose appropriate security models that aim to capture their intended security goals and use the models to analyze their security. First, our proof confirms the authentication security of WebAuthn. Then, we show CTAP2 can only be proved secure in a weak sense; meanwhile, we identify a series of its design flaws and provide suggestions for improvement. To withstand stronger yet realistic adversaries, we propose a generic protocol called sPACA and prove its strong security; with proper instantiations, sPACA is also more efficient than CTAP2. Finally, we analyze the overall security guarantees provided by FIDO2 and WebAuthn+sPACA based on the security of their components.

We expect that our models and provable security results will help clarify the security guarantees of the FIDO2 protocols. In addition, we advocate the adoption of our sPACA protocol as a substitute for CTAP2 for both stronger security and better performance.



***

## 2. SSE and SSD: Page-Efficient Searchable Symmetric Encryption

Searchable Symmetric Encryption (SSE) enables a client to outsource a database to an untrusted server, while retaining the ability to securely search the data. The performance bottleneck of classic SSE schemes typically does not come from their fast, symmetric cryptographic operations, but rather from the cost of memory accesses. To address this issue, many works in the literature have considered the notion of locality, a simple design criterion that helps capture the cost of memory accesses in traditional storage media, such as Hard Disk Drives (HDDs). A common thread among many SSE schemes aiming to improve locality is that they are built on top of new memory allocation schemes, which form the technical core of the constructions.
The starting observation of this work is that for newer storage media such as Solid State Drives (SSDs), which have become increasingly common, locality is not a good predictor of practical performance. Instead, SSD performance mainly depends on page efficiency, that is, reading as few pages as possible. We define this notion, and identify a simple allocation problem, Data-Independent Packing, that captures the main technical challenge required to build page-efficient SSE. As our main result, we build a page-efficient and storage-efficient data-independent packing scheme, and deduce an SSE scheme with the same properties. The technical core of the result relies on a new generalization of cuckoo hashing to items of variable size. Practical experiments show that this approach achieves excellent performance.



***

## 3. Towards Tight Random Probing Security

Proving the security of masked implementations in theoretical models that are relevant to practice and match the best known attacks of the side-channel literature is a notoriously hard problem. The random probing model is a good candidate to contribute to this challenge, due to its ability to capture the continuous nature of physical leakage (contrary to the threshold probing model), while also being convenient to manipulate in proofs and to automate with verification tools. Yet, despite recent progresses in the design of masked circuits with good asymptotic security guarantees in this model, existing results still fall short when it comes to analyze the security of concretely useful circuits under realistic noise levels and with low number of shares. In this paper, we contribute to this issue by introducing a new composability notion, the Probe Distribution Table (PDT), and a new tool (called STRAPS, for the Sampled Testing of the RAndom Probing Security). Their combination allows us to significantly improve the tightness of existing analyses in the most practical (low noise, low number of shares) region of the design space. We illustrate these improvements by quantifying the random probing security of an AES S-box circuit, masked with the popular multiplication gadget of Ishai, Sahai and Wagner from Crypto 2003, with up to six shares.



***

## 4. Secure Wire Shuffling in the Probing Model

In this paper we describe the first improvement of the shuffling countermeasure against side-channel attacks described by Ishai, Sahai and Wagner at Crypto 2003. More precisely, we show how to get worst case statistical security against t probes with running time O(t) instead of O(t log t); our construction is also much simpler. Recall that the classical masking countermeasure achieves perfect security but with running time O(t^2). We also describe a practical implementation for AES that outperforms the masking countermeasure for t ≥ 6 000.