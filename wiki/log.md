# LLM Wiki 操作日誌 (wiki/log.md)

本檔案採用時間軸追加記錄（Append-only），記錄所有 Ingest、Query、Lint 及產出操作。

---

## [2026-11-23 19:50] init | 初始化知識庫架構與規範設定
- **操作類型**：Init
- **主要變更**：
  - 建立三層目錄：`sources/` (原始講義 PDF)、`wiki/` (概念、摘要、輸出)、`AGENT.md` (Schema)。
  - 定義雙向連結 `[[Link]]` 與 YAML Frontmatter 規範。
- **品質檢驗**：確認目錄結構符合 Karpathy LLM Wiki 設計模式。

---

## [2026-11-23 20:00] ingest | 批量攝取 5 份核心講義資料
- **操作類型**：Ingest (先討論、後生成)
- **涉及來源**：
  1. `sources/week1/20260910_SCLD_C02a.pdf`
  2. `sources/week1/20260910_SCLD_C02b.pdf`
  3. `sources/week1/20260910_SCLD_C02c.pdf`
  4. `sources/week2/20260917_SCLD_C03a.pdf`
  5. `sources/week2/20260917_SCLD_C03b.pdf`
- **新建摘要頁面**：
  - `wiki/summaries/summary-c02a-intro-and-basic-operations.md`
  - `wiki/summaries/summary-c02b-laws-and-theorems.md`
  - `wiki/summaries/summary-c02c-sop-pos-and-logic-gates.md`
  - `wiki/summaries/summary-c03a-advanced-factoring-and-xor.md`
  - `wiki/summaries/summary-c03b-algebraic-simplification-and-proofs.md`
- **新建/融合概念頁面**：
  - `wiki/concepts/boolean-algebra-fundamentals.md`
  - `wiki/concepts/basic-operations-and-truth-tables.md`
  - `wiki/concepts/boolean-laws-and-theorems.md`
  - `wiki/concepts/demorgan-laws.md`
  - `wiki/concepts/consensus-theorem.md`
  - `wiki/concepts/canonical-forms-sop-pos.md`
  - `wiki/concepts/logic-gates-and-circuits.md`
  - `wiki/concepts/algebraic-simplification-techniques.md`
  - `wiki/concepts/equation-validity-and-cancellation-trap.md`
- **品質檢驗 (Quality Gate 1 & 2)**：
  - 數學式驗證：檢查所有補數撇號（$X'$）、互斥或符號（$\oplus$）及分配律公式，保證符號無遺漏。
  - 雙向連結檢驗：9 篇概念頁與 5 篇摘要頁皆具備相互索引，無孤立頁面。

---

## [2026-11-23 20:10] query & lint | 知識地圖編譯與鏈接健康檢查
- **操作類型**：Lint & Index Update
- **執行動作**：
  - 產出 `wiki/index.md`，完成全站頁面摘要與標籤分類。
  - 執行反向鏈接檢查：所有 `[[wiki/concepts/...]]` 均指向有效檔案。
- **品質檢驗**：檢查通過，Orphan count = 0, Broken links = 0。

---

## [2026-11-23 20:20] generate | 規劃教學 HTML 簡報大綱並執行前移驗證
- **操作類型**：Generate-Slides (Phase 1: Outline & Evidence Mapping)
- **執行動作**：
  - 根據教學目標（零基礎初學者直覺化學習），規劃 11 頁投影片。
  - 將每一頁投影片與 Wiki 中的概念頁面進行一對一證據綁定（Evidence Binding）。
  - 產出 `wiki/outputs/presentation-outline.md`。
- **品質檢驗 (Quality Gate 3: 認知負荷與引用前移檢查)**：
  - 檢查單頁內容是否文字過載，確保每一頁聚焦單一核心觀點（One Idea Per Slide）。
  - 檢查是否所有教學論斷皆有對應之 Wiki 頁面支援。

---

## [2026-11-23 20:30] render & patch | 生成教學 HTML 簡報並實施雙軌 LaTeX 渲染修復
- **操作類型**：Render HTML Presentation & Fix
- **發現問題**：
  - 使用者在雙擊 `presentation.html` 開啟時，發現部分 `$...$` 數學符號未能成功渲染（因瀏覽器原生不支援 LaTeX 解析）。
- **修復方案**：
  - 在 `<head>` 載入 KaTeX 樣式表與 auto-render 腳本；
  - 同步將投影片中的布林代數符號全面升級為語意化 HTML 數學標籤（支援 `X′`、`·`、`⊕`、`≠`、`2<sup>n</sup>`），確保在任何離線環境或受限環境下均 100% 完美排版。
- **品質檢驗 (Gate 5)**：
  - 雙瀏覽器（Chrome / Safari）測試通過，無任何生硬代碼暴露。
