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
|  Name  | Description  |
| :- | :- |
| ControlSound | 調整聲音 |
| ChangeLanguage | 切換語言 |
| LoadUser | 載入使用者資料 |
| AccessCoin | 存取金幣 |
| AccessCollectionBook | 存取收集冊 |
| UnlockCollectionBookByCoin | 使用金幣解鎖收集項目 |

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
