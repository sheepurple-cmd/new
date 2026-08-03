# GitHub Copilot Instructions - 行銷網頁製作專案

## 1. 基本語言與溝通規範
* **語言設定**：所有回應、註解、說明文字及提交訊息，一律請使用**繁體中文（zh-TW）**。

## 2. 記憶與任務紀錄 (Memories)
* 本專案包含 `memories/` 資料夾，用於紀錄每日開發任務與進度。
* **每日任務自動存檔**：當執行完一項任務或一日開發結束時，請自動在 `memories/YYYY-MM-DD.md`（例如：`memories/2026-08-03.md`）建立或更新任務記憶紀錄。
* **紀錄內容包含**：當日完成事項、遇到的重大調整或未完成的待辦項目。

## 3. Git 版本控制與 Commit 規範
* **自動提交與推送**：每次專案中有任何檔案變更時，請呼叫本檔案中的 Git 規範，並在任務階段性完成後提醒並執行 `git add .`、`git commit` 與 `git push`。
* **Commit 格式**：Commit 標題必須符合「`[任務名稱] YYYY-MM-DD HH:mm`」格式。
  * 範例：`[完成首頁 Hero 區塊 RWD 切頁] 2026-08-03 15:30`

---

## 4. 行銷網頁開發規範與建議 (Marketing Landing Page Guidelines)

### A. 響應式與視覺設計 (RWD & UI/UX)
* **Mobile-First 優先**：行銷網頁大部分流量來自行動裝置，寫樣式時務必確保手機端體驗良好。
* **行動導向 (Call-to-Action, CTA)**：確保購買、訂閱、報名等 CTA 按鈕在手機與電腦版皆顯眼且容易點擊（建議觸控區域不小於 44x44px）。
* **跨瀏覽器相容性**：寫 CSS 時需考慮主流瀏覽器（Chrome, Safari, Edge, Firefox）的相容性。

### B. 搜尋引擎最佳化與社群分享 (SEO & Open Graph)
* **語意化 HTML**：請善用 `<header>`, `<main>`, `<section>`, `<article>`, `<footer>` 等語意標籤，並確保每頁只有一個 `<h1>`。
* **Meta 標籤與 OG 設定**：建立新頁面時，務必包含必要的 `<meta name="description">` 以及 Facebook/LINE 分享所需的 Open Graph (`og:title`, `og:image`, `og:description`) 標籤。
* **圖片 Alt 屬性**：所有裝飾性以外的圖片都必須填寫明確的 `alt` 說明，以利 SEO 與無障礙體驗。

### C. 網頁載入效能 (Performance Optimization)
* **圖片優化**：建議優先使用 WebP/AVIF 等高壓縮格式，並對非首屏 (Below the fold) 的圖片加上 `loading="lazy"`。
* **動畫效能**：網頁動畫應盡量使用 CSS `transform` 與 `opacity` 觸發 GPU 加速，避免引發網頁重繪 (Reflow/Repaint)。

### D. 文案與行銷追蹤 (Analytics & Marketing Tracking)
* **埋點支援**：切頁時請預留埋點機制（例如按鈕標註 `data-ga-category` 或 HTML ID/Class），方便後續串接 Google Analytics (GA4) 或 Meta Pixel 追蹤事件。
* **文案彈性**：盡量將行銷文案、標題、優惠訊息獨立抽離（或使用變數/JSON 檔集中管理），方便後續無痛修改文案。