---
title: "講義摘要：Boolean Algebra (2) - 定律、化簡定理與對偶性"
type: summary
tags: [數位邏輯設計, 布林代數, 代數定律, 狄摩根定律, 共識定理, 對偶性]
sources: ["[[sources/week1/20260910_SCLD_C02b.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 講義摘要：Boolean Algebra (2) - 定律、化簡定理與對偶性

本單元源自 Charles H. Roth & Larry L. Kinney 之《Fundamentals of Logic Design》第 2 章第 2 部分，詳細討論了布林代數中的關鍵代數律、經典化簡定理、狄摩根定律、共識定理以及對偶原理。

## 1. 基本代數定律
- **交換律 (Commutative Laws)**：
  - $XY = YX$
  - $X + Y = Y + X$
- **結合律 (Associative Laws)**：
  - $(XY)Z = X(YZ) = XYZ$
  - $(X + Y) + Z = X + (Y + Z) = X + Y + Z$
  - 電路意義：多個兩輸入 AND 閘可串接簡化為單一多輸入 AND 閘；OR 閘同理。
- **分配律 (Distributive Laws)**：
  - 第一分配律（常規）：$X(Y + Z) = XY + XZ$（AND 對 OR 分配）
  - 第二分配律（**布林代數特有**）：$X + YZ = (X + Y)(X + Z)$（OR 對 AND 分配）
  - 證明：展開右式 $(X + Y)(X + Z) = XX + XZ + YX + YZ = X + XZ + XY + YZ = X(1 + Z + Y) + YZ = X(1) + YZ = X + YZ$。

## 2. 狄摩根定律 (DeMorgan's Laws)
- 雙變數形式：
  - $(X + Y)' = X'Y'$
  - $(XY)' = X' + Y'$
- 推廣至 $n$ 個變數：
  - $(X_1 + X_2 + \dots + X_n)' = X_1' X_2' \dots X_n'$
  - $(X_1 X_2 \dots X_n)' = X_1' + X_2' + \dots + X_n'$
- 口訣原則：
  - 乘積的補數等於補數的總和。
  - 總和的補數等於補數的乘積。

## 3. 常用化簡定理 (Simplification Theorems)
- **結合項化簡 / 單位元消除 (Unity)**：
  - $XY + XY' = X$
  - $(X + Y)(X + Y') = X$
- **吸收律 (Absorption)**：
  - $X + XY = X$
  - $X(X + Y) = X$
- **多餘項消除 (Elimination)**：
  - $X + X'Y = X + Y$
  - $X(X' + Y) = XY$

## 4. 共識定理 (The Consensus Theorem)
- **標準形式**：
  $$XY + X'Z + YZ = XY + X'Z$$
  其中 $YZ$ 被稱為「共識項 (Consensus Term)」，可以被直接剔除。
- **產生條件**：當有一對項，其中一項包含某變數（$X$），另一項包含其反相變數（$X'$），將兩項中其餘變數相乘（$Y \cdot Z$），即為共識項。
- **對偶形式 (Dual of Consensus Theorem)**：
  $$(X + Y)(X' + Z)(Y + Z) = (X + Y)(X' + Z)$$

## 5. 對偶原理 (Duality)
- **對偶式 (Dual)** 的構成方式：將原式中的 AND 換為 OR、OR 換為 AND、0 換為 1、1 換為 0，**變數與補數本身保持不變**。
- 表達式補數與對偶的本質差異：
  - 補數式 (Complement)：$(AB' + C)' = (A' + B)C'$
  - 對偶式 (Dual)：$(AB' + C)^D = (A + B')C$

## 關聯概念頁面
- [[boolean-laws-and-theorems]]
- [[demorgan-laws]]
- [[consensus-theorem]]
- [[algebraic-simplification-techniques]]
