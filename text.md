## 📅 專案時程與任務分配 (Project Schedule & Tasks)

### 1. 👥 團隊成員任務分配 (Team Roles)

| 成員 | 角色 (Role) | 負責內容 (Responsibilities) |
| :--- | :--- | :--- |
| **林東毅** | **AI & Backend Core** | • WhisperX 模型整合與優化<br>• Transformer 摘要與翻譯實作<br>• 撰寫 AI 處理邏輯 (Service Layer) |
| **張恩豪** | **Frontend (React)** | • React 專案架構與 UI 切版<br>• 開發錄音、檔案上傳與結果顯示介面<br>• RWD 行動端適配與互動優化 |
| **蘇子皓** | **DevOps & Integration** | • Django 環境建置與 DRF API 接口開發<br>• FFmpeg 音訊預處理串接<br>• 系統整合、除錯與最終部署 |

---

### 2. 📊 專案甘特圖 (Gantt Chart)

```mermaid
gantt
    title 語音轉文字專案開發時程 (10/01 - 12/21)
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%d
    
    section 初始階段
    需求分析與規格確認        :done,    p1, 2024-10-01, 2024-10-07
    環境建置 (Django/React)   :done,    p2, 2024-10-05, 2024-10-12

    section AI 與後端
    WhisperX 模型整合         :active,  b1, 2024-10-13, 2024-10-27
    FFmpeg 音訊處理模組       :         b2, 2024-10-20, 2024-11-03
    Transformer 摘要翻譯      :         b3, 2024-10-28, 2024-11-10
    API 接口開發              :         b4, 2024-11-01, 2024-11-15

    section 前端開發
    UI/UX 設計與切版          :active,  f1, 2024-10-13, 2024-10-27
    錄音與上傳功能實作        :         f2, 2024-10-28, 2024-11-10
    結果展示介面優化          :         f3, 2024-11-05, 2024-11-18

    section 整合與交付
    前後端 API 串接           :         i1, 2024-11-15, 2024-11-30
    系統測試與 Bug Fix        :         t1, 2024-12-01, 2024-12-15
    文件撰寫與成果發表        :         t2, 2024-12-15, 2024-12-21
```
```mermaid
graph LR
    %% 樣式定義
    classDef critical fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    classDef normal fill:#e1f5fe,stroke:#01579b,stroke-width:1px;
    classDef start_end fill:#f9f,stroke:#333,stroke-width:2px;

    Start((Start 10/1)):::start_end --> Req[需求分析]:::critical
    Req --> Env[環境建置]:::critical

    %% 分支任務
    Env --> Whisper[WhisperX 整合]:::critical
    Env --> UI[前端 UI 設計]:::normal
    
    Whisper --> Trans[摘要/翻譯功能]:::critical
    Trans --> API[API 開發]:::critical
    
    UI --> Comp[前端元件實作]:::normal
    
    %% 整合
    API --> Inte[前後端串接]:::critical
    Comp --> Inte
    
    Inte --> Test[系統測試]:::critical
    Test --> End((End 12/21)):::start_end

    %% 關鍵路徑連結樣式 (紅色)
    linkStyle 0,1,2,4,5,7,8,9 stroke:#ff0000,stroke-width:2px;
```
