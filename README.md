# MGP MemoryMaster Doc
- 這是一個記憶配對遊戲
- 減少操作中斷感(點-點-配對)
- 難度調整(輔助/干擾)
- 陪玩
- 成就

## Module
* 本專案採用按組件打包(Package by Component)的方式
* Components 與 Features 均遵守 Clean Architecture 分層/依賴關係
* Component 主要的定位是**提供功能**
* Feature 主要的定位是**提供使用者情境**

## Components
組件額外設置 API (Facade)，對組件操作一律只透過 API
- Collections 收集核心
- GameShared 遊戲共用邏輯
- GameWidgets 遊戲共用元件
- Settings 設定
- Shared Component共用
- Users 使用者

## Features
- CollectionAlbum 收集冊
- Credit 致謝
- GameBattle 遊玩對戰模式
- GameClassic 遊玩經典模式
- Support 支持

----------------------------------------
### 思考
- 玩家/NPC點擊次數是域規則? | 不是，可以是玩家點4次換npc點2次
- Scorer 跟 Game 有域的關聯嗎? | 沒有，沒有Scorer並不影響Game的運作，沒有評分的環節也無所謂，評分是屬於這個應用程序的機制

-----------------------------------------
### 備案 多結束條件
### GameSolver
- 包含多個 GameSolvePolicy，其中一個成立即結束

### GameSolvePolicy
- 判定遊戲是否結束
