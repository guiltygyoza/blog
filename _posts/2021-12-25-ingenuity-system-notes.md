---
layout: post
title:  "Notes on ingenuity system"
date:   2021-10-04 00:00:00 -0500
categories: crypto
published: false
---

新增構想：
或許不是為了激勵 Ingenuity，而是 enable autonomous composition of protocol legos.
假使 StarkNet 上有成千上萬個 NFT 各自代表某種有藝術價值或功能價值的代碼片段，稱作 'lego'，可以 interoperate。
問，一個新的 NFT 如何去搜尋、過濾、選擇這些 lego 來做組合？
=> 建立某種特殊的 on-chain registry, could be content addressable, for autonomous search and composition.

===

當前主流追逐的 ft / nft with provable scarcity，其實是 artificial scarcity.
弱點一：不管是鏈上還是鏈下存儲媒體，都可以直接將媒體 fork 後重發一套 nft。當然後者發佈時間晚於前者，但依舊能正當存在。
弱點二：譬喻上皆 mirror atomic scarcity -- land, physical material etc. skeuomorphic to the atomic universe.
Great Expansion 的世界不應以此為基礎。

物理世界的稀缺，由主體的需求決定：主體為肉體，需要物質和能量維生。在有限的生命時長和驅動侷限導致的探索範圍侷限，導致物質注定是稀缺的。因此一切稀缺皆圍繞在物質、土地(可以生產物質)、貨幣(可以交換物質)。
在鏈上世界裡，所謂物質都是人造物質，稀缺性都是虛構的，arbitrary、non native。

構想：
A graph, where nodes are embeddings of X. X is a family of information, such as AI procedure.
The graph is arranged by some similarity metrics.

The purpose of constructing and maintaining this graph is:
- given x ∈ X, find if x's embedding already exists in the graph and where; if nonexistent, find the best location to insert the x's embedding as a new node; the insertion process may or may not modify the rest of the graph e.g. by way of some kind of propagation.
- this would achieve idea provenance, where no duplicates are allowed. also no duplicates of AI/autonomous procedures, hence making it possible to quantify ingenuity.

If there exists an incentive model to expand this graph => we will have achieved a positive feedback loop to fuel ingenuity.

One naive concept: create a NFT system that is permission-ed on ingenuity.
- maintain a DB containing pairs of (address, payload embedding)
- every time someone wants to create an NFT, its payload is converted to embedding and searched in the DB.
- only if the entry is nonexistent would the NFT be able to be created.
- hence achieving NFT creation gated by ingenuity.
- the function that converts payload to embedding is key here. What does that function compute, and where does the computation happen.

what about utility?
isn't what's truly valuable **useful ingenuity**, not just pure ingenuity?
i.e. mutate existing concept minutely doesn't really constitute ingenuity does it?

potentially useful reference:
content addressable network operated in distributed network https://is.muni.cz/th/snvu2/ffalchi-phdthesis.pdf
