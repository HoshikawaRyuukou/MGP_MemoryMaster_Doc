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


NPC模式
1. 選擇參數
2. 建置遊戲
3. 用戶操作
4. 結算遊戲


## 前述
- 這是一個記憶配對遊戲
- 基本的記憶配對Gameplay
- 減少操作中斷感(點-點-配對)
- 難度調整(輔助/干擾)
- 陪玩
- 成就

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
