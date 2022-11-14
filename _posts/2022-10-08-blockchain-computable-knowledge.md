---
layout: post
title:  "Civilizational computing for computable knowledge // 以文明級運算乘載可運算知識"
date:   2022-10-08 00:00:00 -0500
categories: crypto
published: true
---

Summary: Civilizational computing, far from being the most performant computing platform but certainly the most legitimate one, is suitable for programmatically manage the rights and obligations of computable knowledge. Coupling privacy tech with civilizational computing, the inventors of computable knowledge could have the cakes and eat them too.

(For context on Civilizational computing, see the previous [post](https://www.guiltygyoza.xyz/2022/09/civilizational-computing){:target="_blank"})

1- Mischaracterization of privacy: the narrative of "giving people total control over their privacy, computing environment, data ownership" is grossly misled. The essence of blockchain computing, coupled with privacy technologies, is more about slaying molochs to resuscitate our civilization from post-industrial post-modern swamp and accelerate human progress.

2- It is well known that a "bad" Nash equilibrium persists when the creator of an intellectual property has to choose between "publicizing the intellectual property at the loss of downstream personal financial returns" or "keeping the intellectual property secret, yet depriving its potential values to others."

3- The tower of human knowledge is created by knowledge composition. For example, by composing the knowledge of building a telescope and the knowledge of precise plotting through mechanical apparatus, Copernicus produced the knowledge of celestial body moving in ways inconsistent with what the Church asserted. Human progress slows down when knowledge composition is hindered.

4- With zero knowledge proofs, and restricting ourselves to *computable knowledge* (Stephen Wolfram), we could for the very first time in our history scalably break this bad Nash equilibrium: one could retain exclusive access to a piece of secret computable knowledge while making the knowledge *trustlessly use-ful* to others via private compute. *Inventors of computable knowledge could have the cakes and eat them too.*

5- Further productivity arises when composition is possible, such as through proof recursion and aggregation, which enables composing *N* secret computable knowledge with *M* non-secret computable knowledge. This brings forth the concept of *composable commercial secret* - proprietary computable knowledge composed with other proprietary computable knowledge (each private to a different party) into larger "half-opaque" computable knowledge.

6- For example, Chang knows in the form of CAD files the precise geometry of a rocket nozzle that exhibit certain mechanical properties. Nicholas knows the precise configuration of solid propellants that exhibit certain physical and chemical properties. Jae wishes to simulate the firing of a rocket using Chang's nozzle design and Nicholas's propellant configuration to analyze the resulting thrust, fuel efficiency, and mechanical stability. An interactive scheme can be devised to run the firing simulation (a public function) with the rocket geometry (a function private to Chang) and with the propellant configuration (a function private to Nicholas), and require Jae to pay fees on-chain to run such public-private simulation. We could call these *composable computable knowledge*.

7- Smart contractual terms (i.e. autonomously enforced) regulating the flow of financial value could be built around the condition of use for each composable computable knowledge. Following the example above, Chang could rate-limit computational access to her secret nozzle design and charge per-access according to some demand curve.

8- *Trustless liveness* through zk proving delegation: what if Chang wants to monetize her secret computable knowledge without either maintaining a high-uptime machine running local zk proving herself, or *trusting* some centralized servers running the zk proving for her that promise not to peek into the secret witness (thereby breaking the secrecy of knowledge)? It is possible to delegate zk proving to an MPC network that preserves the secrecy of the witness [Chiesa, Lehmkuhl, Mishra, Zhang; [talk](https://www.youtube.com/watch?v=iT_s92f3wds&ab_channel=ZeroKnowledge){:target="_blank"}]. Further research is required to enable dynamic joining/leaving of the MPC network and further reduce complexity blowup.

---

總結：文明級運算 - 即鏈上執行環境 - 絕非高效能運算平台，而是最具跨國界正統性的運算平台。這樣的運算平台適用於程式化管理可運算知識 (computable knowledge) 相關的權利與義務。倘若將文明級運算與隱私技術結合，可運算知識的發明人將能魚與熊掌兼得。

(有關文明級運算定義可閱[前文](https://www.guiltygyoza.xyz/2022/09/civilizational-computing){:target="_blank"})

1- 產業對於隱私技術潛力的錯誤認知：所謂「開發隱私技術的目的在於讓人們完全掌握其隱私、控制程式執行環境、數據所有權」是個誤解。結合鏈上運算與隱私技術的精髓在於能夠進一步解決協調問題 (moloch) 進而將我們的文明從後工業、後現代的泥淖中救出，重新加速文明進展。

2- 眾所皆知，有一種「不幸的」奈許均衡（Nash Equilibrium）: 當知識產權的創作者必須在「公布知識，讓知識被應用和迭代，卻失去對知識可能衍生經濟價值的獨佔」和「將知識保密，企圖獨佔式商業化，卻剝奪知識被自由應用所能創造的價值」之間做選擇，後者往往勝出。

3- 人類的知識高塔由知識組合創造新知築成。例如，有了「製造望遠鏡」的知識，也有了「精密製圖」的知識，透過組合這兩項知識，哥白尼創造出了「新的天體運行方式，其與教會地心說信條相違」的新知識。當知識的組合受到阻礙，人類進步隨之減速。

4- 在可運算知識 (Stephen Wolfram) 的範疇裡，零知識證明能幫助我們首度打破這種不幸的奈許均衡：一項秘密的可運算知識可以同時為他人所用並維持知識創作者的獨佔性，且當他人使用此知識之產出時是無需信任的，只需驗證證明。知識創作者能夠魚與熊掌兼得。

5- 當證明本身句可組合性，例如證明迭代（recursion）和證明聚合（aggregation），知識生產力將進一步提升。我們可以創造一種新概念：可組合的商業機密 -- 一筆私有可運算知識可以和另一筆私有可運算知識 (各自由不同實體持有) 組合成更龐大的可運算知識。

6- 舉例來說，張小姐有一筆私有 CAD 檔，高精度描述具有特定機械屬性的火箭噴嘴設計；Nicholas 先生有一筆私有固態燃料組態，擁有特定物理和化學屬性；Jae 先生希望結合張小姐的火箭噴嘴設計和 Nicholas 的燃料組態進行火箭點火模擬，以分析推進力、燃料使用率、機械穩定性。可以設計一種交互式運算系統，以私有火箭噴嘴設計以及私有燃料組態作為程序輸入，運行公開的火箭模擬程序，並要求 Jae 先生支付相應鏈上費用來執行這項公私結合的模擬運算。可將此模式稱為「可組合的可運算知識」。

7- 可利用智能合約規範在滿足何種契約條件之下，可組合的可運算知識能夠被運算使用。承上例，張小姐可以為其火箭噴嘴設計知識的使用進行流量管制，為每次使用收費，費用依某種需求曲線而定。

8- 透過零知識證明工作委託來實現「低信任的活躍性」(Trustless liveness)：倘若張小姐希望將其火箭噴嘴設計知識變現，卻不想在本機端維護高效能、高上線時間的機器生成零知識證明呢？倘若仰賴本機端生成證明，則一旦本機關機，私有知識將無法被他方使用進而產生經濟價值；倘若仰賴中心化伺服器運行證明程序，則張小姐必須信任伺服器端不將其私有知識外洩。透過多方計算網路，零知識證明工作可以被委託執行 [Chiesa, Lehmkuhl, Mishra, Zhang; [演講](https://www.youtube.com/watch?v=iT_s92f3wds&ab_channel=ZeroKnowledge){:target="_blank"}]。如何允許節點動態加入、退出多方計算網路，以及改善複雜度爆炸問題，有待進一步研究。
