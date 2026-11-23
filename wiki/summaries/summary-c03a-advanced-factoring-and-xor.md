---
title: "講義摘要：Boolean Algebra (Continued) (1) - 進階因式分解與 XOR 代數運算"
type: summary
tags: [數位邏輯設計, 布林代數, 因式分解, XOR, 等價運算, 電路化簡]
sources: ["[[sources/week2/20260917_SCLD_C03a.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 講義摘要：Boolean Algebra (Continued) (1) - 進階因式分解與 XOR 代數運算

本單元源自 Charles H. Roth & Larry L. Kinney 之《Fundamentals of Logic Design》第 3 章第 1 部分，深入解析布林表達式的進階展開、互斥或 (XOR) 與等價 (Equivalence) 之代數代換技巧。

## 1. 展開與因式分解的強大定理
- **核心雙向轉換定理**：
  $$(X + Y)(X' + Z) = XZ + X'Y \quad (\text{POS 轉 SOP})$$
  $$XY + X'Z = (X + Z)(X' + Y) \quad (\text{SOP 轉 POS})$$
- **證明技巧**：
  - 當 $X = 0$ 時：左式 $= (0 + Y)(1 + Z) = Y(1 + Z) = Y$；右式 $= 0 \cdot Z + 1 \cdot Y = Y$。兩式相等。
  - 當 $X = 1$ 時：左式 $= (1 + Y)(0 + Z) = 1 \cdot Z = Z$；右式 $= 1 \cdot Z + 0 \cdot Y = Z$。兩式相等。
  - 由於布林變數僅有 0 與 1 兩種可能，故定理完全得證。

## 2. 互斥或 (XOR) 的進階代數性質
- **分配律**：
  $$X(Y \oplus Z) = XY \oplus XZ$$
  證明可利用 $XY \oplus XZ = XY(XZ)' + (XY)'XZ = XYZ' + XY'Z = X(YZ' + Y'Z) = X(Y \oplus Z)$。
- **補數與等價性**：
  $$(X \oplus Y)' = X \oplus Y' = X' \oplus Y = XY + X'Y' = (X \equiv Y)$$
- **多變數奇偶判斷 (Odd-parity Property)**：
  - $0 \oplus 0 \oplus \dots \oplus 1$：當式子中「1」的個數為奇數時，結果為 1；若「1」的個數為偶數時，結果為 0。
  - 在奇偶校驗（Parity generation and checking）中應用極廣。

## 3. 含 $\oplus$ 與 $\equiv$ 的化簡操作策略
- 當面對含有 $\oplus$ (XOR) 或 $\equiv$ (Equivalence) 的複合表達式時：
  1. 第一步先利用基本定義將 $\oplus$ 與 $\equiv$ 展開為 AND、OR 與 NOT 的形式：
     - $A \equiv B \rightarrow AB + A'B'$
     - $A \oplus B \rightarrow AB' + A'B$
  2. 展開後應用吸收律、消去律或共識定理進行項的化簡與合併。

## 關聯概念頁面
- [[boolean-laws-and-theorems]]
- [[logic-gates-and-circuits]]
- [[algebraic-simplification-techniques]]
