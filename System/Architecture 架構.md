# Architecture 架構
應用程式是由許多不同模組之間協同運作的，大多數的模組都使用 Clean Architecture，該架構說明 <詳見>

本專案採用的模組依賴關係如下

![Module_App01](images/Modularization.PNG)

## App Module
- 應用程式的入口點
- 負責 Feature 之間的導航
- 依賴所有 Modules
- 使用 Clean Architecture
- 詳見

## Feature Module
- Feature 是 App 的子場景，提供完整的使用者互動流
- Feature 可依賴 Core 
- Feature 不依賴其他 Feature
- Feature 之間的關係建立在 App 之中
- Standalone : 對此專案無任何依賴(可跨專案外掛)
- Based on this project : 依賴 Core (不可跨專案)
- 使用 Clean Architecture
- 詳見

## Core Module
- 為此 App 提供共用功能 (Ex:用戶系統/日誌系統/聲音系統)
- 使用 Clean Architecture or 簡單的 DIP 外部服務
- 詳見
