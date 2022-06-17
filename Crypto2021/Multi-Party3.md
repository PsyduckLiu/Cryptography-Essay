# Multi-Party Computation 3 

## 1. Pushing the Limits of Valiant's Universal Circuits: Simpler, Tighter and More Compact

A universal circuit (UC) is a general-purpose circuit that can simulate arbitrary circuits (up to a certain size $n$). Valiant provides a $k$-way recursive construction of UCs (STOC 1976), where $k$ tunes the complexity of the recursion. More concretely, Valiant gives theoretical constructions of 2-way and 4-way UCs of asymptotic (multiplicative) sizes $5n\log n$ and $4.75 n\log n$ respectively, which matches the asymptotic lower bound $\Omega(n\log n)$ up to some constant factor. 

Motivated by various privacy-preserving cryptographic applications, Kiss et al. (Eurocrypt 2016) validated the practicality of $2$-way universal circuits by giving example implementations for private function evaluation. G{\"{u}}nther et al. (Asiacrypt 2017) and Alhassan et al. (J. Cryptology 2020) implemented the 2-way/4-way hybrid UCs with various optimizations in place towards making universal circuits more practical. Zhao et al. (Asiacrypt 2019) optimized Valiant's 4-way UC to asymptotic size $4.5 n\log n$ and proved a lower bound $3.64 n\log n$ for UCs under the Valiant framework.

As the scale of computation goes beyond 10-million-gate ($n=10^7$) or even billion-gate level ($n=10^9$), the constant factor in UCs size plays an increasingly important role in application performance. In this work, we investigate Valiant's universal circuits and present an improved framework for constructing universal circuits with the following advantages.

[Simplicity.] Parameterization is no longer needed. In contrast to that previous implementations resorted to a hybrid construction combining $k=2$ and $k=4$ for a tradeoff between fine granularity and asymptotic size-efficiency, our construction gets the best of both worlds when configured at the lowest complexity (i.e., $k=2$).

[Compactness.] Our universal circuits have asymptotic size $3n\log n$, improving upon the best previously known $4.5n\log n$ by 33\% and beating the $3.64n\log n$ lower bound for UCs constructed under Valiant's framework (Zhao et al., Asiacrypt 2019).

[Tightness.] We show that under our new framework the UCs size is lower bounded by $2.95 n\log n$, which almost matches the $3n\log n$ circuit size of our $2$-way construction.

We implement the 2-way universal circuits and evaluate its performance with other implementations, which confirms our theoretical analysis.



***

## 2. Oblivious Key-Value Stores and Amplification for Private Set Intersection

Many recent private set intersection (PSI) protocols encode input sets as polynomials. We consider the more general notion of an oblivious key-value store (OKVS), which is a data structure that compactly represents a desired mapping $k_i$ to $v_i$. When the $v_i$ values are random, the OKVS data structure hides the $k_i$ values that were used to generate it. The simplest (and size-optimal) OKVS is a polynomial $p$ that is chosen using interpolation such that $p(k_i)=v_i$.

We initiate the formal study of oblivious key-value stores, and show new constructions resulting in the fastest OKVS to date.

Similarly to cuckoo hashing, current analysis techniques are insufficient for finding *concrete* parameters to guarantee a small failure probability for our OKVS constructions. Moreover,
it would cost too much to run experiments to validate  a small upperbound on the failure probability. We therefore show novel techniques to amplify an  OKVS construction which has a failure probability $p$, to an OKVS with a similar overhead and failure probability $p^c$. Setting $p$ to be moderately small enables to  validate it by running a relatively small number of $O(1/p)$ experiments. This validates a $p^c$ failure probability for the amplified OKVS. 
		
Finally, we describe how OKVS can significantly improve the state of the art of essentially all variants of PSI. This leads to the fastest two-party PSI protocols to date, for both the semi-honest and the malicious settings. Specifically, in networks with moderate bandwidth (e.g., 30 - 300 Mbps) our malicious  two-party PSI  protocol has 40\% less communication and is 20-40% faster than the previous state of the art protocol, even though the latter only has heuristic confidence.



***

## 3. MHz2k: MPC from HE over $\mathbb{Z}_{2^k}$ with New Packing, Simpler Reshare, and Better ZKP

We propose a multiparty computation protocol over $\mathbb{Z}_{2^k}$ secure against actively corrupted majority from somewhat homomorphic encryption. The main technical contributions are: (i) a new efficient packing method for messages in $\mathbb{Z}_{2^k}$ for lattice-based somewhat homomorphic encryption schemes, (ii) a simpler reshare protocol for level-dependent packings, (iii) a more efficient zero-knowledge proof of plaintext knowledge on a cyclotomic ring $\Z[X]/\Phi_M(X)$ with $M$ being a prime. Integrating them, our protocol shows from 2.2x upto 4.9x improvements in amortized communication costs compared to the previous best results. Our techniques not only improve the efficiency of MPC over the $\mathbb{Z}_{2^k}$ considerably, but also elucidate several properties of $\mathbb{Z}_{2^k}$ which can be exploited when designing other cryptographic primitives over $\mathbb{Z}_{2^k}$.



***

## 4. Sublinear GMW-Style Compiler for MPC with Preprocessing

We consider the efficiency of protocols for secure multiparty computation (MPC) with a dishonest majority. A popular approach for the design of such protocols is to employ {\em preprocessing}. Before the inputs are known, the parties generate correlated secret randomness, which is consumed by a fast and ``information-theoretic'' online protocol. 

A powerful technique for securing such protocols against malicious parties uses {\em homomorphic MACs} to authenticate the values produced by the online protocol. Compared to a baseline protocol, which is only secure against semi-honest parties, this involves a significant increase in the size of the correlated randomness, by a factor of up to a statistical security parameter. Different approaches for partially mitigating this extra storage cost come at the expense of increasing the online communication.

In this work we propose a new technique for protecting MPC with preprocessing against malicious parties. We show that for circuit evaluation protocols that satisfy mild security and structural requirements, that are met by almost all standard protocols with semi-honest security, the extra {\em additive} storage and online communication costs are both {\em logarithmic} in the circuit size. This applies to Boolean circuits and to arithmetic circuits over fields or rings, and to both information-theoretic and computationally secure protocols. Our protocol can be viewed as a sublinear information-theoretic variant of the celebrated ``GMW compiler'' that applies to MPC with preprocessing.

Our compiler makes a novel use of the techniques of Boneh et al. (Crypto 2019) for sublinear distributed zero knowledge, which were previously only used in the setting of {\em honest-majority} MPC.



***

## 5. Limits on the Adaptive Security of Yao’s Garbling

Yao’s garbling scheme is one of the most fundamental cryptographic constructions. Lindell and Pinkas (Journal of Cryptograhy 2009) gave a formal proof of security in the selective setting assuming secure symmetric-key encryption (and hence one-way functions). This was fol- lowed by results, both positive and negative, concerning its security in the, stronger, adaptive setting. Applebaum et al. (Crypto 2013) showed that it cannot satisfy adaptive security as is, due to a simple incompressibility argument. Jafagholi and Wichs (TCC 2017) considered a natural adaptation of Yao’s scheme that circumvents this negative result, and proved that it is adaptively secure, at least for shallow circuits. In particular, they showed that for the class of circuits of depth d, the loss in security is at most exponential in d. The above results all concern the simulation-based notion of security.

In this work, we show that the upper bound of Jafargholi and Wichs is more or less optimal in a strong sense. As our main result, we show that there exists a family of Boolean circuits, one for each depth d ∈ N, such that any black-box reduction proving the adaptive indistinguishability- security of the natural adaptation of Yao’s scheme from any symmetric-key encryption has to lose a factor that is sub-exponential in d. Since indistinguishability is a weaker notion than simulation, our bound also applies to adaptive simulation.

To establish our results, we build on the recent approach of Kamath et al. (Eprint 2021), which uses pebbling lower bounds in conjunction with oracle separations to prove fine-grained lower bounds on loss in cryptographic security



***

