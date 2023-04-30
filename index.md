# Atsuki Momose

I am a research scholar (Aug. 2022 - Aug. 2023) in [Computer Science at University of Illinois Urbana-Champaign](https://cs.illinois.edu/), working with [Prof. Ling Ren](https://sites.google.com/view/renling). I did my undergraduate and graduate studies (M.S.) at Nagoya University advised by [Prof. Yuichi Kaji](https://profs.provost.nagoya-u.ac.jp/html/100009250_en.html) (Apr. 2015 - Mar. 2021), and spent a year at [SECOM](https://www.secom.co.jp/isl/en/) (Apr. 2021 - Jul. 2022).

**[Google Scholar](https://scholar.google.com/citations?user=fl3XtlUAAAAJ&hl=en) / [Twitter](https://www.twitter.com/AtsukiMomose)**


## Research.

I study distributed consensus, an underlying technology of Bitcoin and what is called "blockchain". Consensus is a decade-old problem in distributed computing and cryptography, and Bitcoin is simply another solution to the classical problem.  But interestingly, Bitcoin's consensus is designed in a completely different way from classical solutions and has several new features such as dynamic participation support, higher resilience under asynchronous clocks, and sub-quadratic total communication using sparse gossip networks. My research interest has been to explore the intersection of Bitcoin and classical solutions aiming at achieving the best of both worlds.


## Selected Publications.

**[On the  Amortized Communication Complexity of Byzantine Broadcast.](https://eprint.iacr.org/2023/038)**

- with Ling Ren, Elaine Shi, Jun Wan, and Zhuolun Xiang. *@ACM PODC 2023.*
- Disseminating consensus values is a crucial task in any protocol. How can we make sure everybody receives the agreed-on value if the origin of the value is corrupt? The most common approach is to let everybody forwards messages once received, but the communication cost is quadratic in the system size. This work propose a more efficient approach that cost linear communication per decision (i.e., essentially no extra cost beyond the sender multi-casts the value). Our key technique is to adaptively form a data dissemination network with constant degree that eventually converges with bounded cost, which is amortized over decisions.


[**Constant Latency in Sleepy Consensus.**](https://eprint.iacr.org/2022/404)

- with Ling Ren. *@ACM CCS 2022.*
- Bitcoin allows nodes to join/leave the network at their own will without any advance notice. This strong dynamic participation support is unique to Bitcoin since all classical protocols require votes from a fixed quorum of nodes to make progress. To adapt the classic quorum-based approach to the dynamic setting, we introduce a new technique we call *time-shifted dynamic quorum*, which dynamically defines the quorum threshold based on each node's perceived participation level while preserving important properties of classic static quorums. This achieves the best of both: constant latency of classical protocols and dynamic participation support of Bitcoin.
- This short [Talk](https://www.youtube.com/watch?v=UvePgoPm64g) by Ling gives more technical details.


**[Multi-Threshold Byzantine Fault Tolerance.](https://eprint.iacr.org/2021/671)**

- with Ling Ren *@ACM CCS 2021*
- Classical consensus protocols assume up to 1/3 of all nodes are *corrupt* (i.e., controlled by an attacker), which is known to be necessary to tolerate occasional network failure. Bitcoin tolerates up to 1/2 corruption but the network must be completely synchronous. We believe neither is robust enough. We show that with small modifications, classical protocols that tolerate 1/3 corruption under network failure can tolerate up to 2/3 corruption when the network is synchronous. In other words, an attacker needs to control a very large fraction (2/3) of nodes, or control 1/3 + the entire network, to be successful.


**[Optimal Communication Complexity of Authenticated Byzantine Agreement.](https://drops.dagstuhl.de/opus/volltexte/2021/14834/pdf/LIPIcs-DISC-2021-32.pdf)**

- with Ling Ren *@DISC 2021*
- This short [Blog Post](https://decentralizedthoughts.github.io/2021-09-20-optimal-communication-complexity-of-authenticated-byzantine-agreement/) gives a technical walkthrough in 5 mins.
- Following Bitcoin, [a few recent works](https://decentralizedthoughts.github.io/2019-11-11-authenticated-synchronous-bft/) studied practical synchronous protocols. All of them have a common step: forward messages to all other nodes. This step easily detects conflicting views between nodes and prevents disagreement. But this increases the overall communication by a factor of n from classical protocols where nodes send their own belief only. To fill this gap, our new technique uses an *expander graph* to forward messages efficiently yet being able to detect conflicting views between nodes. Interestingly, this happens to show the tightness of [Dolev-Reischuk lower bound](https://decentralizedthoughts.github.io/2019-08-16-byzantine-agreement-needs-quadratic-messages/), which has been open for a few decades.
