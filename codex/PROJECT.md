# PROJECT

## 專案用途

此資料夾目前用於保存使用者指定 Gemini 分享內容改作的獨立靜態網站與 QR code 產物。

## 本次網址

- GitHub 專案名稱：古鎖山羊2
- GitHub 儲存庫：`https://github.com/su2006sgm/gu-suo-shan-yang-2`
- GitHub Pages：`https://su2006sgm.github.io/gu-suo-shan-yang-2/site/`
- 來源網址：`https://gemini.google.com/share/216eb2bfab81`
- 靜態網站：`site/index.html`
- 網站 QR code：`site/site_qrcode.png`、`site/site_qrcode.svg`
- 目前公開暫時網址：`https://fifty-years-clean.loca.lt`
- 原始分享 QR code：`gemini_share_qrcode.png`、`gemini_share_qrcode.svg`

## 網站內容

- 主題：台灣山羊古鎖 × 南洋工藝。
- 內容來源：Gemini 分享頁中的互動 Canvas 內容。
- 核心元素：設計靈感、解鎖步驟、簧片鎖原理、山羊古鎖工藝特點、客製化工坊、解鎖成功訊息。
- 最新互動：主舞台使用 CSS 分層繪製簡潔側面台灣野山羊古鎖模型，參考使用者提供 RAR 中的 low poly goat 幾何風格，包含橫向深色鎖樑、低多邊形折面山羊頭、長鼻口、明顯雙角、尖耳、脖子、鬍鬚、四肢、中央金色鎖牌、水平鑰匙與黑色狀態欄；固定底部草地與左右行走的 Q 版台灣野山羊，點擊觸發合成叫聲。

## 技術方式

- 使用純 HTML/CSS/JS 建立可離線開啟的單頁網站。
- 主模型由 `site/index.html` 內的 CSS/HTML 元件組成，不以外部圖片作為主要模型。
- 使用者提供的低模山羊壓縮檔已解到 `codex/tmp/lowpolygoat-20260602/` 做參考；目前未把 OBJ/FBX/DAE 直接匯入網頁，避免新增大型 3D loader 依賴。
- 使用 Codex 內建 Python runtime 產生 QR code。
- 使用 Windows 內建 SSH 與 localhost.run 建立免費暫時公開 tunnel。
- 若 localhost.run 失效，改用 `npx --yes localtunnel --port 5190` 建立免費暫時公開網址。
- 不使用外部 QR code API。
- 不新增全域套件或專案依賴。
- 根目錄 `README.md` 提供跨電腦下載、啟動與推送說明。
