# DECISIONS

## ADR-0001：採用新版 codex/ 分層結構

- 狀態：accepted
- 日期：2026-06-02
- 背景：本目錄原先沒有專案記憶，本次會新增 QR code 產物，依全域 AGENTS 規則需要建立協作骨架。
- 選項：不建立記憶、建立舊版格式、建立新版分層結構。
- 決策：建立新版 `codex/` 分層結構。
- 原因：符合目前全域協作規則，且方便後續代理接手。
- 後果：完成前需同步壓縮 `codex/` 到 `codex_compressed/`。
- 取代：無。
- 相關檔案：`codex/00_START_HERE.md`

## ADR-0002：QR code 使用本機產生

- 狀態：accepted
- 日期：2026-06-02
- 背景：使用者要求為 Gemini 分享網址產生 QR code。
- 選項：外部 QR code API、本機套件、本機最小 QR 編碼流程。
- 決策：使用本機最小 QR 編碼流程產生 PNG 與 SVG。
- 原因：避免把網址送到第三方 QR code 服務，也不需要新增全域依賴。
- 後果：產物需以本機解碼或掃描方式驗證。
- 取代：無。
- 相關檔案：根目錄 QR code 產物。

## ADR-0003：獨立網站採用單檔靜態 HTML

- 狀態：accepted
- 日期：2026-06-02
- 背景：使用者要求把 Gemini 分享內容做成獨立網站與 QR code。
- 選項：複製動態 Gemini 頁、建立 React/Vite 專案、建立單檔 HTML/CSS/JS。
- 決策：建立 `site/index.html` 單檔靜態網站。
- 原因：可離線開啟、不需新增依賴、不需付費服務，且足以保留內容與互動。
- 後果：QR code 若要公開使用，需另行部署到公開網址後重產。
- 取代：無。
- 相關檔案：`site/index.html`、`site/site_qrcode.png`

## ADR-0004：暫時公開採用 localhost.run SSH tunnel

- 狀態：accepted
- 日期：2026-06-02
- 背景：使用者表示手機打不開區網 QR code，要求公開出去。
- 選項：localhost.run SSH tunnel、GitHub Pages、Cloudflare Pages、Netlify、自架主機。
- 決策：先用 localhost.run 建立免費短效公開 HTTPS tunnel。
- 原因：免註冊、免下載、可立即讓手機用公開網址開啟。
- 後果：網址非永久；電腦、Python HTTP server 或 SSH tunnel 停止時會失效。
- 取代：先前指向 `http://10.100.0.2:5190/` 的 QR code。
- 相關檔案：`site/site_qrcode.png`、`site/site_qrcode.svg`

## ADR-0005：台灣古鎖模型採用 CSS 3D

- 狀態：accepted
- 日期：2026-06-02
- 背景：使用者要求將鎖改成台灣古鎖與台灣野山羊結合的 3D 互動模型，並讓 Q 版山羊固定在底部行走與發出叫聲。
- 選項：引入 Three.js、使用 CSS 3D 與 Web Audio、使用圖片或影片。
- 決策：使用 CSS 3D 與 Web Audio，不新增外部依賴。
- 原因：目前網站是單檔靜態頁，需維持離線與公開 tunnel 都可穩定運作；CSS 3D 足以呈現本次需求的可互動立體感，Web Audio 可避免音檔依賴。
- 後果：不是可匯入的真 3D 模型檔；若未來需要 glTF / OrbitControls / 光照材質，可再改為 Three.js。
- 取代：原本較平面的古鎖示意。
- 相關檔案：`site/index.html`

## ADR-0006：主模型改採寫實 3D 靜態資產

- 狀態：superseded
- 日期：2026-06-02
- 背景：使用者補充主模型要像參考圖的寫實 3D 台灣野山羊古鎖，底部行走角色才要是 Q 版山羊。
- 選項：繼續修 CSS 拼接模型、引入 Three.js 與模型檔、使用 imagegen 產生寫實主視覺圖並保留頁面互動。
- 決策：使用 imagegen 產生寫實 3D 主視覺圖，保存為 `site/assets/serow-lock-hero.png`；原 CSS 模型隱藏為備援，頁面互動改作用於圖片視差、亮度與光暈。
- 原因：能最快貼近使用者參考圖，又不新增大型依賴或遠端資源。
- 後果：主模型不是可旋轉的 glTF 真 3D 模型；目前互動是圖片視差與狀態效果。
- 取代：ADR-0005 中 CSS 3D 作為主模型外觀的做法。
- 相關檔案：`site/index.html`、`site/assets/serow-lock-hero.png`

## ADR-0007：主模型改為 SVG/CSS 分層繪製

- 狀態：superseded
- 日期：2026-06-02
- 背景：使用者明確指出不是要直接換上參考圖或生成圖，而是要做成像參考圖的台灣野山羊古鎖模型。
- 選項：保留生成圖、引入 Three.js、使用內嵌 SVG/CSS 分層繪製。
- 決策：使用 `site/index.html` 內嵌 SVG/CSS 分層繪製主模型，包含山羊、青銅鎖牌、U 形鎖樑、水平鑰匙、雕刻線與山林舞台。
- 原因：符合「不是直接貼圖」要求，同時維持單頁靜態網站、無大型依賴、可公開 tunnel 與離線開啟。
- 後果：目前是 2.5D SVG/CSS 互動模型，不是可匯入 glTF 的真 3D 模型檔。
- 取代：ADR-0006。
- 相關檔案：`site/index.html`

## ADR-0008：主模型改回 CSS 側面古鎖

- 狀態：accepted
- 日期：2026-06-02
- 背景：使用者提供新截圖，要求主舞台更像暗色框內的簡潔側面山羊古鎖，而不是山林 SVG 舞台。
- 選項：延續 SVG 山林模型、直接貼圖、使用既有 CSS/HTML 元件重塑側面古鎖。
- 決策：隱藏 `#heroModel` SVG，顯示 `#lockArea` CSS 側面山羊古鎖模型，並調整舞台背景、狀態欄、比例與置中。
- 原因：最貼近使用者新參考圖，仍維持不是直接貼圖、無外部依賴。
- 後果：主模型是 CSS/HTML 2.5D 視覺，不是 glTF 真 3D 模型。
- 取代：ADR-0007 的山林 SVG 主舞台外觀。
- 相關檔案：`site/index.html`
