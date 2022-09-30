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

## Battle
### Game
- Create/ Start/ Pick/ Stop
- Created/ TurnChanged/ Marked/ Grouped/ Tricked/ Clear/ Stopped


## GameCore 域規則

### 核心域(VO) BoardOption
* groupUnit / groupCount

### 核心域 Board
* size = groupUnit x groupCount
* 總共具有 size個 Cell
* Cell的狀態: Idle/ Marked/ Matched
* 最多只能有 groupUnit個Cells 處於 Marked
* 使用 Group來將 Marked -> Idle or Matched
* Action: Create/ MarkCell

## BattleGame 
### 核心域 Game
* 有1個 Board / 1個 Player / 1個NPC /1個Tricker/ 1個BoardNote / 1個 Turn
* Board(Clear) -> Game(Clear) 
* 將Board事件紀錄於 BoardNote

### 核心域 Player
* 有1個 Board / PlayerState
* 接受 index輸入 做Pick

### 核心域 NPC
* 有1個 Board / 1個 BoardNote
* NPC查 Note 做 Pick

### 輔助域 Tricker
* 有1個 Board / 1個 Turn
* 每當 Turn.Count 為X的倍數時成立
* Trick 為選出兩個 cell(Index) 做交換 / 這裡只是選出沒有實際交換，交換的動作是表示層的行為


### 思考
- 玩家/NPC點擊次數是域規則? | 不是，可以是玩家點4次換npc點2次

