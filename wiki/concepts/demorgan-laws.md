---
title: 狄摩根定律與對偶性 (De Morgan's Laws and Duality)
type: concept
tags: [布林代數, 狄摩根定律, 對偶性, 邏輯閘轉換, 萬能閘]
sources: ["[[sources/week1/20260910_SCLD_C02b.pdf]]", "[[sources/week1/20260910_SCLD_C02c.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 狄摩根定律與對偶性 (De Morgan's Laws and Duality)

**奧古斯都·德·摩根 (Augustus De Morgan)** 提出的定律是布林代數與數位邏輯電路設計中最重要的等價轉換工具。

---

## 1. 狄摩根定律公式

### 1.1 雙變數形式
$$(X + Y)' = X'Y'$$
$$(XY)' = X' + Y'$$

### 1.2 推廣至 $n$ 個變數
$$(X_1 + X_2 + \dots + X_n)' = X_1' X_2' \dots X_n'$$
$$(X_1 X_2 \dots X_n)' = X_1' + X_2' + \dots + X_n'$$

### 1.3 核心記憶口訣
- **「總和的補數等於補數的乘積」** (The complement of the sum is the product of complements)
- **「乘積的補數等於補數的總和」** (The complement of the product is the sum of complements)
- 操作口訣：「**斷長線、變符號**」——將整個長長的上劃線（補數線）切斷分配給各變數，並將內部的 $+$ 變成 $\cdot$ 或 $\cdot$ 變成 $+$。

---

## 2. 真值表嚴格驗證

| $X$ | $Y$ | $X+Y$ | $(X+Y)'$ | $X'Y'$ | $XY$ | $(XY)'$ | $X'+Y'$ |
|:---:|:---:|:-----:|:--------:|:------:|:----:|:-------:|:-------:|
|  0  |  0  |   0   |  **1**   | **1**  |  0   |  **1**  |  **1**  |
|  0  |  1  |   1   |  **0**   | **0**  |  0   |  **1**  |  **1**  |
|  1  |  0  |   1   |  **0**   | **0**  |  0   |  **1**  |  **1**  |
|  1  |  1  |   1   |  **0**   | **0**  |  1   |  **0**  |  **0**  |

真值表第 4 行與第 5 行完全一致，第 7 行與第 8 行完全一致，定理得證。

---

## 3. 電路工程意涵：萬能邏輯閘的理論基礎
- **NOR 閘等效轉換**：$(A + B)' = A'B'$
  - 一個 NOR 閘等價於一個輸入端加了反相器的 AND 閘（Negative-AND）。
- **NAND 閘等效轉換**：$(AB)' = A' + B'$
  - 一個 NAND 閘等價於一個輸入端加了反相器的 OR 閘（Negative-OR）。
- **萬能閘 (Universal Gates)**：
  - 透過狄摩根定律，工程師可以**完全僅用 NAND 閘**或**完全僅用 NOR 閘**實現所有的基本邏輯運算（NOT, AND, OR），這極大降低了積體電路 (IC) 製造時的光罩與晶圓製程成本。

---

## 4. 補數 (Complement) vs 對偶式 (Dual) 的關鍵區別
許多初學者常將對偶原理與狄摩根求補數混淆：
- **求補數 (Complement)**：
  - 將 AND 換為 OR、OR 換為 AND、0 換為 1、1 換為 0，**並且每個變數也取反相**（$X \rightarrow X'$）。
  - 例：$(AB' + C)' = (A' + B)C'$。
- **求對偶 (Dual)**：
  - 將 AND 換為 OR、OR 換為 AND、0 換為 1、1 換為 0，**變數與原有補數維持原樣不變**！
  - 例：$(AB' + C)^D = (A + B')C$。

## 關聯頁面
- [[boolean-laws-and-theorems]]
- [[logic-gates-and-circuits]]
- [[canonical-forms-sop-pos]]
- [[summary-c02b-laws-and-theorems]]
