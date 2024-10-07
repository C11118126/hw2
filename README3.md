# 關鍵路徑圖示例

```mermaid
graph TD;
    A[研擬計畫\n1天] --> B[任務分配\n4天];
    A --> C[取得硬體\n17天];
    B --> D[程式開發\n70天];
    C --> E[安裝硬體\n10天];
    D --> F[程式測試\n30天];
    E --> G[撰寫使用手冊\n25天];
    E --> H[轉換檔案\n20天];
    F --> I[系統測試\n25天];
    G --> J[使用者訓練\n20天];
    H --> J;
    I --> K[使用者測試\n25天];
    J --> K;

    %% 關鍵路徑
    classDef critical fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    class A,B,D,F,I,K critical;
