---
layout: post
title:  "Double Blinding Onchain // 鏈上雙盲"
date:   2022-11-02 00:00:00 -0500
categories: crypto
published: true
---

Special thanks to [Lev Stambler](https://twitter.com/StamblerLev){:target="_blank"}, [Arthaud Mesnard](https://twitter.com/arthaud_){:target="_blank"}, and [Ryan Cao](https://twitter.com/nayr_oac){:target="_blank"} for thoughtful reviews.

Summary: Zero knowledge proof helps improve coordination by allowing for "double-blinding" - the seller of computable knowledge (definition from Stephen Wolfram) retain exclusive access to the knowledge in sale, and the buyer of computable knowledge retain exclusive access to private test suite - through the process of verification until the moment of settlement. Blockchain helps improve coordination by enforcing such interactive or non-interactive process through code that runs credibly neutrally. Proof delegation helps improve coordination by delegating proof generation by the owner of exclusive computable knowledge to a trustless third party.

0- This essay is meant to poke at radical possibilities and indicate they are actionable.

1- Mischaracterization of DAO: the notion that "DAO is company but on-chain" is grossly underestimating the potential of DAO. DAO represents coordination enforcement by code that runs credibly neutrally. But why coordinate onchain when for most scenarios offchain coordination is much cheaper and inexpensive?

2- DAO as company is half illuminating and half misleading. The illuminating part lies in seeing DAO as INC - [Internet Native Company](https://twitter.com/arthaud_/status/1577743392666099712){:target="_blank"}. The misleading part lies in the connotation of existing company structures and processes, and the suggestion that we ought to move those structures and processes onchain.

3- DAO has large unrealized potential in distributing value to verifiable sweat.

4- Bitcoin mining is a primitive form of verifiable sweat. Upon hash verification, we know some corresponding mining sweat has occurred as intended.

5- Topology's Solve2Mint 2 (S2M2; [link](https://s2m2.netlify.app/){:target="_blank"}) experiment demonstrates the potential of verifiable sweat in a human-centric context. S2M2 comprises 50 puzzles of the same kind - solver is asked to find a closed path that pass through all circles and squares on the grid, while satisfying constraints such as going straight through circles and turning corners at squares. S2M2 was designed as a gate for Isaac playtesting (note: Isaac is another experiment of Topology that centers around onchain three-body physics simulation and player coordination) - an account must have solved one S2M2 puzzle in order to queue up in Isaac, otherwise the transaction to queue up will revert. For simplicity, no notion of token was introduced: the Isaac contract simply queries the S2M2 contract whether the caller that asks to queue has solved a puzzle or not.

6- S2M2's human-centric-ness lies in the puzzle being quite bruteforce-resistant while being fairly easily solvable by human intuition; it also lies in the explanation of the rules of puzzle only available as inline human-readable comment in S2M2's public github repository.

7- The Isaac-S2M2 relationship can be understood abstractly as: the access to A requires some verifiable sweat invested into B, where the verification is performed autonomously - via smart contract execution. But how do we generalize beyond game playtesting and casual puzzles for killing time? How to understand the potential of "distributing value to verifiable sweat"?

8- Let us start with a simple scenario. Bob announces publicly that a $1M bounty is held onchain and will be transferred to the account that first submits a program p that (1) is a pure function that takes object of type Ti as input, returns object of type To as output, (2) meets all capability requirement (able to map each object of type Ti into corresponding object of type To in a test suite onchain), and (3) meets all performance requirement (p takes at most X amount of runtime memory and Y latency across all test case in the test suite). Basically, Bob puts up a programming problem onchain with a bounty to be transferred atomically with the first qualifying solution submission. Note that the test suite and program verification procedure are also onchain. We can call this pattern quite aptly “onchain Kaggle”. (Note: in a similar note, Bob can put up a math problem onchain to be verified via [Lean](https://leanprover.github.io/){:target="_blank"} implemented in some smart contract / verifiable programming language.

9- The problem of this setup is three-fold. First, there exists ways where Bob can hijack the solution submission and withhold the bounty. For example, Bob can collaborate with a miner or validator of the network to frontrun the first qualifying solution submission with the exact same calldata (calldata carries the solution). Second, what if the solvers believe that program p is highly valuable beyond the $1M bounty such that solvers withhold their solutions and prefer to find higher bidders, which may be nonexistent? Third, given the verification procedure and test suite are onchain, solvers can memorize or overfit the test cases and come up with bad solutions that would be useless for Bob.

10- Here comes zero knowledge proof to the rescue. Bob can commit (via some functional commitment scheme) to private test suite. All candidate solutions are run against both onchain public test suite and Bob's private test suite. This helps "blind" the solvers against knowing all the test cases, while guaranteeing that Bob does not change the private test suite upon receiving a good solution. We can call this Verification Blinding.

11- Zero knowledge proof also allows the solver to run its solution against tests without revealing the solution. We can call this Solution Blinding.

12- Note that Solution Blinding allows the solver to rent-seek its solution, or equivalently, creating pay-to-call verifiable API - "if you want to utilize my program p, you can supply me some desirable input x plus some fee, and I will return p(x) to you along with a zero knowledge proof that proves the validity of p's execution hence correctness of p(x)."

13- If we pair Verification Blinding with Solution Blinding and enforce their respective computation onchain by verifying the proofs onchain, we get Double Blinding Onchain (DBO). DBO allows for buyer of computable knowledge (Stephen Wolfram; solution to some computable problem) to not reveal all verification schemes, and seller of computable knowledge to not reveal the knowledge itself. Upon successful verification, the computable knowledge can be transferred, or utilized in the manner of pay-to-call verifiable API.

14- Given a DBO protocol for some type of computable knowledge, DAO can be created to both develop and monetize computable knowledge, similar to how companies are created to develop and monetize assets, whether it's real estate assets (e.g. WeWork) or proprietary industry knowledge (e.g. McKinsey). Besides DAO, DBO-powered marketplaces for computable knowledge could be built which require less trust and can operate globally - inheriting the property of public blockchain.

15- Let us assume at some point in the future, the entire suite of chip verification tools involved to create some processor IP have been implemented in some verifiable programming language such as Cairo, Noir, or Lurk (or equivalently, the tools implemented in C++ run on some verifiable RISC-V). A DAO can be created as an onchain chip design house that hires no one, has no office, and accepts contribution from anyone through a DBO protocol. The DAO's core devs write test suites for chip components to be implemented. Anyone can submit concrete RTL implementations to be verified and accepted into the DAO, for which the person receives DAO equity - perhaps we can call this verifiable sweat equity. Accounts that possess sweat equity beyond a certain threshold are invited into the core dev cohort. This mirrors the spirit of [CarseDAO](https://isaac-book.netlify.app/#/eng/isaacdao){:target="_blank"}, where contributors to onchain subjects governed by DAO receive voice in the DAO - contribution is credibly neutrally verified.

16- Many “thorns” exist - for example, how to run a program p secret to the seller over some secret test input secret to the buyer? One solution is to build secure MPC network with one-of-N honesty collectively holding both the secret program and the secret test input. Recent research indicates practicality of collaborative proving (Boneh et al.) as well as zk proving delegation (Chiesa et al.).

---

特別感謝 [Lev Stambler](https://twitter.com/StamblerLev){:target="_blank"}、[Arthaud Mesnard](https://twitter.com/arthaud_){:target="_blank"} 和 [Ryan Cao](https://twitter.com/nayr_oac){:target="_blank"} 的用心回饋。

總結：零知識證明技術能透過「雙盲」模式改善協作：在有價可運算知識（定義來自 Stephen Wolfram）的驗證過程中，賣家保持知識私有，同時買家也保持測試集私有，直到驗證通過後進行交易結算。區塊鏈能將上述程序 - 無論是交互式或非交互式 - 透過智能合約方式的自動執行，保有可信賴的中立性。透過零知識證明委託，證明生成工作可以委託給無需信任的第三方完成。

0- 本文旨在揭示激進的未來可能性、我們已具備初步技術可以採取行動。

1- 對 DAO 的誤解：所謂「DAO 是鏈上公司」嚴重低估 DAO 的潛能。DAO 代表中立程序強制執行協作系統。然而，為何要在鏈上進行協作？尤其在大多數現有情境中，鏈下協作既低成本又高效率。

2- 「DAO 是鏈上公司」這樣的類比同時闡明了 DAO 的潛力，卻誤解了 DAO 的根本屬性。闡明的部分請見 [INC](https://twitter.com/arthaud_/status/1577743392666099712){:target="_blank"} (Internet Native Company；網路原生公司)。誤解的部分在於把 DAO 和現實世界公司的組織架構和流程聯繫在一起，並且暗示我們應該思考如何把現有公司架構和流程上鏈。

3- DAO 有一個尚未開始實現的巨大潛能：分配價值給可驗證的勞動付出者。可以稱之「可驗證血汗股權」(verifiable sweat)。

4- 比特幣挖礦正是一種可驗證血汗股權。哈希值確認無誤後，礦工即獲得相應的比特幣網路股權。

5- Topology 的 Solve2Mint 2 實驗（S2M2；[鏈結](https://s2m2.netlify.app/){:target="_blank"}）具體展現了可驗證血汗股權的潛力，且具備人本性質。S2M2 一共有 50 道相同類型的謎題：在網格上找到一個封閉路徑，通過網格上所有圓形和方形，並且滿足特定條件，例如通過圓形時必須直行、通過方形時必須轉彎。當初設計 S2M2 的目的在於為 Isaac (Topology 的三體遊戲實驗，在鏈上執行物理系統模擬，並考驗玩家協作) 提供封測入場券，只有解過 S2M2 題目者能夠排隊進場參加 Isaac 封測，否則排隊進場交易會回滾 (revert)。為簡單起見，S2M2 沒有將解題證明實作成代幣標準；Isaac 合約在收到排隊進場交易時，首先呼叫 S2M2 合約的一個外部函數，檢查交易發起地址是否有成功解題，而非檢查交易發起地址是否擁有某代幣。

6- S2M2 人本性質在於謎題本身較難自動化硬解，憑藉人類直覺卻相當容易解決。另外，謎題本身規則並沒有在前端闡明，而是選擇在開源合約代碼裡以自然語言註釋解釋。

7- Isaac 與 S2M2 之間的關係可以抽象理解為：必須在系統 B 具有可驗證血汗股權才能存取系統 A，並且驗證是透過智能合約自動執行的。但是，如何才能從遊戲封測和休閒解謎遊戲的情境裡抽身出來，想像更概括的情境？如何理解可驗證血汗股權的潛力？

8- 考慮一個簡單的情境：Bob 在鏈上發佈一道編程問題，並懸賞一百萬美元獎金；參賽者提交的程序必須滿足以下條件 (1) 是一個純函數 (pure function)，輸入物件的類是 Ti，輸出物件的類是 To；(2) 滿足所有功能條件 (能將測試集裡所有 Ti 類物件轉換成對應的 To 類物件)；(3) 滿足所有效能條件 (執行測試集內任一筆測試，程序至多需要 X 記憶空間、Y 時間延遲，即限制時間複雜度和空間複雜度)。基本上，Bob 懸賞的獎金將自動轉移給第一個提交滿足所有條件的程序的地址。注意，整個測試集和驗證程序都在鏈上。我們可以將這個模式稱作 "鏈上 Kaggle / Leetcode"。(ps 運用類似的模式，Bob 可以在鏈上發佈數學證明問題，透過 Lean 來驗證所提交的數學證明，其中 Lean 必須由可驗證語言或智能合約語言實作；有關 [Lean](https://leanprover.github.io/){:target="_blank"})。

9- 此模式至少有三個問題。第一，Bob 有辦法攔截提交的程序，取貨不付款。例如，Bob 可以和礦工或驗證節點共謀搶先交易 (frontrun)，看到成功滿足所有條件的提交時 (提交位於交易的 calldata 裡) 帶著提交跑路，不讓提交上鏈因此不必轉移獎金。第二，如果知道答案的人認為此答案價值大於懸賞的獎金金額呢？理性上此人會將答案保密 (因為一旦提交，答案即對所有人公開)，企圖尋找更高的獎金選賞，但更高的獎金可能不存在，導致供需落差。第三，既然測試程序和測試集都在鏈上公開，解法可以取巧記憶測試案例，或者採用過度學習 (overfitting)，導致滿足所有條件的解法對 Bob 實際用處不大。

10- 零知識證明前來拯救。Bob 可以針對測試集提出多項式承諾；所有提交的程序都在 Bob 本地跑公開測試與私有的測試，並且生成執行的零知識證明。這樣的作法讓提交者「單盲」，看不到私有測試集，同時確保 Bob 無法在收到好解法時偷天換日、在本機臨時調換測試集。我們可以把這樣的作法稱作「盲測試」。

11- 當然，零知識證明也能讓解題者將解法保密，在本機跑測試程序，不公開解法。我們可以把這樣的作法稱作「盲解法」。

12- 注意，盲解法的作法可以讓解題者以解法尋租，等同付費呼叫 API，API 回應包含零知識證明讓呼叫者確認 API 端執行無誤 - 「如欲使用我的程序 p，你可以付費並提交輸入值 x，我會把 p(x) 回傳給你，並附上一筆零知識證明，驗證後能確定我沒有作弊。」

13- 我們可以將盲測試和盲解法兩種模式合併，並於鏈上驗證兩邊執行所生成的零知識證明 - 我們可以將此模式稱作「鏈上雙盲」(DBO; Double Blinding Onchain)。鏈上雙盲讓有價可運算知識 (Stephen Wolfram) 的買家不必揭露其驗證手段，同時賣家也不必揭露知識本體。成功驗證後，買賣雙方可以進行後續程序，例如銀貨兩訖，或者開始付費呼叫 API。

14- 可以在 DBO 協議上建立 DAO，來開發可運算知識或者將可運算知識變現，如同現實世界公司開發資產並將資產變現。除了 DAO 之外，也可以在 DBO 協議上建立市場，促進低信任的可運算知識買賣流動，並且此市場繼承公鏈的無國界屬性，形成無國界的可運算知識市場。

15- 假想有一天，用於處理器 IP 晶片驗證所需的工具已被實作在可驗證語言上，例如 Cairo、Noir、Lurk (或以 C++ 實作並運行於可驗證 RISC-V 上，例如 Risc0 的作法)。可以建立一個晶片設計 DAO，沒有實體辦公室，沒有雇用任何員工，並且在區塊鏈上向全世界人才開放無需許可提交貢獻，所有貢獻都透過 DBO 協議驗證，在價值交換之前保有提交私有性和測試集私有性。DAO 的核心開發團隊針對需要開發的新組件撰寫新的測試集。任何人都能提交 RTL 實作方案 (註：RTL 為 Register Transfer Language，為設計晶片用的編程語言)，透過 DBO 協議驗證成功，提交者能獲得 DAO 分配股權 - 即可驗證血汗股權。擁有一定比例的可驗證血汗股權即自動獲邀加入 DAO 核心開發團隊。這樣的模式呼應 [CarseDAO](https://isaac-book.netlify.app/#/eng/isaacdao){:target="_blank"} 的設計 - 貢獻者自動獲得 DAO 內話語權，且貢獻內容於鏈上驗證。Topology 的 [Christopher](https://github.com/topology-gg/christopher){:target="_blank"} 即往此方向邁進的一小步。

16- 鏈上雙盲模式可能面臨的最大技術難題為：如何中立的、低信任的執行 p(x)，其中 p 是只有賣家知道的知識本體，而 x 是只有買家知道的測試集？一種解法是將零知識證明工作委託給安全多方計算網路 (secure multi-party computation；secure MPC)，具備「只要網路還有至少一個節點誠實，隱密性不破」的特性，讓網路分散式持有私有知識和私有測試集。近日研究 (Boneh et al. 和 Chiesa et al.) 顯示此方法已可實踐並具實用性。要解決的難題是，證明委託讓複雜度倍增，安全多方計算也會讓複雜度倍增，兩者若為乘積關係將導致複雜度爆炸。
