# 隨機話題產生器

213 道聊天話題，依關係深度分七層（L1 初識 → L7 性），點一下隨機抽一題。
每題附「接著問」的追問提示。可標記「好用」（抽中機率 ×3）或「不要這題」（永久隱藏）。

## 部署到 GitHub Pages

1. 新建 repo（例如 `topics`），把這個資料夾裡的檔案全部放進根目錄。
2. Settings → Pages → Source 選 `Deploy from a branch`，分支 `main`、資料夾 `/ (root)`。
3. 等一兩分鐘，網址是 `https://<你的帳號>.github.io/<repo 名>/`。
4. 手機 Safari 開該網址 → 分享 → 加入主畫面。

## 離線

`sw.js` 是 Service Worker，第一次連線時把所有檔案存進瀏覽器快取，之後飛航模式也打得開。
Service Worker 只在 HTTPS 下生效（GitHub Pages 是 HTTPS，本機用 `file://` 開則不會註冊，屬正常）。

**改版之後**：請同時把 `sw.js` 裡的 `CACHE = "topics-vX.X"` 換成新版本號，否則手機會一直吃舊快取。
版本號本身在 `index.html` 的 `const VERSION` 和 `CHANGELOG` 陣列裡。

## 資料

「好用」「隱藏」和使用統計存在瀏覽器的 localStorage，只在該裝置。
點標題旁的版本號可以看統計與更新紀錄。

## 依賴

無。單一 HTML，不載入任何外部資源。
