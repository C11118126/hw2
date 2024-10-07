# 甘特圖示例

```mermaid
gantt
    title 項目甘特圖
    dateFormat  YYYY-MM-DD
    section 任務
    研擬計畫           :a1, 2024-10-01, 1d
    任務分配           :after a1  , 4d
    取得硬體           :after a1  , 17d
    程式開發           :after a2  , 70d
    安裝硬體           :after a3  , 10d
    程式測試           :after a4  , 30d
    撰寫使用手冊       :after a5  , 25d
    轉換檔案           :after a5  , 20d
    系統測試           :after a6  , 25d
    使用者訓練         :after a7  , 20d
    使用者測試         :after a9  , 25d
