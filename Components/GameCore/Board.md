# Board 

## 定義
* group : 組-配對的基本單位
* groupUnit : 一組內有幾個 Cell
* groupCount : 總共的組數

## 規則
* Board 的 Cell 總數 = groupUnit x groupCount
* 可標記 Cell 為 isMatched
* 當所有 Cells 為 isMatched 時 Board 為 isClear

## 操作
* Create(groupUnit, groupCount)
* CheckGroup(indices)
* SetMatched(indices)
* IsMatched(index)  
* IsClear() 
* GetCell()
* GetCells() / GetCells(indices)
* GetUnmatcheds()
