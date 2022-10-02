## 前述
- 這是一個記憶配對遊戲
- 減少操作中斷感(點-點-配對)
- 難度調整(輔助/干擾)
- 陪玩
- 成就

-------------------------------------

## Feature - 收集冊
- 使用者可以查看所擁有的圖像 ( Icon / Photo )
- 使用者消耗金幣解鎖圖像

## Feature - 遊玩模式(共同項)
- 開局詢問玩家遊玩選項
- 配對成功擊獲得金幣 (玩家看到即時金幣狀態)
- 結算成果獲得金幣
- 重開新局/重玩/離開

## Feature - 遊玩經典模式
- 無間斷點擊 : 因為是單人操作且有計時數據，只要是反向的 Cell 就能點擊，以增加順暢感
- 計次反轉輔助 : 將未配對的 Cell 翻正，但是翻正期間不能點擊

## Feature - 遊玩對戰模式
- 與 NPC 進行回合制點擊
- 搗蛋鬼 : 給隔幾次配對會將兩個 Cell 做交換，增加記憶難度 

--------------------------------

## Domain
### Board
* Board size = groupUnit x groupCount
* Board cellState: Idle/ Marked/ Matched
* Board 最多只能有 groupUnit 個 cell(Marked)
* Board 所有 cell(Matched) 為 clear

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

<br>

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
