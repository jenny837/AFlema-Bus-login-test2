# AFlema Bus-RW（UI）

`AFlema Bus` 車隊管理系統 / 中央監控平台（純前端 UI 範例）。本專案目前只有 `index.html`（Vue 3 + Tailwind CSS 皆由 CDN 載入），不含後端 API。

## 使用方式（如何開啟）

### 方式 A：直接用瀏覽器開啟（最簡單）

1. 在檔案總管找到專案資料夾。
2. 直接雙擊 `index.html`，或把 `index.html` 拖到瀏覽器（Chrome / Edge）開啟。

> 備註：以 `file://` 開啟時，頁面右上「連線狀態」會以瀏覽器的 `navigator.onLine` 判斷（此專案已有針對 `file://` 情境處理）。

### 方式 B：用本機 HTTP Server 開啟（較接近上線環境）

如果你希望用 `http://` 方式開啟（例如測試相對路徑、快取、連線狀態等），可在此資料夾啟動簡易靜態伺服器後再進入：

- **Python**

```bash
python -m http.server 8080
```

然後用瀏覽器開 `http://localhost:8080/index.html`

- **Node.js（http-server）**

```bash
npx http-server -p 8080
```

然後用瀏覽器開 `http://localhost:8080/index.html`

## 如何登入

### 登入規則（目前版本）

- **Account 帳戶**與**Password 密碼**：只要「兩者皆非空」即可登入（此為 UI Demo 行為，尚未串接真實驗證/後端）。
- 若任一欄位為空，會顯示錯誤狀態（輸入框抖動/紅框）。

### 記住帳戶（Remember account）

- 勾選「記住帳戶」後，系統只會把**帳戶（account）**存到瀏覽器的 localStorage。
- **不會保存密碼**。
- localStorage key：`af_remember_account`

### 登出

- 登入後，側邊欄底部使用者區塊可點「登出」回到登入頁。

## 介面功能概覽（UI）

- **日/夜模式**：右上角切換（登入前/後皆可切換）。
- **側邊欄**：可收合。
- **分頁（示範）**：總覽面版、監控中心、車隊管理、路線管理、告警管理、報表分析、系統設定。

## 資料與限制說明

- 此專案目前的儀表板數據、告警清單、報表列表等多為**示範資料**（前端假資料/占位）。
- 未含後端 API、權限角色、真實帳密驗證流程；如需串接，建議新增：
  - API base URL / token 儲存策略
  - 登入後取得使用者資訊與權限
  - 登入失敗/逾時處理與路由保護

