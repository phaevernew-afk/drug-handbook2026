# 院內用藥查詢網站

純前端靜態網站，可直接部署於 GitHub Pages。

## 檔案說明
- `index.html` — 同仁查詢頁，支援關鍵字搜尋（藥品名/學名/商品名/中文名/適應症/索引碼）與欄位篩選
- `admin.html` — 後台管理頁，可上傳 Excel（.xls/.xlsx）轉換成 `drugs.json`，或直接編輯既有資料、新增/刪除藥品，最後下載新的 `drugs.json`
- `drugs.json` — 藥品資料本體（602 筆，由原始 藥品.xls 轉換而來）

## 部署到 GitHub Pages
1. 建立一個新的 GitHub repository（例如 `drug-lookup`）
2. 將這三個檔案（`index.html`、`admin.html`、`drugs.json`）上傳到 repo 根目錄
3. 到 repo 的 Settings → Pages，Source 選擇 `main` branch / `root`，儲存
4. 等待約 1 分鐘，網站會出現在 `https://你的帳號.github.io/drug-lookup/`

## 日常維護方式（不需重新上傳整個網站）
往後若要新增、修改、刪除藥品資料，**只需要更新 `drugs.json` 這一個檔案**：

1. 開啟 `admin.html`（可直接在 GitHub Pages 上開啟後台頁，例如 `https://你的帳號.github.io/drug-lookup/admin.html`）
2. 點「載入目前 drugs.json」讀入現有資料，或上傳新的 Excel 檔
3. 在表格中直接點儲存格編輯、用「＋ 新增藥品」新增列、用每列右側的 ✕ 刪除
4. 按「下載 drugs.json」，瀏覽器會下載一個新的 `drugs.json`
5. 回到 GitHub repo，把這個新檔案上傳並覆蓋原本的 `drugs.json`（commit），網站會自動更新

整個流程完全不需要写程式碼，也不需要伺服器後端。
