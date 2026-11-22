# Mia English Lab 網站

這是可直接放在 GitHub Pages 儲存庫根目錄的靜態網站。開啟 `index.html` 可查看內容；部署時一併保留 `styles.css` 和 `assets/`。沒有建置步驟或套件依賴。

## 上線前待確認

- 在 `index.html` 的 `#contact` 區塊補上 Mia 願意公開的 LINE、Email 或預約連結。
- 確認網站使用的學生照片、作品及過去任職機構畫面可公開展示。若需調整，替換 `assets/` 的對應圖片即可。
- 確認「新竹地區 1–5 人小班」是目前對外提供的課程安排。

網站只使用從專案照片挑選並壓縮的 WebP 圖片。兩張證照是另外製作的遮蔽版本；原始證照留在專案的 `證照/`，未複製進網站。原始照片與證照也未被修改。

`github_io.txt` 是本機帳號備註，不是網站內容；`.gitignore` 已排除它。若用 GitHub 網頁介面手動上傳檔案，也請略過這份備註。

## 雙擊發布

確認內容及照片可以公開後，在 Finder 雙擊 `上傳網站到GitHub.command`。它只會把本資料夾的網站檔案提交並推送到 `nekonano-q/profolio_mia`，不會上傳上層專案。沒有異動時會顯示「沒有新變更」。

第一次執行會在本資料夾建立 Git 儲存庫。GitHub 網頁與外掛的登入不等於 Terminal 的 Git 認證；若首次推送要求密碼，請在自己的 Terminal 輸入這個帳號的 [GitHub fine-grained personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)，授權範圍只選 `profolio_mia`，儲存庫權限選 **Contents: Read and write**。不要把 token 寫進檔案或傳給他人。之後若已存入 macOS 鑰匙圈，通常可直接雙擊更新。

首次推送成功後，到儲存庫的 **Settings → Pages**，選 **Deploy from a branch**、`main`、`/(root)` 並儲存。網站網址是 `https://nekonano-q.github.io/profolio_mia/`。

## 本機預覽

在本資料夾執行 `python3 -m http.server 8765`，再開啟 `http://127.0.0.1:8765/`。

## 更新 GitHub Pages

網站儲存庫為 `nekonano-q/profolio_mia`。在 GitHub 的 `Settings → Pages` 設定 `Deploy from a branch`、`main`、`/(root)`。這是 GitHub Pages 官方支援的發布方式。

之後在 Mac 上雙擊本資料夾的 `更新網站.command`，程式會提交並推送 `index.html`、`styles.css`、`assets/` 等網站檔案。首次使用前，這台 Mac 必須已有可推送到該儲存庫的 Git 驗證方式。程式不會儲存密碼或 token；若遠端有其他人新增的變更，會停止以避免覆蓋。
