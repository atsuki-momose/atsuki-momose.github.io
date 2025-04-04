# Atsuki Momose

I am an Executive Officer and Head of Research (Chief Research Officer) at [Acompany](https://acompany.tech/en), a privacy-tech startup based in Japan. I also serve as the Founding Director of Confidential Computing Lab (CC Lab) at Acompany, where we conduct cutting-edge R&D in Confidential Computing based on Trusted Execution Environment (TEE) technologies, in collaboration with both academic and industry research partners. 

In addition, I work independently as a researcher on Multi-Party Computation (MPC) for blockchains. This project is partially supported by a research grant from the [Ethereum Foundation](https://ethereum.foundation/).

Previously, I was a Research Scholar and a Ph.D. student in Computer Science at the [University of Illinois Urbana-Champaign](https://illinois.edu/).

I am honored to have received the [Tsujii Shigeo Security Paper Award (2022)](https://www.jssm.net/news/6808/) and the [Illinois Distinguished Fellowship](https://apps.grad.illinois.edu/fellowship-finder/SearchResult/Fellowship/4683). 

I also serve as a program committee member for [ACM CCS 2024](https://www.sigsac.org/ccs/CCS2024/call-for/call-for-papers.html) and [ACM CCS 2025](https://www.sigsac.org/ccs/CCS2025/call-for/call-for-papers.html).

**[Google Scholar](https://scholar.google.com/citations?user=fl3XtlUAAAAJ&hl=en) / [Twitter](https://www.twitter.com/AtsukiMomose)**

## Research.

I am generally interested in distributed computing and cryptography.

### Blockchain Consensus.
Distributed consensus is an underlying technology of Bitcoin, often referred to as *blockchain*. Consensus is a decade-old problem, and Bitcoin is often considered just another solution to the classical problem. However, Bitcoin's consensus mechanism takes a completely different approach from classic solutions, and it comes with several unique features, such as support for dynamic participation, higher fault tolerance under asynchronous clocks, and efficient communication through the use of sparse gossip networks. My interest is exploring the intersection of Bitcoin and classic solutions aiming to achieve the best of both worlds. Here are some of my recent works.

* **Sleepy BFT.** 
The most prominent feature that makes the Bitcoin protocol unique is its support for dynamic and unknown participation, where nodes can spontaneously join/leave the network at will without prior notice. Traditional protocols do not work in the dynamic setting since they require a fixed quorum of votes to make progress. To adapt the classic quorum-based approach to the dynamic setting, we have introduced a new technique we call *time-shifted quorum*. Time-shifted quorum allows each node to dynamically define the quorum threshold based on the node's perceived participation level while preserving important properties of classic static quorums. This achieves the best of both: constant latency of classical protocols and dynamic participation support of Bitcoin. Part of this work is published in [ACM CCS 2022](https://eprint.iacr.org/2022/404) and [ACM CCS 2023](https://eprint.iacr.org/2022/1448).

* **Multi-threshold BFT.**
Consensus protocols in general assume a bound f on the number of *corrupt* nodes (i.e., those controlled by an attacker). Classic consensus protocols assume f < n/3, which is known to be the theoretical limit for tolerating occasional network failure. One strength of Bitcoin is its higher fault tolerance f < n/2, but it assumes a perfectly synchronous network. In other words, they are on the two extremes. Can we circumvent this trade-off and enjoy the best of both worlds? Our recent work shows, that with small modifications, classic protocols that tolerate n/3 corruption under asynchronous networks can still tolerate up to 2n/3 corruption when the network is synchronous. In other words, an attacker needs to control a very large fraction (2/3) of nodes or control 1/3 plus the entire network, to successfully mount the attack. This work is published in [ACM CCS 2021](https://eprint.iacr.org/2021/671).

* **Optimal communication BA/BB.**
Bitcoin is the first practical synchronous protocol, and it inspired several follow-up works that leverage synchronous communication for higher fault tolerance. All existing synchronous protocols share a common step: *forwarding messages to all other nodes*. This step helps detect conflicting views among nodes and prevents disagreement. However, it increases the overall communication by a factor of n compared to classical asynchronous protocols where nodes send their own belief only. To fill this gap, we introduce a new technique that utilizes an *expander graph* to forward messages efficiently yet being able to detect conflicting views among nodes. Remarkably, this technique also resolves a long-standing open question on the optimal communication complexity of Byzantine broadcast/agreement, namely the tightness of [Dolev-Reischuk lower bound](https://decentralizedthoughts.github.io/2019-08-16-byzantine-agreement-needs-quadratic-messages/). We have also applied this technique to design a *broadcast channel*, a primitive often used in cryptography, with optimal communication. These works are published in [DISC 2021](https://drops.dagstuhl.de/opus/volltexte/2021/14834/pdf/LIPIcs-DISC-2021-32.pdf) and [ACM PODC 2023](https://eprint.iacr.org/2023/038).

### Distributed Cryptography.

I am recently expanding my research interest to cryptography for distributed computing.

* **Security of KZG commitment.**
Distributed computing often relies on secret-shared randomness, which involves distribution of polynomial evaluations. An essential cryptographic primitive for secret-sharing is a polynomial commitment, which validates each evaluation without revealing the entire polynomial. KZG commitment is one of the gold standards of polynomial commitment and finds widespread use in the design of bandwidth-efficient secret-sharing protocols. However, we point out a critical property that the KZG commitment is missing, which we call *degree binding*. The property ensures that the polynomial used for secret-sharing has the required degree. In our recent work, we show how to augment the KZG commitment to guarantee this property while preserving the bandwidth efficiency. The paper is published at [ACM CCS 2023](https://eprint.iacr.org/2023/1350).

* **Setup-free asynchronous consensus.**
Asynchronous consensus has seen revived interest in recent years due to its robustness against network failures. However, the biggest pain point of most existing asynchronous consensus protocols is their reliance on an external common coin. A common coin is often instantiated through a distributed key generation (DKG) setup, which involves several expensive cryptographic operations (e.g., elliptic curve pairings). In our recent work, we show how to design an asynchronous consensus protocol without any setup (including PKI) while solely relying on a hash function. The paper will appear in [ACM CCS 2024](https://eprint.iacr.org/2024/677).

## Publications.

* [Practical Asynchronous MPC from Lightweight Cryptography](https://eprint.iacr.org/2024/1717) @Preprint.

* [Asynchronous Consensus without Trusted Setup or Public-Key Cryptography](https://eprint.iacr.org/2024/677) with Sourav Das, Sisi Duan, Shengqi Liu, Ling Ren, and Victor Shoup. *@ACM CCS 2024*.

* [On the Security of KZG Commitment for VSS.](https://eprint.iacr.org/2023/1350) with Sourav Das and Ling Ren. *@ACM CCS 2023*.

* [Towards Practical Sleepy BFT.](https://eprint.iacr.org/2022/1448) with Dahlia Malkhi and Ling Ren. *@ACM CCS 2023*.

* [On the  Amortized Communication Complexity of Byzantine Broadcast.](https://eprint.iacr.org/2023/038) with Ling Ren, Elaine Shi, Jun Wan, and Zhuolun Xiang. *@ACM PODC 2023.*

* [Constant Latency in Sleepy Consensus.](https://eprint.iacr.org/2022/404) with Ling Ren. *@ACM CCS 2022.*

* [Multi-Threshold Byzantine Fault Tolerance.](https://eprint.iacr.org/2021/671) with Ling Ren *@ACM CCS 2021*

* [Optimal Communication Complexity of Authenticated Byzantine Agreement.](https://drops.dagstuhl.de/opus/volltexte/2021/14834/pdf/LIPIcs-DISC-2021-32.pdf) with Ling Ren *@DISC 2021*
