# 實習紀錄助手 PWA 部署說明

這個資料夾就是可以直接上架的完整內容：

| 檔案 | 用途 |
|---|---|
| `index.html` | 主程式（與上層的 `實習紀錄助手.html` 內容相同） |
| `manifest.webmanifest` | PWA 設定：App 名稱、圖示、獨立視窗 |
| `sw.js` | service worker：離線也能開，連線時自動抓最新版 |
| `icon-512.png` / `icon-192.png` | App 圖示 |
| `apple-touch-icon.png` | iOS 主畫面圖示 |

## 上架到 GitHub Pages（一次性，約 10 分鐘）

1. 到 github.com 登入，右上角「+」→ New repository，名稱例如 `intern-log`，選 Public，按 Create
2. 在 repo 頁面點「uploading an existing file」，把這個資料夾裡的 **6 個檔案全部**拖進去，按 Commit changes
3. repo 的 Settings → Pages → Source 選「Deploy from a branch」、Branch 選 `main`、資料夾選 `/ (root)`，按 Save
4. 等 1～2 分鐘，網址會是 `https://你的帳號.github.io/intern-log/`

## iPhone 安裝

1. 用 Safari 開上面的網址
2. 點下方「分享」按鈕 → 「加入主畫面」
3. 主畫面會出現「實習紀錄」圖示，點開就是全螢幕 App

Mac 上用瀏覽器開同一個網址即可（Chrome 網址列右側也會出現安裝按鈕）。

## 之後怎麼更新

1. 改上層的 `實習紀錄助手.html`，複製一份到這裡改名 `index.html`
2. 把 `sw.js` 裡的 `intern-log-v1` 版本號 +1（例如 `v2`）
3. 兩個檔案重新上傳到 GitHub repo 蓋掉舊的，所有裝置下次開啟自動更新

## 注意事項

- 每台裝置的資料各自獨立存在本機，不會因為同網址就互通；跨裝置搬資料用 App 裡的「備份與同步」
- repo 是公開的：程式碼誰都看得到，但**資料不在裡面**（資料只存在各裝置的瀏覽器）
- 換了 GitHub Pages 網址（改 repo 名）等於換一個 App，本機資料不會跟過去，搬家前先匯出備份
