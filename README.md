# 規劃與運輸系統 <br>Planning and Transport System（PTS） <br>和倉儲管理系統<br>Warehouse Management System (WMS)<br>HTTPS 通訊規格書

## 0. 版本管理
|版本 | 更新| 編制者 |
|:------|:------|:------|
| v1.0.0　新建| 2025-10-07 |Athena |


## 1. 總覽

本規格書定義了規劃與運輸系統（PTS）與倉儲管理系統(WMS)之間的 HTTPS 通訊協定。倉儲管理系統(WMS)作為伺服器端，規劃與運輸系統(PTS)作為客戶端，透過WebAPI進行通訊，使用HTTPS協議傳輸JSON格式資料。
<br>
<br>

- **通訊協定**：HTTPS
- **傳輸格式**：JSON
- **系統架構**：
  - **WMS Server：** 倉儲管理系統伺服器，提供WebAPI服務。
  - **PTS Client：** 規劃與運輸系統端，主動呼叫WMS系統API。

  - **系統架構圖：**

<br>
<br>
