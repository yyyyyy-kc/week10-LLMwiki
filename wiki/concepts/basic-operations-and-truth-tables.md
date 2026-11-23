---
title: 基本運算與真值表 (Basic Operations and Truth Tables)
type: concept
tags: [布林代數, NOT, AND, OR, 真值表, Literal]
sources: ["[[sources/week1/20260910_SCLD_C02a.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 基本運算與真值表 (Basic Operations and Truth Tables)

布林代數建構於三個最基本的操作之上：**補數 (NOT)**、**邏輯乘法 (AND)** 與 **邏輯加法 (OR)**。

## 1. 三大基本運算

### 1.1 反相 / 補數 (Complement / NOT)
- **定義**：改變輸入的邏輯值。
- **符號**：通常以右上撇號 $X'$ 或上劃線 $\overline{X}$ 表示。
- **公理規律**：
  $$0' = 1, \quad 1' = 0$$

### 1.2 邏輯乘法 (Logical Multiplication / AND)
- **定義**：僅當所有輸入皆為 1 時，結果才為 1；只要有任何一個輸入為 0，結果即為 0。
- **符號**：以居中點號 $\cdot$ 或直接相連表示（例如 $A \cdot B$ 或 $AB$）。
- **公理規律**：
  $$0 \cdot 0 = 0, \quad 0 \cdot 1 = 0, \quad 1 \cdot 0 = 0, \quad 1 \cdot 1 = 1$$

### 1.3 邏輯加法 (Logical Addition / Inclusive-OR)
- **定義**：只要有任何一個輸入為 1，結果即為 1；僅當所有輸入皆為 0 時，結果才為 0。
- **符號**：以加號 $+$ 表示（例如 $A + B$）。
- **公理規律**：
  $$0 + 0 = 0, \quad 0 + 1 = 1, \quad 1 + 0 = 1, \quad 1 + 1 = 1$$
  *(注意：$1 + 1 = 1$ 是布林代數與一般數值代數最本質的差異之一！)*

---

## 2. 真值表 (Truth Table)
**真值表 (Truth Table)**，又稱**組合表 (Table of Combinations)**，是窮舉一個布林函數所有可能輸入組合與對應輸出值的完整表格。

### 基本真值表對照

| $A$ | $B$ | $A'$ (NOT) | $A \cdot B$ (AND) | $A + B$ (OR) |
|:---:|:---:|:----------:|:-----------------:|:------------:|
|  0  |  0  |     1      |         0         |      0       |
|  0  |  1  |     1      |         0         |      1       |
|  1  |  0  |     0      |         0         |      1       |
|  1  |  1  |     0      |         1         |      1       |

### 真值表的維度規律
- 若一個布林表達式包含 $n$ 個獨立布林變數，其所有可能狀態組合總數為：
  $$N_{\text{rows}} = 2^n$$
- 例如：3 個變數（$A, B, C$）共有 $2^3 = 8$ 列；4 個變數共有 $2^4 = 16$ 列。

---

## 3. 文字 (Literal) 定義
- **文字 (Literal)** 是指在布林表達式中，**變數本身或其補數**的單次出現。
- 範例分析：
  $$F = AB'C + A'B + A'BC' + B'C'$$
  - 項數（Terms）：4 個
  - 變數種類：3 個（$A, B, C$）
  - 文字總數（Literals）：$3 + 2 + 3 + 2 = 10$ 個文字。
- **工程意義**：在硬體實作中，文字總數往往直接決定了邏輯閘的輸入接腳（Inputs / Fan-in）數量，文字越少代表電路面積越小、成本越低。

## 關聯頁面
- [[boolean-algebra-fundamentals]]
- [[boolean-laws-and-theorems]]
- [[canonical-forms-sop-pos]]
- [[summary-c02a-intro-and-basic-operations]]
