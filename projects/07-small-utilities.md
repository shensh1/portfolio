# 7. Small utilities

*[中文](#中文)*

Three small tools that solved recurring chores.

## Folder inventory to Excel
**Purpose.** Produce a complete, sortable list of everything in a folder tree.

**What it does.** Walks a folder tree and writes one row per folder and file: type, name indented by depth, extension, full path, parent folder, size, created and modified times. The output is a formatted Excel workbook that can be filtered and sorted.

**Technologies.** Python, pathlib, openpyxl, managed with uv.

## Automatic consolidation of Excel files
**Purpose.** Keep one combined list up to date when the source data is spread across Excel files in sub-folders.

**What it does.** Watches a folder and its sub-folders. When an Excel file is added or changed, it merges all of them into one workbook, with handling for duplicate column names and for rows that lack a valid project number. It is started by double-clicking a batch file, so colleagues without Python experience can run it.

**Technologies.** Python, pandas, openpyxl.

## Database access through a standard tool protocol
**Purpose.** Let query and analysis tools reach a personal PostgreSQL database in a controlled way.

**What it does.** Connects to a PostgreSQL instance running in a container on a single-board computer, and runs a Model Context Protocol (MCP) server inside the project's own virtual environment. A small script tests the connection. The connection string is held in a local environment file that is excluded from version control.

**Technologies.** Python 3.12, uv, PostgreSQL, Docker, MCP.

---

<a id="中文"></a>

# 7. 小工具

三個解決重複性雜務的小工具。

## 資料夾清冊輸出 Excel
**目的。** 產生資料夾樹中所有內容的完整、可排序清單。

**功能。** 走訪整個資料夾樹，每個資料夾與檔案寫成一列：類型、依層級縮排的名稱、副檔名、完整路徑、上層資料夾、大小、建立與修改時間。輸出為可篩選、可排序的格式化 Excel 活頁簿。

**技術。** Python、pathlib、openpyxl，以 uv 管理環境。

## Excel 檔自動合併
**目的。** 來源資料分散在子資料夾的多個 Excel 檔時，讓合併清單保持最新。

**功能。** 監看一個資料夾及其子資料夾。有 Excel 檔新增或修改時，把全部合併成一個活頁簿，並處理重複的欄名與缺少有效專案編號的列。雙擊批次檔即可啟動，沒有 Python 經驗的同事也能執行。

**技術。** Python、pandas、openpyxl。

## 以標準工具協定存取資料庫
**目的。** 讓查詢與分析工具以受控的方式連到個人的 PostgreSQL 資料庫。

**功能。** 連線到單板電腦上以容器執行的 PostgreSQL，並在專案自己的虛擬環境內執行 Model Context Protocol（MCP）伺服器。附一支測試連線的小程式。連線字串放在本機的環境檔，不進版本控管。

**技術。** Python 3.12、uv、PostgreSQL、Docker、MCP。
