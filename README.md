## 前述
- 這是一個記憶配對遊戲
- 基本的記憶配對Gameplay
- 減少操作中斷感(點-點-配對)
- 難度調整(輔助/干擾)
- 陪玩
- 成就

<br/> 

## Domain - App
### Entity
- 金幣
### UseCase
- 載入使用者資料

<br/> 

## Domain - Setting
### Entity
- 靜音
- 語言
### UseCase
- 調整聲音
- 切換語言

<br/> 

## Domain - Collection
### Entity
- 收集冊
### UseCase
- 瀏覽收集冊
- 檢查金幣是否足夠解鎖
- 消耗金幣解鎖收集項目

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
- 改變遊戲狀態( Retry / New / Finish )
- 建置盤面
- 選擇格子 (定義選擇完成)

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
