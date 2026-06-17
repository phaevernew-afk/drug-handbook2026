# 本院藥品手冊 115 年版 — 院內查詢網站

## 網站功能
- 全文關鍵字搜尋（藥名、學名、原廠名、適應症、副作用等）
- 依大分類 / 次分類 / 劑型篩選
- 點擊藥品卡片展開完整資訊
- RWD 響應式設計，手機、電腦均可使用
- 純靜態網頁，不需後端，直接掛 GitHub Pages

---

## 檔案結構

```
drug-website/
├── index.html      ← 網站主頁（查詢介面）
├── drugs.json      ← 藥品資料（由 Excel 轉換產生）
└── README.md       ← 本說明文件
```

---

## 佈署到 GitHub Pages（第一次）

1. 至 [github.com](https://github.com) 建立新的 Repository（例如命名 `drug-handbook`）
2. 將本資料夾內所有檔案上傳至 Repository 根目錄
3. 進入 Repository → **Settings** → **Pages**
4. Source 選擇 **Deploy from a branch** → Branch 選 `main`，資料夾選 `/ (root)`
5. 按 Save，約 1–2 分鐘後網址即可連線

> 網址格式：`https://你的帳號.github.io/drug-handbook/`

---

## 更新藥品資料（日後維護）

每次更新藥品內容時，只需兩個步驟：

### 步驟一：更新 Excel

使用原有的 `藥品手冊115_資料庫.xlsx` 進行新增、修改或刪除藥品，儲存後上傳給 Claude，執行以下指令重新產生 `drugs.json`：

```
請幫我把更新後的 Excel 重新轉成 drugs.json
```

### 步驟二：上傳新的 drugs.json

將新的 `drugs.json` 覆蓋上傳至 GitHub Repository 中，GitHub Pages 自動更新（約 30 秒–1 分鐘生效）。

**不需要動 `index.html`，除非要修改介面。**

---

## 可查詢欄位

| 欄位 | 說明 |
|------|------|
| 藥品名稱 | 粗體標題（商品名或學名） |
| 原廠名 | 原廠商品名 |
| 學名名稱 | 國際學名（INN） |
| 劑量劑型 | 口服 / 注射劑 / 外用等 |
| 藥理 | 作用機轉說明 |
| 適應症 | 核准適應症 |
| 用法用量 | 成人 / 兒童建議劑量 |
| 注意事項 | 禁忌 / 注意事項 |
| 副作用 | 常見及重大副作用 |
| 孕婦分級 | FDA 孕婦用藥分級 |
| 備註欄 | 院內特殊規定、抗生素階梯等 |

---

## 技術說明

- 純 HTML + CSS + JavaScript，無框架依賴
- 資料以 JSON 格式嵌入，首次載入後全數在前端搜尋（無後端 API）
- 全文搜尋使用即時 filter，關鍵字命中處會螢光標記
- 支援行動裝置（RWD）

---

*如有問題請洽藥劑科或資訊室*
