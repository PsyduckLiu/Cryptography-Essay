# Protocols

## 1. A Logarithmic Lower Bound for Oblivious RAM (for all parameters)

An Oblivious RAM (ORAM), introduced by Goldreich and Ostrovsky (J. ACM 1996), is a (probabilistic) RAM that hides its access pattern, i.e., for every input the observed locations accessed are similarly distributed. In recent years there has been great progress both in terms of upper bounds as well as in terms of lower bounds, essentially  pinning down the smallest overhead possible in various settings of parameters. 

We observe that there is a very natural setting of parameters in which \emph{no} non-trivial lower bound is known, even not ones in restricted models of computation (like the so called balls and bins model). Let $N$ and $w$ be the number of cells and bit-size of cells, respectively, in the RAM that we wish to simulate obliviously. Denote by $b$ the cell bit-size of the ORAM. \emph{All} previous ORAM lower bounds have a multiplicative $w/b$ factor which makes them trivial in many settings of parameters of interest.

In this work, we prove a new ORAM lower bound that captures this setting (and in all other settings it is at least as good as previous ones, quantitatively). We show that any ORAM must make (amortized)
$$
\Omega\left(\log \left(\frac{Nw}{m}\right)/\log\left(\frac{b}{w}\right)\right)
$$
memory probes for every logical operation. Here, $m$ denotes the bit-size of the local storage of the ORAM. Our lower bound implies that logarithmic overhead in accesses is necessary, even if $ b \gg w$. Our lower bound is tight for \emph{all} settings of parameters, up to the $\log(b/w)$ factor. Our bound also extends to the non-colluding multi-server setting.

As an application, we derive the first (unconditional) separation between the overhead needed for ORAMs in the \emph{online} vs.\ \emph{offline} models. Specifically, we show that when $w=\log N$ and $b,m \in poly\log N$, there exists an offline ORAM that makes (on average) $o(1)$ memory probes per logical operation while every online one must make $\Omega(\log N/\log\log N)$ memory probes per logical operation. No such previous separation was known for any setting of parameters, not even in the balls and bins model.



***

## 2. Oblivious RAM with Worst-Case Logarithmic Overhead

We present the first Oblivious RAM (ORAM) construction that for $N$ memory blocks supports accesses with \emph{worst-case} $O(\log N)$ overhead for any block size $\Omega(\log N)$ while requiring a client memory of only a constant number of memory blocks. We rely on the existence of one-way functions and guarantee computational security. Alternatively, we obtain statistical security in the (private) random oracle model. Our result closes a long line of research on fundamental feasibility results for ORAM constructions as logarithmic overhead is necessary.

The previous best logarithmic overhead construction only guarantees it in an \emph{amortized} sense, i.e., logarithmic overhead is achieved only for long enough access sequences, where some of the individual accesses incur $\Theta(N)$ overhead. The previously best ORAM in terms of \emph{worst-case} overhead  achieves $O(\log^2 N/\log\log N)$ overhead. 

Technically, we design a novel de-amortization framework for modern ORAM constructions that use the ``shuffled inputs'' assumption. Our framework significantly departs from all previous de-amortization frameworks, originating from Ostrovsky and Shoup (STOC~'97), that seem to be fundamentally too weak to be applied on modern ORAM constructions.



***

## 3. Puncturable Pseudorandom Sets and Private Information Retrieval with Near-Optimal Online Bandwidth and Time

Imagine that one or more non-colluding servers each holds a large public database, e.g., the repository of DNS entries.  Clients would like to access entries in this database without disclosing their queries to the servers.  Classical private information retrieval (PIR) schemes achieve polylogarithmic bandwidth per query, but require the server to perform linear computation per query, which is a deal-breaker in practice.

Several recent works showed, however, that by introducing a one-time, per-client, off-line preprocessing phase, an \emph{unbounded} number of client queries can be subsequently served
with sublinear online computation time per query (and the cost of the preprocessing can be amortized over the unboundedly many queries).  Unfortunately, existing preprocessing PIRs
make undesirable tradeoffs to achieve sublinear online computation: they are either significantly non-optimal in online time or bandwidth, or require the servers to store a linear amount state per client (or even per query), or require polylogarithmically many non-colluding servers.

We propose a novel 2-server preprocessing PIR scheme that achieves $\widetilde{O}(\sqrt{n})$ online computation per query, while preserving the polylogarithmic online bandwidth of classical PIR
schemes.  Both the online bandwidth and computation are optimal up to a poly-logarithmic factor.
In our construction, each server stores only the original database and nothing extra, and each online query is served within a single round trip.  Our construction relies on the standard LWE
assumption.  As an important stepping stone, we propose new, more generalized definitions for a cryptographic object called a Privately Puncturable Pseudorandom Set, and give novel constructions that depart significantly from prior approaches.



***

## 4. Authenticated Key Exchange and Signatures with Tight Security in the Standard Model

We construct the first authenticated key exchange protocols that achieve tight security in the standard model. Previous works either relied on techniques that seem to inherently require a random oracle, or achieved only “Multi-Bit-Guess” security, which is not known to compose tightly, for instance, to build a secure channel.
Our constructions are generic, based on digital signatures and key encapsulation mechanisms (KEMs). The main technical challenges we resolve is to determine suitable KEM security notions which on the one hand are strong enough to yield tight security, but at the same time weak enough to be efficiently instantiable in the standard model, based on standard techniques such as universal hash proof systems.
Digital signature schemes with tight multi-user security in presence of adaptive corruptions are a central building block, which is used in all known constructions of tightly-secure AKE with full forward security. We identify a subtle gap in the security proof of the only previously known efficient standard model scheme by Bader et al. (TCC 2015). We develop a new variant, which yields the currently most efficient signature scheme that achieves this strong security notion without random oracles and based on standard hardness assumptions.



***

## 5. KHAPE: Asymmetric PAKE from Key-Hiding Key Exchange

OPAQUE [Jarecki et al., Eurocrypt 2018] is an asymmetric password authenticated key exchange (aPAKE) protocol that is being developed as an Internet standard and for use within TLS 1.3.  OPAQUE combines an Oblivious PRF (OPRF) with an authenticated key exchange to provide strong security properties, including security against pre-computation attacks (called saPAKE security). However, the security of OPAQUE relies crucially on the integrity of the OPRF. If the latter breaks (by cryptanalysis, quantum attacks or security compromise), the user's password is immediately exposed to an offline dictionary attack. To address this weakness, we present KHAPE, a variant of OPAQUE that does not require the use of an OPRF to achieve aPAKE security, resulting in improved resilience  and performance. An OPRF can be optionally added to KHAPE, for enhanced saPAKE security, but without opening the password to an offline dictionary attack upon OPRF compromise.

In addition to resilience to OPRF compromise, a DH-based implementation of KHAPE (using HMQV) offers the best performance among aPAKE protocols in terms of exponentiations with less than the cost of an exponentiation on top of an unauthenticated Diffie-Hellman exchange. KHAPE uses three messages with explicit client authentication and four with explicit server authentication (one more than OPAQUE in the latter case).

All results in the paper are proven within the UC framework in the ideal cipher model. Of independent interest is our treatment of "key-hiding AKE" which KHAPE uses as a main component, and our UC proofs of AKE security for protocols 3DH (a basis of Signal) and HMQV that we use as efficient instantiations of KHAPE.