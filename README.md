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

### Flow
- 選擇Option
- 創建遊戲
- 玩家/NPC/Trick

### Game 域規則
- 一次Group互動(Pick Unit次)
- 終極目標是讓 GameState isClear false -> true 
- 當全部Cell matched 為結束

### 思考
- 玩家/NPC點擊次數是域規則? | 不是，可以是玩家點4次換npc點2次

