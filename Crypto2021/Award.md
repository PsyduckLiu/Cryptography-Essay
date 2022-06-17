# Award Papers

## 1. On the Possibility of Basing Cryptography on $\EXP \neq \BPP$

Liu and Pass (FOCS'20) recently demonstrated an equivalence between the existence of one-way functions and mild average-case hardness of the time-bounded Kolmogorov complexity problem. In this work, we establish a similar equivalence but to a different form of time-bounded Kolmogorov Complexity---namely, Levin's notion of Kolmogorov Complexity---whose hardness is closely related to the problem of whether $\EXP \neq
\BPP$. In more detail, let $Kt(x)$ denote the Levin-Kolmogorov Complexity of the string $x$; that is, $Kt(x) = \min_{\desc \in \bitset^*, t \in \N}\{|\desc| +
\lceil \log t \rceil: U(\desc, 1^t) = x\}$, where $U$ is a universal Turing machine, and let $\mktp$ denote the language of pairs $(x,k)$ having the property that $Kt(x) \leq k$. We demonstrate that:

 - $\mktp$ is \emph{two-sided error} mildly average-case hard (i.e., $\mktp
    \notin \HeurpBPP$) iff infinititely-often one-way functions exist.
- $\mktp$ is \emph{errorless} mildly average-case hard (i.e., $\mktp
    \notin \AvgpBPP$) iff $\EXP \neq \BPP$. Thus, the only ``gap'' towards getting (infinitely-often) one-way functions from the assumption that $\EXP \neq \BPP$ is the
seemingly ``minor'' technical gap between two-sided error and errorless average-case hardness of the$\mktp$ problem.

As a corollary of this result, we additionally demonstrate that any reduction from errorless to two-sided error average-case hardness for $\mktp$ implies (unconditionally) that $\NP \neq \P$. 

We finally consider other alternative notions of Kolmogorov complexity---including space-bounded Kolmogorov complexity and
conditional Kolmogorov complexity---and show how average-case hardness of problems related to them characterize log-space
computable one-way functions, or one-way functions in $\NC^0$.



***

## 2. Linear Cryptanalysis of FF3-1 and FEA

Improved attacks on generic small-domain Feistel ciphers with alternating round tweaks are obtained using linear cryptanalysis. This results in practical distinguishing and message-recovery attacks on the United States format-preserving encryption standard FF3-1 and the South-Korean standards FEA-1 and FEA-2. The data-complexity of the proposed attacks on FF3-1 and FEA-1 is $O(N^{r/2 - 1.5})$, where $N^2$ is the domain size and $r$ is the number of rounds. For example, FF3-1 with $N = 10^3$ can be distinguished from an ideal tweakable block cipher with advantage $\ge 1/10$  using $2^{23}$ encryption queries. Recovering the left half of a message with similar advantage requires $2^{24}$ data. The analysis of FF3-1 serves as an interesting real-world application of (generalized) linear cryptanalysis over the group $\mathbb{Z}/N\mathbb{Z}$.



***

## 3. Efficient Key Recovery for all HFE Signature Variants

The HFE cryptosystem is one of the best known multivariate schemes. Especially in the area of digital signatures, the HFEv- variant offers short signatures and high performance. Recently, an instance of the HFEv- signature scheme called GeMSS was elected as one of the alternative candidates for signature schemes in the third round of the NIST Post Quantum Crypto (PQC) Standardization Project. In this paper, we propose a new key recovery attack on the HFEv- signature scheme. Our attack shows that both the Minus and the Vinegar modifi- cation do not enhance the security of the basic HFE scheme significantly. This shows that it is very difficult to build a secure and efficient signature scheme on the basis of HFE.
   In particular, we use our attack to show that the proposed parameters of the GeMSS scheme are not as secure as claimed.



***

## 4. Three Halves Make a Whole? Beating the Half-Gates Lower Bound for Garbled Circuits

We describe a garbling scheme for boolean circuits, in which XOR gates are free and AND gates require communication of $1.5\kappa + 5$ bits. This improves over the state-of-the-art ``half-gates'' scheme of Zahur, Rosulek, and Evans (Eurocrypt 2015), in which XOR gates are free and AND gates cost $2\kappa$ bits. The half-gates paper proved a lower bound of $2\kappa$ bits per AND gate, in a model that captured all known garbling techniques at the time. We bypass this lower bound with a novel technique that we call \textbf{slicing and dicing}, which involves slicing wire labels in half and operating separately on those halves. Ours is the first to bypass the lower bound while being fully compatible with free-XOR, making it a drop-in replacement for half-gates. Our construction is proven secure from a similar assumption to prior free-XOR garbling (circular correlation-robust hash), and uses only slightly more computation than half-gates.