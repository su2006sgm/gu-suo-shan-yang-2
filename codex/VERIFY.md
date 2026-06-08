# VERIFY

## QR code 驗證

- 確認 PNG 與 SVG 檔案存在。
- 網站 QR code 目前指向：
  `https://fifty-years-clean.loca.lt`
- 若無法本機解碼，至少用手機掃描做人工驗證。

## 2026-06-02 驗證結果

- `gemini_share_qrcode.png`：存在，888x888，RGB。
- `gemini_share_qrcode.svg`：存在。
- 已做視覺檢查：QR code 有完整 quiet zone，三個定位圖案清楚。
- 本機環境未提供獨立 QR 解碼套件，因此未做獨立解碼驗證。

## 2026-06-02 網站驗證結果

- `site/index.html`：存在。
- `site/site_qrcode.png`：存在，792x792。
- `site/site_qrcode.svg`：存在。
- 本機預覽：`http://127.0.0.1:5190/`
- 公開暫時網址：`https://fifty-years-clean.loca.lt`
- 瀏覽器 smoke test：標題、主要內容、客製化工坊、簧片鎖原理皆可見。
- 互動 smoke test：點擊「完成解鎖」後顯示「解鎖成功」對話框。
- 公開網址驗證：`curl.exe -I https://fifty-years-clean.loca.lt` 回傳 HTTP 200。
- 最新 UI 驗證：本機頁面包含 `.goat-body-3d` 與 `#walkingGoat`；底部草地為 `position: fixed`；Q 版山羊動畫名稱為 `goatWalk`。
- 最新互動驗證：點擊 `#walkingGoat` 後會進入 `speaking` 與 `paused` 狀態，泡泡顯示 `咩～` 或 `咩咩！`。
- 模型優化驗證：in-app browser 截圖確認頭部與鑰匙完整落在舞台內；公開頁內容包含新的水平鑰匙位置與金色鎖牌。
- 最新主模型驗證：`#lockArea` computed display 為 `block`，`#heroModel` computed display 為 `none`，狀態欄背景為 `rgba(0, 0, 0, 0.82)`；確認主視覺回到 CSS 側面山羊古鎖。
- 最新公開頁驗證：`curl.exe -I https://fifty-years-clean.loca.lt` 回傳 HTTP 200，公開頁 HTML 長度更新為 50954。
- 山羊強化驗證：in-app browser DOM 檢查顯示 `.goat-ear` 數量為 2，且 `.goat-neck`、`.goat-beard`、`.goat-back` 皆存在；公開頁內容也包含這些元素。
- 最新 Q 版山羊驗證：點擊 `#walkingGoat` 後 class 包含 `speaking` 與 `paused`，泡泡顯示 `咩咩！`。
- 最新截圖：`codex/artifacts/svg-serow-lock-stage-preview.png`。
- 低模山羊參考驗證：`nhqocuyjkk5c-lowpolygoat.rar` 內含 `goat.obj`、`goat.dae`、`goat.fbx`、`goat.3ds`、`goat.c4d`；已解到 `codex/tmp/lowpolygoat-20260602/`，`goat.obj` 有 369 vertices、734 faces。
- 低模 CSS 模型驗證：本機 HTTP 200；in-app browser DOM 顯示 `.goat-facet` 數量為 5、`.goat-eye` 存在、`.goat-ear` 數量為 2、`#walkingGoat` 存在；瀏覽器 console error 為空。
- 截圖限制：本次 in-app browser `Page.captureScreenshot` 仍逾時，未取得新截圖；以 DOM、HTTP 與 console error 驗證替代。

## 協作檔驗證

- `codex/` 根目錄需包含新版入口與狀態文件。
- `codex_compressed/` 僅保留一個 `.tar.gz` 壓縮檔。
