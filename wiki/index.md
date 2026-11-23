---
title: "LLM Wiki Index & Knowledge Catalog"
type: index
created: 2026-11-23
last_updated: 2026-11-23
---

# LLM Wiki Index & 知識地圖 (Digital Logic Design)

歡迎來到「**數位邏輯設計：從布林代數到邏輯閘**」LLM Wiki。本知識庫由 LLM Agent 自主維護與交叉引用，記錄了數位積體電路與計算機結構底層的布林代數公理、定理、標準式與邏輯閘實現。

---

## 1. 原始講義摘要 (Lecture Summaries)
各篇原始教材之核心提煉與架構導讀：

- [[summary-c02a-intro-and-basic-operations]]：二值布林代數起源（Boole 與 Shannon）、NOT/AND/OR 基本運算、真值表與基礎開關電路公理。
- [[summary-c02b-laws-and-theorems]]：交換/結合/分配律（第二分配律）、狄摩根定律、吸收律、消去律、共識定理及對偶原理。
- [[summary-c02c-sop-pos-and-logic-gates]]：積之和 (SOP) 與和之積 (POS) 標準式、AND-OR/OR-AND 兩階電路、XOR、XNOR 及萬能閘 NAND/NOR。
- [[summary-c03a-advanced-factoring-and-xor]]：進階代數因式分解定理 $(X+Y)(X'+Z)=XZ+X'Y$、XOR 分配律、奇偶性與複合運算展開。
- [[summary-c03b-algebraic-simplification-and-proofs]]：開關表達式化簡三大基本手法、人為加入冗餘項技術、等式驗證可逆原則與「消去律完全失效」陷阱分析。

---

## 2. 核心概念庫 (Core Concept Pages)
高度原子化、具備雙向連結的知識單元：

| 概念頁面 | 核心主題簡介 | 關鍵字 / 標籤 |
|:---|:---|:---|
| [[boolean-algebra-fundamentals]] | 布林代數的歷史脈絡、0 與 1 的狀態本質、夏農開關電路對應模型 | `布林代數` `夏農` `開關模型` |
| [[basic-operations-and-truth-tables]] | NOT、AND、OR 運算定義、真值表構造法 ($2^n$ 列) 與文字 (Literal) 統計 | `NOT` `AND` `OR` `真值表` `Literal` |
| [[boolean-laws-and-theorems]] | 恆等元、等冪律、互補律、結合律、布林代數特有的第二分配律 $X+YZ=(X+Y)(X+Z)$ | `代數定律` `第二分配律` `公理` |
| [[demorgan-laws]] | 狄摩根定律雙變數與 $n$ 變數推廣、真值表證明、萬能閘轉換與對偶式差異 | `狄摩根` `DeMorgan` `萬能閘` `對偶性` |
| [[consensus-theorem]] | 共識定理 $XY+X'Z+YZ=XY+X'Z$ 之證明、項消除判定規則與人為添加冗餘項應用 | `共識定理` `冗餘項` `化簡` |
| [[canonical-forms-sop-pos]] | SOP (積之和) 與 POS (和之積) 定義、AND-OR / OR-AND 兩階硬體映射與因式分解 | `SOP` `POS` `兩階電路` `標準式` |
| [[logic-gates-and-circuits]] | 基本邏輯閘（NOT, AND, OR）、萬能閘（NAND, NOR）、算術核心閘（XOR, XNOR）與傳遞延遲 | `邏輯閘` `NAND` `NOR` `XOR` `XNOR` |
| [[algebraic-simplification-techniques]] | 合併項、消除項、消除文字、主動添加共識項等四階段代數化簡完整流程 | `化簡技巧` `合併項` `吸收律` `晶片成本` |
| [[equation-validity-and-cancellation-trap]] | 等式證明的合法路徑（單邊推導、雙邊化簡、反例反證）與消去律在布林代數中的重大陷阱 | `等式證明` `消去律陷阱` `反例` |

---

## 3. 輸出沉澱與教學成果 (Outputs & Presentations)
由 Wiki 內容查詢、聚合並生成的教學與分析產物：

- [[presentation-outline]]：從零開始懂數位邏輯設計的 11 頁互動教學 HTML 簡報完整大綱與知識點對應。
- `../presentation.html`：**可直接雙擊瀏覽的現代互動式教學 HTML 簡報**。
- `../SUBMISSION.md`：作業完整說明與成果報告（包含 loop/graph 流程圖、檢查紀錄與反思回答）。

---

## 4. 原始資料來源 (Raw Sources Registry)
- `sources/week1/20260910_SCLD_C02a.pdf` (Roth & Kinney, Unit 2 Part 1)
- `sources/week1/20260910_SCLD_C02b.pdf` (Roth & Kinney, Unit 2 Part 2)
- `sources/week1/20260910_SCLD_C02c.pdf` (Roth & Kinney, Unit 2 Part 3)
- `sources/week2/20260917_SCLD_C03a.pdf` (Roth & Kinney, Unit 3 Part 1)
- `sources/week2/20260917_SCLD_C03b.pdf` (Roth & Kinney, Unit 3 Part 2)
