# GameBattle
- 主循環是以 Player 與 NPC 交互做 Pick
- Pick 可能觸發 Trigger
- Trigger - TrickSwap : 將兩個 Cell 做交換
- Trigger - BonusPick : 額外獲得一次 Pick

## Domain

### Game (Root)
- Board
- Pick(index, playerID) => CellMarked, CellGrouped

### Record
- RecordClick(index, playerID)
- RecordMatched(indices, playerID)

### Tricker
- 計數為 X的倍數時 Trick 成立

### Scorer
- 公式計算

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
