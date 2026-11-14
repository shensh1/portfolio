# 2. Monthly sales and order dashboard

*[中文](#中文)*

## Problem
Monthly sales figures were circulated as an e-mail in a fixed layout. Readers wanted the same numbers on demand, together with order intake and the open order book, and the ability to drill into a sales unit or a customer.

## What I built
A Power BI report on the corporate cloud data warehouse:

| Page | Content |
|---|---|
| Overview | KPI cards for last month's net sales, order intake, book-to-bill and open order book; a 13-month sales versus intake trend; breakdowns by sales unit; top customers |
| Sales details | Sales unit and sales engineer matrix; monthly sales and intake matrices |
| Order book | Open order book by accepted delivery month and sales unit |
| Month and year-to-date | This year against last year, reproducing the layout of the former monthly e-mail so readers could switch without relearning |
| Guide | How to read and export the report, with an embedded demonstration and a narrated tutorial video with subtitles |

The semantic model is a star schema: three fact tables (invoices, order intake, order book), shared dimensions (customer, product, date), a sales-unit mapping table and a last-refresh table, with about twenty DAX measures.

## Design points
- **Stored as a Power BI project (PBIP)** with the report in PBIR and the model in TMDL, so every change is a readable text difference in Git instead of an opaque binary.
- **Data stays out of the repository.** The imported-data cache and the binary report file are excluded; credentials are never stored.
- **Experimental pages live on a branch**, not in a copied folder with a date in its name. The fourth page is being developed that way.
- **The report explains itself.** A guide page inside the report shows how to read and export it.

## Result
- The monthly e-mail's content is available on demand, with drill-down by sales unit, sales engineer and customer.
- More than thirty commits record how the report evolved, each with a message saying what changed.

## Technologies
Power BI Desktop and Service, PBIP / PBIR / TMDL, DAX, Snowflake, Git.

---

<a id="中文"></a>

# 2. 月度銷售與訂單戰情報表

## 問題
每月銷售數字原本以固定版面的郵件發送。讀者希望隨時看到同樣的數字，連同接單與未交訂單，並能下鑽到某個銷售單位或客戶。

## 我做了什麼
建立在公司雲端資料倉儲上的 Power BI 報表：

| 頁面 | 內容 |
|---|---|
| 總覽 | 上月淨銷售、接單、接單出貨比、未交訂單的 KPI 卡；13 個月銷售與接單趨勢；依銷售單位的分析；主要客戶 |
| 銷售明細 | 銷售單位與業務工程師矩陣；月度銷售與接單矩陣 |
| 未交訂單 | 依確認交期月份與銷售單位的未交訂單 |
| 當月與年累計 | 今年對去年，版面沿用原本月報郵件的格式，讓讀者不必重新適應 |
| 使用指南 | 如何閱讀與匯出報表，內嵌操作示範，並附有配音與字幕的教學影片 |

語意模型採星狀結構：三張事實表（發票、接單、未交訂單）、共用維度（客戶、產品、日期）、銷售單位對照表與最後更新時間表，約二十個 DAX 量值。

## 設計重點
- **以 Power BI 專案檔 (PBIP) 儲存**，報表為 PBIR、模型為 TMDL，每次修改在 Git 中都是看得懂的文字差異，而不是無法比對的二進位檔。
- **資料不進儲存庫。** 匯入資料的快取與二進位報表檔都被排除；不儲存任何帳密。
- **實驗中的頁面放在分支**，不再複製資料夾並在名稱加日期。第四頁就是這樣開發的。
- **報表自己會說明。** 報表內的使用指南頁說明如何閱讀與匯出。

## 成果
- 月報郵件的內容可隨時查看，並可依銷售單位、業務工程師與客戶下鑽。
- 三十多筆提交紀錄記下報表的演進，每筆都說明改了什麼。

## 技術
Power BI Desktop 與服務、PBIP／PBIR／TMDL、DAX、Snowflake、Git。
