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


```mermaid
graph LR
    %% 第一排
    A1[1] --- A2[2] --- A3[3] --- A4[4]
    %% 第二排
    A5[5] --- A6[6] --- A7[7] --- A8[8]
    %% 第三排
    A9[9] --- A10[10] --- A11[11] --- A12[12]

    %% 垂直連線（每欄對應）
    A1 --- A5 --- A9
    A2 --- A6 --- A10
    A3 --- A7 --- A11
    A4 --- A8 --- A12
```


2.1 本場域共設置有12個工作站點以及一個充電站點。
2.2 共有4台AMR 會在本廠域內運行，正常模式下，3台AMR 在工作區，1台AMR 在充電區待命。
2.3 




