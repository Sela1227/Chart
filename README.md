# 病歷整理器 (Chart)

> 彰濱癌症中心 · Chang Bing Show Chwan Memorial Hospital  
> © SELA · Radiation Oncology

---

## 簡介

病歷整理器是一款用於整理和輸出病歷資料的網頁應用程式，可於瀏覽器中離線使用，亦可部署於 GitHub Pages。

---

## 功能特色

- **7 個分頁管理**：Prompt、病人資料、病摘、檢驗、病理、影像、預覽
- **10 個 Prompt 範本**：需先按編輯才能修改內容，可直接重命名
- **病人資料管理**：含 ECOG 及衰弱量表 (CFS 1-9) 評估
- **報告管理**：病理報告（支援 Biopsy/Pathology 多選分類）與影像報告
- **自動儲存**：資料自動存入 localStorage
- **匯出功能**：支援 TXT 及 PDF 格式
- **個資遮蔽**：匯出時可選擇遮蔽病人姓名與病歷號

---

## 部署至 GitHub Pages

1. 建立新的 GitHub Repository
2. 上傳 `index.html` 和 `logo.jpg`
3. Settings → Pages → Source: `main` / `/ (root)`
4. 網址：`https://你的帳號.github.io/repository名稱/`

---

## 版本歷程

### V6.5 (2026-04-03)
**變更內容：**
- 日期輸入即時格式化
  - 輸入 8 碼數字（如 `20211227`）即時自動轉換為 `2021-12-27`
  - 不需等待失焦，輸入完成立即格式化
- 範本編輯機制調整
  - Prompt textarea 預設為唯讀
  - 需先按「編輯」按鈕進入編輯模式
  - 編輯後按「儲存」確認，或「取消」放棄修改
  - 「命名」功能可直接使用，無需進入編輯模式
- 病理報告增加分類多選
  - 可勾選 Biopsy / Pathology（可複選）
  - 表格顯示分類欄位
  - 預覽輸出包含 Category 資訊
- 版面高度優化
  - 調整範本列表區域大小，10 個範本無需滾軸
  - 減少各元件 padding/margin
  - 整體版面更緊湊

---

### V6.4 (2026-04-03)
**變更內容：**
- 專案重新命名為 Chart
- 新增 README 版本歷程記錄
- ZIP 與資料夾統一命名規則 `Chart_v版本號`

---

### V6.3 (2026-04-03)
**變更內容：**
- 霧灰色比例提高
  - 主背景：`#CBD5E1`（霧灰）
  - 次要背景：`#94A3B8`（深霧灰）
  - 卡片背景：`#F1F5F9`（淺灰）
  - 僅 Logo 保持橘色 `#F97316`
- 日期輸入改為文字輸入框（移除日曆選擇器）
- 報告編輯區版面優化（日期、按鈕同一行）

---

### V6.2 (2026-04-03)
**變更內容：**
- 從 Flet Python 桌面應用轉換為純 HTML5 網頁版本
- 技術架構：HTML5 + CSS3 + Vanilla JavaScript
- jsPDF + html2canvas 用於 PDF 匯出
- localStorage 取代 JSON 檔案儲存
- 北歐簡潔配色 + SVG 圖示
- 字型：Noto Sans TC（Google Fonts）

---

### V6.1 → V6.2 (Flet 升級)
**變更內容：**
- Flet 框架從 0.28 升級至 0.80 相容
- API 變更對應（詳見升級指南）

---

### V6.1 (原始版本)
**功能：**
- Flet Python 桌面應用程式
- 7 個分頁管理、10 個 Prompt 範本
- 病理/影像報告管理
- TXT/PDF 匯出、個資遮蔽功能

---

## 技術規格

| 項目 | 說明 |
|------|------|
| 字型 | Noto Sans TC (Google Fonts) |
| 圖示 | SVG inline icons |
| PDF 匯出 | html2canvas + jsPDF |
| 資料儲存 | localStorage |
| 配色 | 北歐風格（霧灰 + 淺色系，Logo 橘色） |

---

## 瀏覽器相容性

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

---

## 授權

© SELA · Radiation Oncology · CBSHOW
