# Feature
- 遊戲流程採**回合制**
- 開局可選擇遊玩**回合模塊**
- 並在結算時給予個別獎勵

## TurnLoop
- 提供模組控制介面(ITurnControl)
- 提供檯面介面(IGroupedCallback)供模組實作，是 Module的流程變化來源
- 採輪循方式對模塊介面進行可執行判定運算，依序執行，直到遊戲結束

## Modules
- 回合模塊之間獨立不相關
- 模塊關心的是Board事件
- 模塊之間可以設計的會互相影響(透過應用層，模塊A的結果將導致模塊B發生流程變化)，只是在這個案例中，不希望弄到太複雜。
- 回合模組的組成包含(可互動判定/主互動與結算獎勵)，
- 回合模塊可實作回合介面 (IMarkedCallback/IGroupedCallback)
- 回合模塊的流程控制由應用層處理，有以下模組

### Player (預設不可選)
- 玩家點擊指定個對象，根據結果給予及時獎勵
- 並記錄玩家點擊/配對數值
- 結算數值給予獎勵

### NPC
- 可選先後手
- NPC點擊指定個對象
- 記錄明牌
- 結算根據輸贏給予獎勵

### TrickSwap
- 每當一定回合數觸發一次，交換檯面上的兩個對象
- 結算根據難度給予獎勵




-----------------------------------------------



## Application

### PlayGame
* Option, Game
* 創建遊戲

### GameHandler
* Note, Tricker
* CellPickRequested: 
* CellMarked: Note/Record 紀錄
* CellGrouped: Tricker 計數 / Note/Record 紀錄
* GameCompleted:

### EvaluateGame
* Option, Record, Scorer, UerAPI
* 根據 遊戲參數/遊戲紀錄 來計算分數，並給予獎勵
