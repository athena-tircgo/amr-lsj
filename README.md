# 八德場區場內運行規劃書

## 0. 版本管理
|版本 | 更新| 編制者 |
|:------|:------|:------|
| v1.0.0　新建| 2025-10-07 |Athena |


## 1. 總覽

本規格書定義AMR接受WMS派遣任務派送到達指定位置，人員在每一個停靠站將藥品放入，完成操作後於AMR 上按下按鈕往下一站，等訂單內物料都齊後，WMS 會派AMR 到包裝區等整個場區的運行規劃。

<br>

- **WMS Server**：倉儲管理系統伺服器。
- **PTS Client**：規劃與運輸系統端。

  - **系統架構圖：**

```mermaid
flowchart TD
    %% 節點設定
    style WMS fill:#f5f5dc,stroke:#333,stroke-width:2px,rx:7,ry:7
    style PTS fill:#7fbf7f,stroke:#333,stroke-width:2px,rx:7,ry:7
    style AMR1 fill:#a3d4f5,stroke:#333,stroke-width:2px,rx:7,ry:7
    style AMR2 fill:#a3d4f5,stroke:#333,stroke-width:2px,rx:7,ry:7
    style AMR3 fill:#a3d4f5,stroke:#333,stroke-width:2px,rx:7,ry:7
    style AMR4 fill:#a3d4f5,stroke:#333,stroke-width:2px,rx:7,ry:7

    %% 節點文字
    WMS["WMS 系統"]
    PTS["PTS 系統"]
    AMR1["AMR_1"]
    AMR2["AMR_2"]
    AMR3["AMR_3"]
    AMR4["AMR_4"]

    %% 連線
    WMS <-->PTS
    PTS -->AMR1
    PTS -->AMR2
    PTS -->AMR3
    PTS -->AMR4
```


## 2. 操作規格

### 2.1 場域配置圖

本場域共設置有12個工作站點以及一個充電站點，如下示意圖所示。<br>
1、5、9 為包裝區站點，同時也是AMR 的待命區，其餘點位為撿貨區站點。0 為充電站 。

<br>

```mermaid
graph LR
    %% 樣式設定
    classDef node fill:#fff,stroke:#555,stroke-width:1px,rx:5,ry:5;

    %% 第一欄
    subgraph col1[ ]
        A1[1]:::node
        A2[5]:::node
        A3[9]:::node
    end

    %% 第二欄
    subgraph col2[ ]
        A4[2]:::node
        A5[6]:::node
        A6[10]:::node
    end

    %% 第三欄
    subgraph col3[ ]
        A7[3]:::node
        A8[7]:::node
        A9[11]:::node
    end

    %% 第四欄
    subgraph col4[ ]
        A10[4]:::node
        A11[8]:::node
        A12[12]:::node
        A13[0]:::node
    end

    %% 橫向連線
    A1 --- A4 --- A7 --- A10
    A2 --- A5 --- A8 --- A11
    A3 --- A6 --- A9 --- A12

```

### 2.2 運行規劃

(1) 共有4台AMR 正常模式下，3台AMR 在工作區，1台AMR 在充電區待命。<br>
(2) 在充電站的AMR 狀態顯示為：unavailable，無法接受派遣任務。<br>
(3) 每天要派遣任務時，須確認AMR1、AMR2、AMR3 是否分別在待命區1、5、9，且AMR狀態是待命中，方可開始派遣任務。<br>
    如果AMR 不在待命區，請人員手動移動到待命區。<br>
(3) 





