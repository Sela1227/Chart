# CLAUDE.md — 病歷整理器 (Chart)

> **這份是給下次 Claude 看的工作上下文，不是文件。**
> 判斷標準只有一個：下次 Claude 讀完，能不能直接動手？

> **⚠ 給同時拿到 SELA-Starter-Kit 的 Claude：**
> 這是**已對齊 Kit V1.8.2 的成熟專案**，不是新專案。
>
> 衝突仲裁規則：
> 1. **以本專案 CLAUDE.md 為主、Kit 為輔**
> 2. 本專案刻意不對齊 Kit 的部分：
>    - 配色用 #F97316（非 Kit 預設 #5A7A8B），因多月臨床使用驗證
>    - README 結構保留原有格式，不依章法手冊重排
> 3. **不要為對齊 Kit 而動既有設計** — 已驗證的就是事實標準
> 4. 版號規則照 Kit（三位數）
> 5. **下次完成版本時記得評估 SELA-handoff.md**（鐵律 #0）

---

## 〇、當前狀態

- **版本：** V7.0.1
- **狀態：** 上線中（臨床使用）
- **一句話定位：** 放射腫瘤科病歷結構化整理工具，支援 AI 摘要、多格式匯出
- **技術棧：** 純 HTML + CSS + Vanilla JS（單檔）
- **入口點：** `index.html`

---

## 一、技術棧決策（為什麼這樣選）

| 選擇 | 替代品 | 選這個的理由 |
|------|--------|------------|
| 純 HTML 單檔 | React / Vue | 離線可用、無需 build、醫院環境部署簡單 |
| localStorage | IndexedDB / 後端 | 個資不上傳、瀏覽器原生支援 |
| html2canvas + jsPDF | 後端 PDF 生成 | 純前端、離線可用 |
| OpenAI / Claude API | 本地 LLM | API 品質穩定、醫療文本理解佳 |

---

## 二、業務對映表

| 業務概念 | 程式實作 | 改這個動哪 |
|---------|---------|-----------|
| 預設範本 | `PRESET_TEMPLATES` 陣列 | index.html 約 600 行附近 |
| 密碼驗證 | `APP_PASSWORD` 常數 + `checkLogin()` | index.html 約 450 行 |
| 資料儲存 | `localStorage` key `chart_data` | `saveData()` / `loadData()` |
| AI 設定 | `localStorage` key `chart_ai_settings` | AI 分頁相關函數 |

---

## 三、關鍵檔案路徑

| 想改什麼 | 動哪些檔 |
|---------|---------|
| 配色 | `index.html` 開頭 `:root` CSS 變數 |
| 預設 Prompt 範本 | `index.html` 的 `PRESET_TEMPLATES` 陣列 |
| 密碼 | `index.html` 的 `APP_PASSWORD` 常數 |
| 分頁結構 | `index.html` 的 `.tab-btn` 和 `.tab-content` 區塊 |
| favicon | `favicon/` 資料夾（SELA 套組） |

---

## 四、踩過的坑（編號累積，永不重排）

### #1. localStorage key 版本衝突
- **症狀**：升版後資料消失或讀到舊格式
- **原因**：早期版本用 `chart_data_vX` 動態 key，版本一變就讀不到
- **做法**：固定 key 為 `chart_data`，加 migration 邏輯自動搬移舊 key

### #2. 遮罩姓名時機
- **症狀**：編輯時看到遮罩後的文字，無法正常編輯
- **原因**：遮罩在輸入時就套用
- **做法**：遮罩只在「產生預覽」時套用，編輯區保持原文

### #3. AI 服務切換 UX
- **症狀**：切換 AI 服務後設定沒存
- **原因**：select 是 disabled 狀態，需要先點編輯
- **做法**：移除 disabled，切換後自動儲存（`saveProviderChoice()`）

### #4. 預設範本密碼保護
- **症狀**：用戶不小心覆蓋預設範本
- **原因**：載入預設範本沒有保護機制
- **做法**：載入預設範本需輸入密碼（`Sela1227`）

---

## 五、煙霧測試（可貼上執行）

```bash
# === 純靜態 HTML，在瀏覽器開啟即可 ===
# 用 Live Server 或直接開檔案

# 驗證清單：
# 1. 開啟 index.html → 應看到密碼輸入畫面
# 2. 輸入 RTO → 應進入主畫面
# 3. 切換各分頁 → 應正常顯示
# 4. 輸入資料後重新整理 → 資料應保留（localStorage）
# 5. 產生預覽 → 應正確顯示格式化內容
# 6. 遮蔽姓名勾選 → 預覽中姓名應被遮蔽
```

---

## 六、版本歷程（最近 10 版）

| 版本 | 重點 |
|------|------|
| V7.0.1 | 修正 logo.jpg 404 + JS 語法錯誤；專案正式定名 Chart |
| V7.0.0 | 首次對齊 SELA-Starter-Kit V1.8.2，換 SELA favicon 套組，加 .gitignore / CLAUDE.md |
| V6.15.1 | Kit 對齊：頂部註解、theme-color |
| V6.15.0 | 密碼保護（RTO）、預載範本升級 v4 整合版 |
| V6.14.2 | 預載範本更新（放腫病歷整理 v3） |
| V6.14.1 | AI 服務選單直接可選 |
| V6.14.0 | UI 一致性：功能鍵統一上方 |
| V6.13.2 | 「重填」按鈕、病理分類新增分子檢測 |
| V6.13.1 | Prompt 分頁清除按鈕 |
| V6.13.0 | 遮蔽姓名移至病人分頁、三組預設範本 |
| V6.12.x | 預設範本載入目標選擇、多組預設 |

> 完整歷程見 README.md

---

## 七、下版候選工作（按優先序）

1. **PDF 匯出品質優化** — 目前 html2canvas 在長內容時有截斷問題，臨床報告需要完整列印
2. 多語系支援（英文介面選項）
3. 範本版本控制（顯示範本版本號、更新提示）
4. 匯入/匯出設定檔（方便跨裝置同步）
5. 深色模式

---

## 八、升版必讀

### V7.0.1 部署動作

- [x] favicon 套組已更新（`favicon/` 資料夾）
- [x] .gitignore 已加入
- [x] CLAUDE.md 已建立
- [x] SELA-handoff.md 已產出
- [ ] 部署後測：開啟 index.html 確認 favicon 正確顯示

---

## 九、一句話總結

V7.0.1 首次對齊 SELA-Starter-Kit，換上高清 favicon、加入 .gitignore 和 CLAUDE.md，下版第一優先是 PDF 匯出品質優化。
