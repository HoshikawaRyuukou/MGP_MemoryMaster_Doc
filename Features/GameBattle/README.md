# GameBattle
- 與 NPC 進行回合制點擊
- 搗蛋鬼 : 給隔幾次配對會將兩個 Cell 做交換，增加記憶難度 


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
