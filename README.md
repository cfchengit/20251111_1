​​```mermaid
graph TD
    subgraph Frontend Layer (VS Code IDE)
        A[學生 (開發者)] --> B(Vibe Coding 流程);
        B --> C{程式碼: 標記顏色的指令};
        C -- "滑鼠接觸/懸停觸發 [3]" --> D(CCQ 教學模組);
    end

    subgraph CCQ Core Intervention Loop
        D --> E(擷取情境與教學內容);
        E --> F(顯示教學內容 & 彈出 H5P 測驗卷 [3]);
        F --> G{學生作答 (結構化驗證)};
    end

    subgraph Backend & Data Management
        G --> H(連結至教學平台/LMS);
        H --> I[測驗內容 (H5P/SCORM)]
        H --> J(作答內容記錄與成效評估 [3]);
        J --> K[數據儲存庫 (Heval數據)];
    end

    style A fill:#D0E7FF,stroke:#333,stroke-width:2px
    style K fill:#FFD2A8,stroke:#333,stroke-width:2px
    style F fill:#FFFACD,stroke:#DAA520,stroke-width:2px

    B -- "LLM 代理協作" --> C
    G -- "傳輸作答內容" --> H
    K -- "學習回饋/優化" --> D
​​```
