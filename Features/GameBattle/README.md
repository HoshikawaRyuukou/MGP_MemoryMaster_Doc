## Core
- Game與NPC之間僅靠 CellGrouped 聯繫，Game只在乎誰(ID)點了哪裡(Index)，產生了怎樣的結果(CellGrouped)

### Game
- 創建盤面
- 點擊盤面 | Evt: CellGrouped
- 查詢盤面

### TurnLoop
- 回合輪轉邏輯

### NPC
- 紀錄盤面
- 產生點擊輸入

### Player
- 玩家的點擊規則

### PlayerRecord
- 玩家的數據

### Scorer
- 計分規則





# Feature
- 遊戲流程採**回合制**
- 開局可選擇遊玩**回合模塊**
- 並在結算時給予個別獎勵

## TurnLoop
- 提供回合控制介面 ITurnControl, IPickControl
- 控制介面的組成包含(可執行判定/主互動/結算獎勵)
- 採輪循方式對模塊介面進行可執行判定運算，依序執行，直到遊戲結束

## Modules
有以下模組

### Player
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


## Flow
- 玩家1 輸入
- 檢查 GameClear, TrickSwap
- 玩家2 輸入
- 檢查 GameClear, TrickSwap

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
