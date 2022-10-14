# GameBattle
- 主循環是以 Player 與 NPC 交互做 Pick
- Pick 可能觸發 Trigger
- Trigger - TrickSwap : 將兩個 Cell 做交換
- Trigger - BonusPick : 額外獲得一次 Pick

## Modules

### GameCores
- 操作以 Turn 的方式進行
- 預設第一動為 Player/NPC Pick
- Turn 執行期間觸發的 Command 將放入佇列中，並作為之後的 Turn 執行
- 當佇列為空且未結束，則取下一動 Player/NPC Pick
- 可以對 Command 註冊 Handler

#### GameState
- CellMarked, CellGrouped, IsClear

#### Turn
- 向其註冊操作，必以輪循方式執行

### NPCs
- 定義 NPC 操作
- 會記錄 CellMarked, CellGrouped 訊息，並以機率做 Pick

### Players
- 取得玩家輸入

### Records
- 紀錄 CellMarked, CellGrouped 與操作對象

### Tricks
- 計數為 X的倍數時 Trick 成立





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
