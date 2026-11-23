---
title: 共識定理 (The Consensus Theorem)
type: concept
tags: [布林代數, 共識定理, 冗餘消除, 電路化簡]
sources: ["[[sources/week1/20260910_SCLD_C02b.pdf]]", "[[sources/week2/20260917_SCLD_C03b.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 共識定理 (The Consensus Theorem)

**共識定理 (Consensus Theorem)** 是布林代數中極具啟發性的高階化簡技巧，能幫助我們肉眼識別並消除看似獨立、實則完全多餘的「共識項 (Consensus Term)」。

---

## 1. 定理標準形式
$$XY + X'Z + YZ = XY + X'Z$$

- 式中的 $YZ$ 稱為 **共識項 (Consensus Term)**。
- 由於其邏輯值完全被前兩項涵蓋，因此可以直接從表達式中刪除而不改變整體邏輯功能。

---

## 2. 嚴格代數證明
透過在共識項 $YZ$ 上乘以布林恆等式 $(X + X') = 1$：
$$\begin{aligned}
XY + X'Z + YZ &= XY + X'Z + (X + X')YZ \\
&= XY + X'Z + XYZ + X'YZ \\
&= XY(1 + Z) + X'Z(1 + Y) \\
&= XY(1) + X'Z(1) \\
&= XY + X'Z \quad \text{Q.E.D.}
\end{aligned}$$

---

## 3. 共識項的識別規則
給定兩個乘積項（Product terms）：
1. 檢視其中是否有且僅有一對**互補變數**（一項有 $X$，另一項有 $X'$）。
2. 將這兩項中除了 $X$ 與 $X'$ 以外的所有其餘文字相乘。
3. 所得的乘積若出現在表達式中，該項即為共識項，可直接刪除。

### 範例：
- $AB$ 與 $A'C$ 的共識項為 $BC$。
- $ABD$ 與 $B'DE'$ 的共識項為 $(AD)(DE') = ADE'$。
- 複合化簡實例：
  $$A'B' + AC + BC' + B'C + AB = A'B' + AC + BC'$$

---

## 4. 共識定理的對偶形式 (Dual Form)
根據對偶原理，將 AND 換為 OR、OR 換為 AND：
$$(X + Y)(X' + Z)(Y + Z) = (X + Y)(X' + Z)$$
在 POS (和之積) 中，求和項 $(Y + Z)$ 亦可直接被剔除。

---

## 5. 反向應用：主動加入共識項以突破化簡瓶頸
有時表達式看起來無法再化簡，但藉由**刻意補入一個共識項（Adding Redundant Consensus Term）**，能創造出新的因式提取機會，進而消除其他更大的項：
- 範例：
  $$WX + XY + X'Z' + WY'Z'$$
  觀察 $XY$ 與 $X'Z'$，其共識項為 $YZ'$；但若觀察 $WX$ 與 $X'Z'$，其共識項為 $WZ'$。
  刻意加入共識項 $WZ'$：
  $$= WX + XY + X'Z' + WY'Z' + WZ'$$
  此時 $WZ'$ 與 $WY'Z'$ 結合（$WZ'(1 + Y') = WZ'$），直接消除了 $WY'Z'$！
  最後 $WZ'$ 又被 $WX$ 與 $X'Z'$ 吸收消除，最終化簡為乾淨的：
  $$WX + XY + X'Z'$$

## 關聯頁面
- [[boolean-laws-and-theorems]]
- [[algebraic-simplification-techniques]]
- [[summary-c02b-laws-and-theorems]]
- [[summary-c03b-algebraic-simplification-and-proofs]]
