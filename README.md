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
- 詢問玩家遊玩選項
- 配對成功擊獲得金幣 (玩家看到即時金幣狀態)
- 結算成果獲得金幣
- 重開新局/重玩/離開

## Feature - 遊玩經典模式
- 無間斷點擊 : 因為是單人操作且有計時數據，只要是反向的 Cell 就能點擊，以增加順暢感
- 計次反轉輔助 : 將未配對的 Cell 翻正，但是翻正期間不能點擊

## Feature - 遊玩對戰模式
- 與 NPC 進行回合制點擊
- 搗蛋鬼 : 給隔幾次配對會將兩個 Cell 做交換，增加記憶難度 

-----------------------------------------------








#### 點擊格子
- 輸入 : 格子 index 
- 輸出 : 
  - Failed : 玩家禁止輸入 / index已經被選
  - Resulted : 格子Index
- 步驟 :
  1. 檢查index狀態
  2. GameCore select操作

#### 配對格子
- 輸入 : 格子 indices 
- 輸出 : 
  - Resulted : isMatched / indices
- 步驟 :
  1. 檢查


#### 翻轉支援(次數限制)
- 輸入 : 支援 On/Off
- 輸出 : 
  - Resulted : isOn / Count
- 步驟 :
  1. 檢查isOn狀態 / 檢查次數
  2. 成立則扣除次數 (isOn: False -> True)


<br/> 




## Domain - App
### Entity - AppSetting
- 靜音
- 語言

### Entity - User
- 金幣
- 收集冊

### UseCase


<br/> 

## Domain - GameBase
### Entity - Round
- 生成盤面 ID
- 查詢 ID 
- 操作 ID ( Select / Match )

### Entity - History
- 盤面紀錄
- 隨機取數 (特化結構 RandomizedSet.Random BigO(1))
- 高階隨機 (根據紀錄/正確率)

### UseCase
|  Name  | Description  |
| :- | :- |
| ConfirmBoard | 確認盤面參數 |
| BuildBoard | 建置盤面 |
| ControlGame | 封裝共同遊戲狀態請求 ( Retry / New / Finish ) |

<br/> 

## Domain - GameClassic
### Entity
- 支援次數
### UseCase
- 設置模式參數
- 支援 (次數限制/期間禁止選擇)

<br/> 

## Domain - GameBattle
### Entity

### UseCase
- 設置模式參數
- 干擾

<br/> 
