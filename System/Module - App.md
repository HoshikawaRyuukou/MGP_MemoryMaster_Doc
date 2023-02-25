# Module - App
- 負責 Features 的加載與導航
- 應用級的用例: 始化時須建立新的用戶

## Navigator 
![Module_App02](images/Module_App.png)
上圖的箭頭並不是指依賴而是使用者操作流，當使用者在 Feature A 中要導航至 Feature B 時，不直接依賴，以維持 Feature 模組的獨立性，因此這個 Navigator 並不屬於 Feature A or B 而是屬於 App。

使用 Navigator Pattern <詳見> 