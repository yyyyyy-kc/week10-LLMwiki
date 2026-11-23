---
title: 布林表達式代數化簡技巧 (Algebraic Simplification Techniques)
type: concept
tags: [數位邏輯設計, 化簡技巧, 合併項, 消除項, 冗餘項, 成本最佳化]
sources: ["[[sources/week1/20260910_SCLD_C02b.pdf]]", "[[sources/week2/20260917_SCLD_C03b.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 布林表達式代數化簡技巧 (Algebraic Simplification Techniques)

在晶片硬體設計中，化簡布林表達式能直接**減少邏輯閘數量**、**減少輸入接腳 (Literals)**、**縮小晶片面積**並**降低功耗與發熱**。

---

## 1. 四大核心化簡手法

### 手法一：合併項 (Combining Terms)
- **依據定理**：$XY + XY' = X$
- **概念**：若兩個乘積項只差在某一個變數為原形與補數，則可將該變數消去，合併為單一項。
- **實例**：
  $$ABC'D' + ABCD' = ABD'(C' + C) = ABD'(1) = ABD'$$
- **輔助技巧：利用 $X + X = X$ 複製項**：
  $$AB'C + ABC + A'BC = (AB'C + ABC) + (ABC + A'BC) = AC + BC$$

### 手法二：消除項 (Eliminating Terms)
- **依據定理**：
  1. 吸收律：$X + XY = X$
  2. 共識定理：$XY + X'Z + YZ = XY + X'Z$（消除共識項 $YZ$）
- **實例**：
  $$A'B + A'BC = A'B$$
  $$A'BC' + BCD + A'BD = A'BC' + BCD$$
  *(其中 $A'BD$ 是前兩項的共識項，可直接消除)*

### 手法三：消除文字 (Eliminating Literals)
- **依據定理**：$X + X'Y = X + Y$
- **概念**：當前項為單一變數 $X$，後項包含反相文字 $X'$ 時，$X'$ 可以被無條件消除。
- **實例**：
  $$\begin{aligned}
  A'B + A'B'C'D' + ABCD' &= A'(B + B'C'D') + ABCD' \\
  &= A'(B + C'D') + ABCD' \\
  &= A'B + A'C'D' + ABCD' \\
  &= B(A' + ACD') + A'C'D' \\
  &= B(A' + CD') + A'C'D' \\
  &= A'B + BCD' + A'C'D'
  \end{aligned}$$

### 手法四：人為添加冗餘項 (Adding Redundant Terms)
- 當直觀的化簡停滯時，可以策略性地加入恆等冗餘項以觸發連鎖化簡：
  - 乘以 $(X + X')$（相當於乘 1）
  - 加上 $XX'$（相當於加 0）
  - 加入共識項 $YZ$

---

## 2. 實例完整演練
簡化表達式：
$$F = A'B'C'D' + A'BC'D' + A'BD + A'BC'D + ABCD + ACD' + B'CD'$$

1. 合併 $A'B'C'D' + A'BC'D' = A'C'D'$：
   $$F = A'C'D' + A'BD + A'BC'D + ABCD + ACD' + B'CD'$$
2. 合併 $A'BD + ABCD = BD(A' + AC) = BD(A' + C) = A'BD + BCD$：
   $$F = A'C'D' + A'BD + BCD + ACD' + B'CD'$$
3. 觀察 $BCD$ 與 $ACD'$，其共識項為 $ABC$。人為引入 $ABC$：
   $$F = A'C'D' + A'BD + BCD + ACD' + B'CD' + ABC$$
4. 結合 $BCD + ACD' + ABC + B'CD'$ 進行連續吸收化簡，最終大幅精簡為：
   $$F = A'C'D' + A'BD + B'CD' + ABC$$
   原本 28 個文字縮減至僅剩 13 個文字，邏輯閘成本減半！

## 關聯頁面
- [[boolean-laws-and-theorems]]
- [[consensus-theorem]]
- [[equation-validity-and-cancellation-trap]]
- [[summary-c03b-algebraic-simplification-and-proofs]]
