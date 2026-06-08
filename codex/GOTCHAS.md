# GOTCHAS

## Python PATH 不一定可用

- 狀態：active
- 證據：observed
- 日期：2026-06-02
- 影響範圍：本機產物產生流程
- 正確做法：優先使用 Codex 內建 Python：`C:\Users\user\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe`
- 不要做：不要假設 `python` 已加入 PATH。
- 驗證方式：執行版本或 import 檢查。
- 相關檔案：`codex/COMMANDS.md`

## localhost.run 免費網址不是永久部署

- 狀態：active
- 證據：observed
- 日期：2026-06-02
- 影響範圍：公開網站與 QR code
- 正確做法：短期分享可用 localhost.run；長期公開需部署到穩定平台後重產 QR code。
- 不要做：不要把 `*.lhr.life` 免費短效網址當成永久網址。
- 驗證方式：用 `curl.exe -I <公開網址>` 確認 HTTP 200。
- 相關檔案：`site/site_qrcode.png`

## in-app browser 截圖可能逾時

- 狀態：active
- 證據：observed
- 日期：2026-06-02
- 影響範圍：UI 視覺驗證
- 正確做法：優先嘗試截圖；若 `Page.captureScreenshot` 逾時，改用 DOM computed style、元素 bounding box、HTTP 200 與 console error 檢查補足驗證。
- 不要做：不要因截圖逾時就假設頁面壞掉。
- 驗證方式：in-app browser DOM 檢查與 `curl.exe -I http://127.0.0.1:5190/`。
- 相關檔案：`site/index.html`

## RAR 低模山羊素材

- 狀態：active
- 證據：observed
- 日期：2026-06-02
- 影響範圍：主視覺模型修改
- 正確做法：`C:\Program Files\NVIDIA Corporation\NVIDIA App\7z.exe` 可列出與解壓使用者提供的 RAR；目前把素材作為 low-poly 山羊外型參考，不直接引入 3D loader。
- 不要做：不要把 RAR 裡的 OBJ/FBX/DAE 直接塞進網頁造成新依賴，除非使用者明確要求真正匯入 3D 模型。
- 驗證方式：檢查 `codex/tmp/lowpolygoat-20260602/lowpolygoat/goat.obj` 與頁面 `.goat-facet` 元素。
- 相關檔案：`site/index.html`
