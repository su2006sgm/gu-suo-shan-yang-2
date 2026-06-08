# COMMANDS

## Runtime

- Codex 內建 Python：
  `C:\Users\user\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe`

## 驗證指令

```powershell
Get-ChildItem -LiteralPath . -Filter '*qrcode*'
Get-ChildItem -LiteralPath .\site
```

## 啟動本機網站預覽

```powershell
& "C:\Users\user\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe" -m http.server 5190 --bind 0.0.0.0
```

執行目錄：`C:\Users\user\Desktop\519 - 複製\site`

本機網址：`http://127.0.0.1:5190/`

## 啟動公開暫時網址

```powershell
ssh.exe -o StrictHostKeyChecking=accept-new -o ServerAliveInterval=60 -R 80:127.0.0.1:5190 nokey@localhost.run
```

目前公開網址：`https://fifty-years-clean.loca.lt`

注意：免費網址會變動，重開 tunnel 後要用新網址重產 `site/site_qrcode.png` 與 `site/site_qrcode.svg`。

## localhost.run 不穩時改用 localtunnel

```powershell
npx --yes localtunnel --port 5190
```

目前 localtunnel 公開網址：`https://fifty-years-clean.loca.lt`

## 壓縮協作記憶

```powershell
tar -czf codex_compressed/YYYY-MM-DD_HHMMSS.tar.gz codex
```
