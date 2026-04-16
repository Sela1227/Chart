# 病歷整理器 (Chart)

> 彰濱癌症中心 · Chang Bing Show Chwan Memorial Hospital  
> © SELA · Radiation Oncology

---

## 簡介

病歷整理器是一款用於整理和輸出病歷資料的網頁應用程式，可於瀏覽器中離線使用，亦可部署於 GitHub Pages。

---

## 功能特色

- **8 個分頁管理**：Prompt、病人資料、病摘、檢驗、病理、影像、預覽、AI
- **10 個 Prompt 範本**：編輯/儲存/命名分開操作
- **病人資料管理**：姓名、年齡、病歷號、ECOG、衰弱量表
- **檢驗資料**：自由輸入 + 腫瘤指數追蹤（支援連續輸入）
- **報告管理**：病理報告與影像報告
- **AI 整理功能**：支援 OpenAI / Claude API 自動整理病歷
- **匯出功能**：支援 TXT、HTML、PDF 格式
- **個資遮蔽**：預覽及匯出時可遮蔽病人姓名與病歷號

---

## 版本歷程

### V6.10.4 (2026-04-13)
**新增功能：**
- HTML 報告匯出
  - 專業排版設計
  - 內嵌 Noto Sans TC 字型
  - 支援列印友善模式
  - 自動格式化章節標題

---

### V6.9.3 (2026-04-13)
- 統一顯示順序：病歷號 → 姓名 → 年齡

---

### V6.9.2 (2026-04-13)
- 預覽時執行個資遮罩
- 新增病人資訊列

---

### V6.9.x
- AI 整理功能
- API Key 編輯保護

---

### V6.8.x
- 腫瘤指數追蹤功能
- 連續輸入模式

---

## 匯出格式說明

| 格式 | 說明 |
|------|------|
| TXT | 純文字，適合複製貼上 |
| HTML | 網頁格式，可直接瀏覽或列印 |
| PDF | 固定版面，適合存檔分享 |

---

## 技術規格

| 項目 | 說明 |
|------|------|
| 字型 | Noto Sans TC (Google Fonts) |
| 圖示 | SVG inline icons |
| PDF 匯出 | html2canvas + jsPDF |
| 資料儲存 | localStorage |
| AI 整合 | OpenAI API / Anthropic API |

---

## 授權

© SELA · Radiation Oncology · CBSHOW
