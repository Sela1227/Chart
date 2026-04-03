# 病歷整理器 V6.3 Web

> 彰濱癌症中心 · Chang Bing Show Chwan Memorial Hospital  
> © SELA · Radiation Oncology

## 簡介

病歷整理器是一款用於整理和輸出病歷資料的網頁應用程式，可於瀏覽器中離線使用，亦可部署於 GitHub Pages。

## 功能特色

- **7 個分頁管理**：Prompt、病人資料、病摘、檢驗資料、病理報告、影像報告、預覽輸出
- **10 個 Prompt 範本**：可儲存、載入、重命名
- **病人資料管理**：含 ECOG 及衰弱量表評估
- **報告管理**：病理報告與影像報告的新增、編輯、刪除
- **自動儲存**：資料自動存入 localStorage
- **匯出功能**：支援 TXT 及 PDF 格式
- **個資遮蔽**：匯出時可選擇遮蔽病人資訊

## 部署至 GitHub Pages

1. 建立新的 GitHub Repository
2. 將本資料夾中的檔案上傳：
   - `index.html`
   - `logo.jpg`
3. 進入 Repository 的 Settings → Pages
4. Source 選擇 `main` branch，資料夾選 `/ (root)`
5. 儲存後等待部署完成
6. 網址格式：`https://你的帳號.github.io/repository名稱/`

## 本地使用

直接用瀏覽器開啟 `index.html` 即可使用。

## 技術規格

- **字型**：Noto Sans TC（Google Fonts，支援中文）
- **圖示**：SVG inline icons
- **PDF 匯出**：html2canvas + jsPDF
- **資料儲存**：localStorage
- **配色**：北歐簡潔風格（霧灰 + 淺色系，Logo 橘色）

## 版本歷史

- **V6.3** - Web 版本，北歐風格設計，SVG 圖示，GitHub Pages 支援
- **V6.2** - Flet 0.80 相容版本
- **V6.1** - 原始 Flet 桌面版本

## 瀏覽器相容性

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## 授權

© SELA · Radiation Oncology · CBSHOW
