---
title: "講義摘要：Boolean Algebra (1) - 基礎運算與開關電路"
type: summary
tags: [數位邏輯設計, 布林代數, 基礎運算, 真值表, 開關電路]
sources: ["[[sources/week1/20260910_SCLD_C02a.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 講義摘要：Boolean Algebra (1) - 基礎運算與開關電路

本單元源自 Charles H. Roth & Larry L. Kinney 之《Fundamentals of Logic Design》第七版第 2 章第 1 部分，奠定了整個數位邏輯電路設計的數學基礎。

## 1. 核心背景與起源
- **二值布林代數 (Two-valued Boolean algebra)**：常被稱為「開關代數 (Switching algebra)」。
- **歷史演進**：
  - 1847 年，**喬治·布爾 (George Boole)** 創立布林代數，用於解決數學邏輯問題。
  - 1939 年，**克勞德·夏農 (Claude Shannon)** 首次將布林代數應用於繼電器與開關電路的設計，開啟了資訊時代。
- **變數與符號**：布林變數 $X$ 僅有兩種可能取值：$X = 0$ 或 $X = 1$。此處的符號「0」與「1」不具備數值大小意義，僅代表狀態（如開/關、高電位/低電位、假/真）。

## 2. 三大基本運算 (Basic Operations)
1. **反相 / 補數 (Complement / Inverse / NOT)**：
   - 符號以撇號（Prime）表示：$0' = 1$，$1' = 0$。若 $X$ 為開關變數，則當 $X=1$ 時 $X'=0$；當 $X=0$ 時 $X'=1$。
2. **邏輯乘法 (Logical Multiplication / AND)**：
   - 定義：$0 \cdot 0 = 0$、$0 \cdot 1 = 0$、$1 \cdot 0 = 0$、$1 \cdot 1 = 1$。
   - 僅當所有輸入皆為 1 時，輸出才為 1。
3. **邏輯加法 (Logical Addition / Inclusive-OR)**：
   - 定義：$0 + 0 = 0$、$0 + 1 = 1$、$1 + 0 = 1$、$1 + 1 = 1$。
   - 只要有任一輸入為 1，輸出即為 1。

## 3. 開關電路模型 (Switching Circuit Analogy)
- 開關狀態定義：
  - $X = 0$ 表示開關斷開（Switch Open，不導通）。
  - $X = 1$ 表示開關閉合（Switch Closed，導通）。
- 串聯電路對應 **AND** 運算：只有兩開關皆閉合時，電路才導通 ($T = A \cdot B$)。
- 並聯電路對應 **OR** 運算：任一開關閉合時，電路即導通 ($T = A + B$)。

## 4. 布林表達式與真值表 (Truth Tables)
- **真值表 (Truth Table / Table of Combinations)**：列出布林表達式中所有變數取值組合及其對應的輸出值。
- 若表達式包含 $n$ 個變數，其真值表將恰好擁有 $2^n$ 種不同的輸入組合。
- **文字 (Literal)**：變數或其補數在表達式中的每一次出現均稱為一個文字。例如 $ab'c + a'b + a'bc' + b'c'$ 共計包含 10 個文字。

## 5. 基本定理 (Basic Theorems)
- **與 0 和 1 的運算**：
  - $X + 0 = X$，$X + 1 = 1$
  - $X \cdot 1 = X$，$X \cdot 0 = 0$
- **等冪律 (Idempotent Laws)**：
  - $X + X = X$
  - $X \cdot X = X$
- **雙重否定律 / 對合律 (Involution)**：
  - $(X')' = X$
- **互補律 (Laws of Complementarity)**：
  - $X + X' = 1$
  - $X \cdot X' = 0$

## 關聯概念頁面
- [[boolean-algebra-fundamentals]]
- [[basic-operations-and-truth-tables]]
- [[boolean-laws-and-theorems]]
- [[logic-gates-and-circuits]]
