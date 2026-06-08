# log

## 2026-06-02

- 建立新版 `codex/` 最小骨架與 `.gitignore`。
- 任務：為 `https://gemini.google.com/share/216eb2bfab81` 產生 QR code PNG / SVG。
- 產出：`gemini_share_qrcode.png`、`gemini_share_qrcode.svg`。
- 驗證：檔案存在，PNG 為 888x888 RGB，已視覺檢查；未做獨立解碼驗證。
- 協作記憶壓縮：`codex_compressed/2026-06-02_015437.tar.gz`。
- 建立獨立網站：`site/index.html`。
- 產生網站 QR code：`site/site_qrcode.png`、`site/site_qrcode.svg`，原先指向 `http://10.100.0.2:5190/`。
- 啟動本機預覽服務並驗證：`http://127.0.0.1:5190/`，內容與解鎖互動 smoke test 通過。
- 使用 localhost.run 建立公開暫時網址：原為 `https://f2b0f070609bbf.lhr.life`，後因 tunnel 503 重建為 `https://c3cb43bfb01926.lhr.life`。
- 重產網站 QR code 指向公開 HTTPS 網址。
- 驗證公開網址 HTTP 200，內容包含 `台灣山羊古鎖`。
- 修改主視覺：改成台灣古鎖與台灣野山羊結合的 CSS 3D 互動模型。
- 新增固定底部草地與左右行走的 Q 版台灣野山羊；點擊會發出合成叫聲並短暫顯示泡泡。
- 驗證：本機 HTTP 200；in-app browser 檢查模型、底部固定、行走動畫與點擊狀態；公開新網址 HTTP 200；重產 QR code 指向 `https://c3cb43bfb01926.lhr.life`。
- 依使用者參考圖優化鎖模型：改為側面山羊剪影、深色橫向鎖樑、中央金色鎖牌、右側水平鑰匙、金色裂紋與光暈；修正窄視窗縮放，避免頭部與鑰匙被裁切。
- 驗證：in-app browser 截圖確認模型完整度；公開頁內容包含新模型樣式。
- 依使用者修正：「主模型要像寫實 3D 參考圖，下面才用 Q 版山羊」。
- 新增 `site/assets/serow-lock-hero.png`，主舞台改用 imagegen 生成的寫實 3D 台灣野山羊古鎖圖；原 CSS 模型隱藏為備援。
- 原公開 tunnel `https://c3cb43bfb01926.lhr.life` 回 503，改用新公開暫時網址 `https://6a1d917238755b.lhr.life`，並重產 `site/site_qrcode.png` 與 `site/site_qrcode.svg`。
- 驗證：本機首頁與圖片 HTTP 200；新公開網址與圖片 HTTP 200；in-app browser 截圖確認主舞台顯示寫實 3D 山羊古鎖，底部固定 Q 版山羊；點擊 `#walkingGoat` 後進入 `speaking` 與 `paused` 狀態。
- 協作記憶壓縮：`codex_compressed/2026-06-02_021144.tar.gz`。
- 使用者修正：主模型不是要直接換上參考圖或生成圖，而是要做成像參考圖的模型。
- 已將 `site/index.html` 主舞台改為內嵌 SVG/CSS 分層模型，移除主舞台 `<img>` 貼圖；模型含山羊、青銅鎖牌、U 形鎖樑、水平鑰匙與山林舞台。
- 驗證：DOM 顯示 `.serow-lock-svg`、`.svg-key`、`.svg-shackle`，且 `#heroModel img` 不存在；點擊完成解鎖後 SVG 鑰匙與鎖樑位移生效。
- localhost.run 多次回 503 或 empty reply，改用 localtunnel；公開網址 `https://fifty-years-clean.loca.lt` 回 HTTP 200，公開頁內容包含 `.serow-lock-svg`。
- 已重產 `site/site_qrcode.png` 與 `site/site_qrcode.svg` 指向 `https://fifty-years-clean.loca.lt`。
- 已移除先前生成圖資產 `site/assets/serow-lock-hero.png` 與空的 `site/assets/`，避免主模型被誤認為直接貼圖。
- 協作記憶壓縮：`codex_compressed/2026-06-02_120528.tar.gz`。
- 使用者提供新參考圖：「像這樣」，指向暗色框內的簡潔側面台灣山羊古鎖。
- 已調整 `site/index.html`：隱藏 `#heroModel` 山林 SVG，顯示 `#lockArea` CSS 古鎖模型；舞台改深色背景、黑色狀態欄、隱藏舞台內草地與舞台內叫聲按鈕，保留頁面底部 Q 版山羊。
- 驗證：本機 HTTP 200；公開 localtunnel HTTP 200；DOM computed style 顯示 `#lockArea` 為 `block`、`#heroModel` 為 `none`、狀態欄為黑底。
- 協作記憶壓縮：`codex_compressed/2026-06-02_121325.tar.gz`。
- 使用者要求把模型改得更像山羊。
- 已加強 CSS 山羊外型：新增雙耳、脖子、鬍鬚、背線，並調整頭部、鼻口、身體、四肢與尾部比例。
- 驗證：本機 HTTP 200；公開 localtunnel HTTP 200；in-app browser DOM 顯示 2 個 `.goat-ear`，且 `.goat-neck`、`.goat-beard`、`.goat-back` 存在。
- 協作記憶壓縮：`codex_compressed/2026-06-02_121949.tar.gz`。
- 使用者提供 `C:\Users\user\OneDrive - 大葉大學\桌面\nhqocuyjkk5c-lowpolygoat.rar`，要求模型像壓縮檔裡的 low poly goat。
- 已用 `C:\Program Files\NVIDIA Corporation\NVIDIA App\7z.exe` 解壓到 `codex/tmp/lowpolygoat-20260602/`；確認內含 `goat.obj`、`goat.dae`、`goat.fbx`、`goat.3ds`、`goat.c4d`，其中 OBJ 為 369 vertices、734 faces。
- 已更新 `site/index.html`：主山羊鎖改為低多邊形折面風格，新增 `.goat-facet` 與 `.goat-eye`，並強化長鼻口、雙角、尖耳、脖子、鬍鬚、身體折面與尾部輪廓。
- 驗證：本機 HTTP 200；in-app browser DOM 顯示 `.goat-facet` 5 個、`.goat-eye` 存在、`.goat-ear` 2 個、`#walkingGoat` 存在；瀏覽器 console error 為空。截圖 API 仍逾時，未取得新截圖。
- 協作記憶壓縮：`codex_compressed/2026-06-02_124734.tar.gz`。

## 2026-06-08

- 使用者要求將目前專案推送到 GitHub 帳號 `su2006sgm`。
- 已安裝 GitHub CLI `2.93.0`，並啟動 GitHub 裝置授權流程。
- 已初始化本機 Git 儲存庫，主分支為 `main`，本機提交者設定為 `su2006sgm <su2006sgm@users.noreply.github.com>`。
- 建議預設遠端儲存庫：公開 `su2006sgm/taiwan-goat-lock`。
- 推送範圍包含網站、QR code、`.gitignore` 與可交接的 `codex/` 文件；排除 `codex/tmp/`、`codex/artifacts/`、`codex_compressed/`。
- 已完成 GitHub CLI 裝置授權，確認登入帳號為 `su2006sgm`。
- 已建立公開儲存庫 `https://github.com/su2006sgm/taiwan-goat-lock`，設定 `origin` 並推送 `main`。
- 協作記憶壓縮：`codex_compressed/2026-06-08_193053.tar.gz`。
