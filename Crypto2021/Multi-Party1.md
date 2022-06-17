# Multi-Party Computation 1

## 1. Game-Theoretic Fairness Meets Multi-Party Protocols: The Case of Leader Election

Suppose that $n$ players want to elect a random leader and they communicate by posting messages to a common broadcast channel. This problem is called leader election, and it is  fundamental to the distributed systems and cryptography literature. 
Recently, it has attracted renewed interests due to its promised applications in decentralized environments. In a game theoretically fair leader election protocol, roughly speaking, we want that even majority coalitions  cannot increase its own chance of getting elected, nor hurt the chance of any honest individual. The folklore tournament-tree protocol, which completes in logarithmically many rounds,  can easily be shown to satisfy game theoretic security. To the best of our knowledge,  no sub-logarithmic round protocol was known in the setting that we consider.

We show that by adopting an appropriate notion of approximate game-theoretic fairness, and under standard cryptographic assumption, we can achieve $(1-1/2^{\Theta(r)})$-fairness in $r$ rounds for $\Theta(\log \log n) \leq r \leq \Theta(\log n)$, where $n$ denotes the number of players. In particular, this means that we can approximately match the fairness of the tournament tree protocol using as few as $O(\log \log n)$ rounds.We also prove a lower bound showing that logarithmically many rounds is necessary if we restrict ourselves 
to ``perfect'' game-theoretic fairness  and protocols that are 
``very similar in structure'' to the tournament-tree protocol.

Although leader election is a well-studied problem in other contexts in distributed computing,  our work is the first exploration of the round complexity of {\it game-theoretically fair} leader election in the presence of a possibly majority coalition.As a by-product of our exploration, we suggest a new, approximate game-theoretic fairness notion, called ``approximate sequential fairness'', which provides a more desirable solution concept than some previously studied approximate fairness notions.



***

## 2. Computational Hardness of Optimal Fair Computation: Beyond Minicrypt

Secure multi-party computation allows mutually distrusting parties to compute securely over their private data. However, guaranteeing output delivery to honest parties when the adversarial parties may abort the protocol has been a challenging objective. As a representative task, this work considers two-party coin-tossing protocols with guaranteed output delivery, a.k.a., fair coin-tossing. 

In the information-theoretic plain model, as in two-party zero-sum games, one of the parties can force an output with certainty. In the commitment-hybrid, any $r$-message coin-tossing protocol is ${1/\sqrt r}$-unfair, i.e., the adversary can change the honest party's output distribution by $1/\sqrt r$ in the statistical distance. Moran, Naor, and Segev (TCC--2009) constructed the first $1/r$-unfair protocol in the oblivious transfer-hybrid. No further security improvement is possible because Cleve (STOC--1986) proved that $1/r$-unfairness is unavoidable. Therefore, Moran, Naor, and Segev's coin-tossing protocol is optimal. However, is oblivious transfer necessary for optimal fair coin-tossing? 

Maji and Wang (CRYPTO--2020) proved that any coin-tossing protocol using one-way functions in a black-box manner is at least $1/\sqrt r$-unfair. That is, optimal fair coin-tossing is impossible in Minicrypt. Our work focuses on tightly characterizing the hardness of computation assumption necessary and sufficient for optimal fair coin-tossing within Cryptomania, outside Minicrypt. Haitner, Makriyannia, Nissim, Omri, Shaltiel, and Silbak (FOCS--2018 and TCC--2018) proved that better than $1/\sqrt r$-unfairness, for any constant $r$, implies the existence of a key-agreement protocol. 

We prove that any coin-tossing protocol using public-key encryption (or, multi-round key agreement protocols) in a black-box manner must be $1/\sqrt r$-unfair. Next, our work entirely characterizes the additional power of secure function evaluation functionalities for optimal fair coin-tossing. We augment the model with an idealized secure function evaluation of $f$, \aka, the $f$-hybrid. If $f$ is complete, that is,  oblivious transfer is possible in the $f$-hybrid, then optimal fair coin-tossing is also possible in the $f$-hybrid. On the other hand, if $f$ is not complete, then a coin-tossing protocol using public-key encryption in a black-box manner in the $f$-hybrid is at least $1/\sqrt r$-unfair.



***

## 3. You Only Speak Once: Secure MPC with Stateless Ephemeral Roles

The inherent difficulty of maintaining stateful environments over long periods of time gave rise to the paradigm of serverless computing, where mostly-stateless components are deployed on demand to handle computation tasks, and are teared down once their task is complete. Serverless architecture could offer the added benefit of improved resistance to targeted denial-of-service attacks, by hiding from the attacker the physical machines involved in the protocol until after they complete their work. Realizing such protection, however, requires that the protocol only uses stateless parties, where each party sends only one message and never needs to speaks again. Perhaps the most famous example of this style of protocols is the Nakamoto consensus protocol used in Bitcoin: A peer can win the right to produce the next block by running a local lottery (mining), all while staying covert.   Once the right has been won, it is executed by sending a single message. After that, the physical entity never needs to send more messages.

We refer to this as the You-Only-Speak-Once (YOSO) property, and initiate the formal study of it within a new model that we call the YOSO model. Our model is centered around the notion of roles, which are stateless parties that can only send a single message. Crucially, our modelling separates the protocol design, that only uses roles, from the role-assignment mechanism, that assigns roles to actual physical entities. This separation enables studying these two aspects separately, and our YOSO model in this work only deals with the protocol-design aspect.

We describe several techniques for achieving YOSO MPC; both computational and information theoretic. Our protocols are synchronous and provide guaranteed output delivery (which is important for application domains such as blockchains), assuming honest majority of roles in every time step. We describe a practically efficient computationally-secure protocol, as well as a proof-of-concept information theoretically secure protocol.



***

## 4. Fluid MPC: Secure Multiparty Computation with Dynamic Participants

Existing approaches to secure multiparty computation (MPC) require all participants to commit to the entire duration of the protocol. As interest in MPC continues to grow, it is inevitable that there will be a desire to use it to evaluate increasingly complex functionalities, resulting in computations spanning several hours or days. 

Such scenarios call for a *dynamic* participation model for MPC where participants have the flexibility to go offline as needed and (re)join when they have available computational resources. Such a model would also democratize access to privacy-preserving computation by facilitating an ``MPC-as-a-service'' paradigm --- the deployment of MPC in volunteer-operated networks (such as blockchains, where dynamism is inherent) that perform computation on behalf of clients. 

In this work, we initiate the study of *fluid MPC*, where parties can dynamically join and leave the computation. The minimum commitment required from each participant is referred to as *fluidity*, measured in the number of rounds of communication that it must stay online. Our contributions are  threefold:

- We provide a formal treatment of fluid MPC, exploring various possible modeling choices. 
- We construct information-theoretic fluid MPC protocols in the honest-majority setting. Our protocols achieve *maximal fluidity*, meaning that a party can exit the computation after receiving and sending messages in one round.
- We implement our protocol and test it in multiple network settings.



***

## 5. Secure Computation from One-Way Noisy Communication, or: Anti-Correlation via Anti-Concentration

Can a sender encode a pair of messages (m_0,m_1) jointly, and send their encoding over (say) a binary erasure channel, so that the receiver can decode exactly one of the two messages and the sender does not know which one?

Garg et al. (Crypto 2015) showed that this is information-theoretically impossible.
We show how to circumvent this impossibility by assuming that the receiver is computationally bounded, settling for an inverse-polynomial security error (which is provably necessary),  and relying on ideal obfuscation.
Our solution creates a ``computational anti-correlation'' between the events of receiving m_0 and receiving m_1 by exploiting the anti-concentration of the binomial distribution.

The ideal obfuscation primitive in our construction can either be directly realized using (stateless) tamper-proof hardware, yielding an unconditional result, or heuristically instantiated using existing indistinguishability obfuscation schemes. We put forward a new notion of obfuscation that suffices to securely instantiate our construction.

As a corollary, we get similar feasibility results for general secure computation of sender-receiver functionalities by leveraging the completeness of the above ``random oblivious transfer'' functionality.