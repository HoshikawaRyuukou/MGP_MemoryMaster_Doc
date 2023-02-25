# Module - Core
- 提供應用程式**內**的業務操作
- 定義接口以隔離實作細節與改變
- 一般情況只提供數據，沒有操作 UI
- 主要為 Feature 所使用

Core 可以是包含業務規則的 CA 分層，如圖左邊。
Core 可以是僅將外部服務轉換至內部服務，如圖右邊。
![Module_Core](images/Module_Core.png)

---

**以下是專案的 Core**
  | Name | Impl | Description |      
  | --- | --- | --- |
  Colors | Only Adapter | 顏色操作     
  DateTimes | CA | 日期操作     
  Loggers |  Only Adapter |日誌操作     
  Sounds | Only Adapter | 聲音操作    
  URLs |  Only Adapter |連結訪問操作  
  Users | CA | 金幣/收集/設定   