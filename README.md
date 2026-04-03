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
- **病人資料管理**：姓名、年齡、病歷號、ECOG、衰弱量表 (CFS 1-9)
- **報告管理**：病理報告（Biopsy/Pathology 多選）與影像報告
- **日期驗證**：輸入格式錯誤會即時提示警告
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

## 版本命名規則

自 V6.6.0 起採用三碼版本號：`V主版本.功能版本.修正版本`

| 變更類型 | 版本號變化 | 範例 |
|---------|-----------|------|
| 大改版 | +1.0.0 | V6.6.0 → V7.0.0 |
| 新增功能 | +0.1.0 | V6.6.0 → V6.7.0 |
| 修正小 bug | +0.0.1 | V6.6.0 → V6.6.1 |

---

## 版本歷程

### V6.6.0 (2026-04-03)
**新增功能：**
- 版本命名規則改為三碼制（主版本.功能.修正）
- 病人資料新增「年齡」欄位（選填，數字輸入）
- 日期輸入驗證功能
  - 輸入格式錯誤時顯示紅色邊框
  - 欄位下方顯示錯誤提示訊息
  - 跳出黃色警告 Toast
  - 驗證月份（1-12）與日期（考慮大小月、閏年）

---

### V6.5 (2026-04-03)
**變更內容：**
- 日期輸入即時格式化（輸入 8 碼立即轉換）
- 範本編輯機制（需按編輯→修改→儲存）
- 病理報告 Biopsy/Pathology 多選分類
- 版面高度優化（10 個範本無需滾軸）

---

### V6.4 (2026-04-03)
**變更內容：**
- 專案重新命名為 Chart
- 新增 README 版本歷程記錄
- ZIP 與資料夾統一命名規則

---

### V6.3 (2026-04-03)
**變更內容：**
- 霧灰色比例提高（北歐風格配色）
- 日期輸入改為文字輸入框
- 報告編輯區版面優化

---

### V6.2 (2026-04-03)
**變更內容：**
- 從 Flet Python 桌面應用轉換為 HTML5 網頁版本
- 技術架構：HTML5 + CSS3 + JavaScript
- jsPDF + html2canvas 用於 PDF 匯出
- localStorage 取代 JSON 檔案儲存
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
