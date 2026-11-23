---
title: 布林代數定律與定理 (Boolean Laws and Theorems)
type: concept
tags: [布林代數, 公理, 交換律, 結合律, 分配律, 等冪律]
sources: ["[[sources/week1/20260910_SCLD_C02a.pdf]]", "[[sources/week1/20260910_SCLD_C02b.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 布林代數定律與定理 (Boolean Laws and Theorems)

布林代數擁有自身嚴謹的公理與定理系統，部分與一般實數代數相同，但也有若干**僅成立於布林代數中**的強大規律。

---

## 1. 基礎定理與單位元素
- **常數 0 與 1 的運算**：
  - $X + 0 = X$（0 為 OR 運算的單位元素）
  - $X + 1 = 1$（1 為 OR 運算的吸收元素 / 飽和）
  - $X \cdot 1 = X$（1 為 AND 運算的單位元素）
  - $X \cdot 0 = 0$（0 為 AND 運算的吸收元素 / 飽和）
- **等冪律 (Idempotent Laws)**：
  - $X + X = X$
  - $X \cdot X = X$
- **雙重否定律 / 對合律 (Involution Law)**：
  - $(X')' = X$
- **互補律 (Laws of Complementarity)**：
  - $X + X' = 1$
  - $X \cdot X' = 0$

---

## 2. 經典代數三律

### 2.1 交換律 (Commutative Laws)
$$XY = YX, \quad X + Y = Y + X$$

### 2.2 結合律 (Associative Laws)
$$(XY)Z = X(YZ) = XYZ$$
$$(X + Y) + Z = X + (Y + Z) = X + Y + Z$$
*電路意涵：此定律保證了多輸入 AND 閘與 OR 閘的電氣等效性。*

### 2.3 分配律 (Distributive Laws)
- **第一分配律（AND 對 OR 分配，同一般代數）**：
  $$X(Y + Z) = XY + XZ$$
- **第二分配律（OR 對 AND 分配，布林代數專有）**：
  $$X + YZ = (X + Y)(X + Z)$$
  **證明步驟**：
  右式展開：
  $$(X + Y)(X + Z) = XX + XZ + YX + YZ = X + XZ + XY + YZ$$
  提取公因式 $X$：
  $$= X(1 + Z + Y) + YZ = X(1) + YZ = X + YZ \quad \text{Q.E.D.}$$

---

## 3. 進階因式分解定理 (Multiplying Out and Factoring Theorem)
在處理不同標準式轉換時極度實用的雙向定理：
$$(X + Y)(X' + Z) = XZ + X'Y$$
- **由左至右**：將 POS (和之積) 展開為 SOP (積之和)。
- **由右至左**：將 SOP 快速因式分解為 POS。
- **直覺驗證**：若 $X=1$，左式為 $(1+Y)(0+Z)=Z$，右式為 $1\cdot Z + 0\cdot Y = Z$；若 $X=0$，左式為 $(0+Y)(1+Z)=Y$，右式為 $0\cdot Z + 1\cdot Y = Y$。兩者必然相等。

## 關聯頁面
- [[basic-operations-and-truth-tables]]
- [[demorgan-laws]]
- [[consensus-theorem]]
- [[algebraic-simplification-techniques]]
