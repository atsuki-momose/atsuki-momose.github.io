# Atsuki Momose

I am a PhD student in [Computer Science](https://cs.illinois.edu/) at [University of Illinois Urbana-Champaign](https://illinois.edu/), working with [Prof. Ling Ren](https://sites.google.com/view/renling). I did my undergraduate and graduate studies (M.S.) at Nagoya University advised by [Prof. Yuichi Kaji](https://profs.provost.nagoya-u.ac.jp/html/100009250_en.html).

I am honored to receive [Tsujii Shigeo Security Paper Award (2022)](https://www.jssm.net/news/6808/). I am supported in part by the [Illinois Distinguished Fellowship](https://apps.grad.illinois.edu/fellowship-finder/SearchResult/Fellowship/4683).

**[Google Scholar](https://scholar.google.com/citations?user=fl3XtlUAAAAJ&hl=en) / [Twitter](https://www.twitter.com/AtsukiMomose)**


## Research.

I am generally interested in distributed computing and cryptography. One of the main topics is distributed consensus, an underlying technology of Bitcoin, and what people call *blockchain*. Consensus is a decade-old problem, and Bitcoin is often considered just another solution to the classical consensus problem. However, Bitcoin's consensus mechanism takes a completely different approach from classic solutions and comes with several unique features, such as dynamic participation support, higher fault tolerance under asynchronous clocks, and sub-quadratic total communication using sparse gossip networks. My interest is exploring the intersection of Bitcoin and classic solutions aiming at achieving the best of both worlds. Here are some of my recent works.

* **Sleepy BFT.** 
One of the most interesting features that makes the Bitcoin protocol unique is its support for dynamic and unknown participation, where nodes can spontaneously join/leave the network at will without prior notice. Traditional protocols do not work in this dynamic setting, as they require votes from a fixed quorum of nodes to make progress. To adapt the classic quorum-based approach to the dynamic setting, we have introduced a new technique we call *time-shifted quorum*. Time-shifted quorum allows each node to dynamically define the quorum threshold based on the node's perceived participation level while preserving important properties of classic static quorums. This achieves the best of both: constant latency of classical protocols and dynamic participation support of Bitcoin. Part of this work is published in [ACM CCS 2022](https://eprint.iacr.org/2022/404) and [ACM CCS 2023](https://eprint.iacr.org/2022/1448).

* **Multi-threshold BFT.**
Consensus protocols in general assume a bound f on the number of *corrupt* nodes (i.e., those controlled by an attacker). Classic consensus protocols assume f < n/3, which is known to be the theoretical limit for tolerating occasional network failure. One strength of Bitcoin is its higher fault tolerance f < n/2, but it assumes a perfectly synchronous network. In other words, they are on the two extremes. Can we circumvent this trade-off and enjoy the best of both worlds? Our recent work shows, that with small modifications, classic protocols that tolerate n/3 corruption under asynchronous networks can still tolerate up to 2n/3 corruption when the network is synchronous. In other words, an attacker needs to control a very large fraction (2/3) of nodes or control 1/3 plus the entire network, to successfully mount the attack. This work is published in [ACM CCS 2021](https://eprint.iacr.org/2021/671).

* **Optimal communication BA/BB.**
Bitcoin is the first practical synchronous protocol that operates under an asynchronous clock, and [several follow-up works](https://decentralizedthoughts.github.io/2019-11-11-authenticated-synchronous-bft/) attempt to achieve similar guarantees. All of these works rely on the common step: *forward messages to all other nodes*. This step helps detect conflicting views among nodes and prevents disagreement. However, it increases the overall communication by a factor of n compared to classical protocols (with lower fault tolerance) where nodes send their own belief only. To fill this gap, we introduce a new technique that utilizes an *expander graph* to forward messages efficiently yet being able to detect conflicting views among nodes. Remarkably, this technique also resolves a long-standing open question on the optimal communication complexity of Byzantine broadcast/agreement, namely the tightness of [Dolev-Reischuk lower bound](https://decentralizedthoughts.github.io/2019-08-16-byzantine-agreement-needs-quadratic-messages/). We have also applied this technique to design a *broadcast channel*, a primitive often used in cryptography, with optimal communication. These works are published in [DISC 2021](https://drops.dagstuhl.de/opus/volltexte/2021/14834/pdf/LIPIcs-DISC-2021-32.pdf) and [ACM PODC 2023](https://eprint.iacr.org/2023/038).

I am recently expanding my research interest to cryptography for distributed computing. Here is one recent work.

* **Security of KZG commitment.**
Distributed computing often relies on secret-shared randomness, which involves distribution of polynomial evaluations. An essential cryptographic primitive for secret-sharing is a polynomial commitment, which validates each evaluation without revealing the entire polynomial. KZG commitment is one of the gold standards of polynomial commitment and finds widespread use in the design of bandwidth-efficient secret-sharing protocols. However, we point out a critical property that the KZG commitment is missing, which we call *degree binding*. The property ensures that the polynomial used for secret-sharing has the required degree. In our recent work, we show how to augment the KZG commitment to guarantee this property while preserving the bandwidth efficiency. This work will appear in [ACM CCS 2023](https://eprint.iacr.org/2023/1350).


## Publications.

[On the Security of KZG Commitment for VSS.](https://eprint.iacr.org/2023/1350) 
  - with Sourav Das and Ling Ren *@ACM CCS 2023*

[Towards Practical Sleepy BFT.](https://eprint.iacr.org/2022/1448) 
  - with Dahlia Malkhi and Ling Ren *@ACM CCS 2023*

[On the  Amortized Communication Complexity of Byzantine Broadcast.](https://eprint.iacr.org/2023/038)
  - with Ling Ren, Elaine Shi, Jun Wan, and Zhuolun Xiang. *@ACM PODC 2023.*

[Constant Latency in Sleepy Consensus.](https://eprint.iacr.org/2022/404) 
  - with Ling Ren. *@ACM CCS 2022.*

[Multi-Threshold Byzantine Fault Tolerance.](https://eprint.iacr.org/2021/671) 
  - with Ling Ren *@ACM CCS 2021*

[Optimal Communication Complexity of Authenticated Byzantine Agreement.](https://drops.dagstuhl.de/opus/volltexte/2021/14834/pdf/LIPIcs-DISC-2021-32.pdf) 
  - with Ling Ren *@DISC 2021*
