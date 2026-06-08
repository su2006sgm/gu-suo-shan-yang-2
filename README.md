# 古鎖山羊2

台灣山羊古鎖互動式靜態網站。網站使用純 HTML、CSS 與 JavaScript 製作，不需要安裝專案套件。

## 重要連結

- GitHub 專案：<https://github.com/su2006sgm/gu-suo-shan-yang-2>
- 線上網站：<https://su2006sgm.github.io/gu-suo-shan-yang-2/site/>
- 網站入口檔：[`site/index.html`](site/index.html)

## 在其他電腦下載專案

### 方法一：使用 Git Clone

電腦需先安裝 [Git](https://git-scm.com/downloads)。

```powershell
git clone https://github.com/su2006sgm/gu-suo-shan-yang-2.git
cd gu-suo-shan-yang-2
```

之後要取得 GitHub 上的最新版本：

```powershell
git pull origin main
```

### 方法二：下載 ZIP

1. 開啟 <https://github.com/su2006sgm/gu-suo-shan-yang-2>。
2. 點擊 `Code`。
3. 點擊 `Download ZIP`。
4. 解壓縮後進入專案資料夾。

ZIP 適合只查看或備份；若要持續修改並推送，建議使用 Git Clone。

## 在其他電腦啟動本機網站

建議使用 Python 啟動本機伺服器，避免瀏覽器直接開啟 HTML 時產生相容性問題。

### Windows

在 PowerShell 進入網站資料夾：

```powershell
cd gu-suo-shan-yang-2\site
py -m http.server 5190
```

若電腦沒有 `py` 指令，可改用：

```powershell
python -m http.server 5190
```

啟動後開啟：

<http://127.0.0.1:5190/>

停止伺服器時，在 PowerShell 按 `Ctrl+C`。

### macOS / Linux

```bash
cd gu-suo-shan-yang-2/site
python3 -m http.server 5190
```

啟動後開啟：

<http://127.0.0.1:5190/>

## 修改後推送回 GitHub

先確認目前使用的是最新版本：

```powershell
git pull origin main
```

修改完成後執行：

```powershell
git status
git add .
git commit -m "描述這次修改內容"
git push origin main
```

如果 GitHub 要求登入，請使用有權限存取 `su2006sgm/gu-suo-shan-yang-2` 的 GitHub 帳號完成授權。

## GitHub Pages

GitHub Pages 會從 `main` 分支根目錄發布靜態檔案，網站位於 `site/` 資料夾，因此公開網址為：

<https://su2006sgm.github.io/gu-suo-shan-yang-2/site/>

推送新版本後，GitHub Pages 通常需要幾分鐘才會更新。

## 主要檔案

- `site/index.html`：互動網站主程式。
- `site/site_qrcode.png`：網站 QR code PNG。
- `site/site_qrcode.svg`：網站 QR code SVG。
- `codex/`：專案交接、狀態與驗證紀錄。

