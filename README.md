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
### Entity - GameBaseModel
- 是否能點擊
### Entity - MatchCore
- 盤面目標
- 盤面紀錄
- 生成/選擇

### UseCase
- 改變遊戲狀態( Retry / New Round / Back Lobby )
- 建置盤面
- 選擇目標

<br/> 

## Domain - GameClassic
### Entity
- 支援次數
### UseCase
- 選擇模式參數
- 支援(次數限制/期間禁止選擇)

<br/> 

## Domain - GameBattle
### Entity

### UseCase
- 選擇模式參數
- 干擾

<br/> 
