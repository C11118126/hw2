# PERT/CPM圖示例
```mermaid
graph TD;
    A[研擬計畫] -->|1天| B[任務分配];
    A -->|17天| C[取得硬體];
    B -->|70天| D[程式開發];
    C -->|10天| E[安裝硬體];
    D -->|30天| F[程式測試];
    E -->|25天| G[撰寫使用手冊];
    E -->|20天| H[轉換檔案];
    F -->|25天| I[系統測試];
    G -->|20天| J[使用者訓練];
    H -->|20天| J;
    I -->|25天| K[使用者測試];
    J -->|25天| K;
