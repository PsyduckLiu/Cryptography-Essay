# Models

## 1. A Rational Protocol Treatment of 51% Attacks

Game-theoretic analysis of cryptocurrencies and, more generally, blockchain-based decentralized ledgers offers insight on their economic robustness, and their behavior when even the cryptographic assumptions that underpin their security fail. In this work we utilize the recently proposed blockchain adaptation of the rational protocol design (RPD) framework [EUROCRYPT~'18] to analyze 51\% double-spending attacks against Nakamoto-style cryptocurrencies. We observe a property of the originally proposed utility class that yields an unnatural behavior against such attacks, and show how to devise a utility that avoids this pitfall and makes predictions that match the observable behavior---i.e., that renders attacking a dominant strategy in settings where an attack was indeed observed. We then propose a generic modification to the underlying protocol which deters attacks on consistency by adversaries controlling a majority of the system's resources, including the 51\% double-spending attack. This can be used as guidance to patch systems that have suffered such attacks, e.g., Ethereum Classic and Bitcoin Cash, and serves as a demonstration of the power of game-theoretic analyses.



***

## 2. MoSS: Modular Security Specifications Framework

Applied cryptographic protocols have to meet a rich set of security requirements under diverse environments and against diverse adversaries. However, currently used security specifications, based on either simulation (e.g., `ideal functionality' in UC) or games, are monolithic, combining together different aspects of protocol requirements, environment and assumptions. Such specifications are complex, error-prone, and foil reusability, modular analysis and incremental design. 

We present the Modular Security Specifications Framework (MoSS) framework, which cleanly separates each security requirement (goal) which a protocol should achieve, from the environment and model (assumptions) under which the requirement should be ensured. This modularity allows us to reuse individual models and requirements across different protocols and tasks, and to compare protocols for the same task, either under different assumptions (models) or satisfying different sets of requirements. 
MoSS is flexible and extendable, e.g., it can support both asymptotic and concrete definitions for security. 

We demonstrate the applicability of MoSS to two applications: secure broadcast protocols and PKI schemes.



***

## 3. Separating Adaptive Streaming from Oblivious Streaming using the Bounded Storage Model

Streaming algorithms are algorithms for processing large data streams, using only a limited amount of memory. Classical streaming algorithms typically work under the assumption that the input stream is chosen independently from the internal state of the algorithm. Algorithms that utilize this assumption are called oblivious algorithms. Recently, there is a growing interest in studying streaming algorithms that maintain utility also when the input stream is chosen by an adaptive adversary, possibly as a function of previous estimates given by the streaming algorithm. Such streaming algorithms are said to be adversarially-robust. 

By combining  techniques from learning theory with cryptographic tools from the bounded storage model, we separate the oblivious streaming model from the adversarially-robust streaming model. Specifically, we present a streaming problem for which every adversarially-robust streaming algorithm must use polynomial space, while there exists a classical (oblivious) streaming algorithm that uses only polylogarithmic space. This is the first general separation between the capabilities of these two models, resolving one of the central open questions in adversarial robust streaming.