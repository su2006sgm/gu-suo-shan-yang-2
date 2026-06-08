# ARCHITECTURE

## 結構

- 根目錄：放置原始分享 QR code 產物。
- `site/`：獨立靜態網站與網站 QR code。
- `codex/`：保存協作記憶、驗證方式與交接狀態。
- `codex_compressed/`：保存本次協作記憶壓縮備份，預設不提交。

## 資料流

1. 使用者提供 Gemini 分享網址。
2. 透過可登入狀態的瀏覽器讀取 Gemini 內嵌 Canvas 可見內容。
3. 將內容整理為單頁靜態網站 `site/index.html`。
4. 將主模型以 `site/index.html` 內的 CSS/HTML 分層繪製，不直接貼上參考圖或生成圖。
5. 啟動本機 HTTP 預覽服務驗證互動。
6. 將公開暫時網址編碼為 `site/site_qrcode.png` 與 `site/site_qrcode.svg`。
