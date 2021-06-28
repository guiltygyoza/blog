---
layout: post
title:  "Sandbox stage ideation"
date:   2021-06-23 00:00:00 -0500
categories: game
published: false
---

A *3D PC expedition PvE + game*,
where the player controls *hero cats navigating magical ancient cities of dramatic verticality using rich locomotive abilities*
to help overcome *hostile creatures, stormy environment, suffocation in rising water level, and other adversarial teams of hero cats*
to achieve *finding and preserving treasure, locating and escorting stranded magical kittens, and survival at extraction from the top of the city structures*.

---







---

Goal
- Sandbox as a stage, enabling stories
- PCG-driven architecture, terrain
- RL-driven character animation

開發任務
- 幾何結構堆疊的空間，RL 角色動畫移動、攀爬
  - 用 wpo 推拉方塊 mesh 表面節點
  - 用 tensorflow-ue4 接 wpo 推拉 mesh 表面節點
  - 寫 blog 描述上述技術
  - 了解 AMP/DeepMimic 的 python 框架，思考如何接入 UE4

Concept
- 古都，風沙 or 漲潮？
- 尋寶
- PvP
- PvE -- 古都和沙裡(?)或/和水裏的生物、幽靈
- 隨著沙高、水高提升，玩家可以進入更高的樓層
- 最後從樓頂 extract
- 移動機制
  - 水平移動
  - 垂直移動 -- 攀爬、垂降 (rapple descend)
  - 水中移動、沙中移動 (半透明的沙？)
  - 角色動畫由 RL 輔助生成
    - reference: https://xbpeng.github.io/projects/AMP/index.html / https://xbpeng.github.io/projects/DeepMimic/index.html

Idea
- 千島湖？
- 龍門飛甲
- Mt Saint Michel
- 都市建築結構由 PCG/ML 輔助設計 (layout! ~AI-assisted P&R)
- 除 extraction 和尋寶外，加入更多目標，擴大策略空間
- Faberge egg 蛋中城市
- character 都是四腳動物 mechanical clone
  - 如何戰鬥？射擊/格鬥
  - 如何在水中移動？
  - 每隻四腳動物皆獨特 -- MaoPunk 的貓？角色 NFT?
- 寶藏是 NFT art 可擁有、交易、拍賣
- 特殊技能是 NFT
- 角色、角色特徵是 NFT
- 如何允許跨 team 的溝通？跨 team 的 coop?

PCG 參考資料
- L4D: https://steamcdn-a.akamaihd.net/apps/valve/2009/ai_systems_of_l4d_mike_booth.pdf
