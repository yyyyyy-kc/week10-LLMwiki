---
title: 標準形式：SOP 與 POS (Canonical and Standard Forms: SOP & POS)
type: concept
tags: [數位邏輯設計, SOP, POS, 積之和, 和之積, 電路實現]
sources: ["[[sources/week1/20260910_SCLD_C02c.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 標準形式：SOP 與 POS (Canonical and Standard Forms: SOP & POS)

在數位邏輯設計中，任何布林函數都可以標準化為兩種基本的二階（Two-level）代數形式：**積之和 (SOP)** 與 **和之積 (POS)**。

---

## 1. 積之和 (Sum-of-Products, SOP)

### 1.1 定義
- 表達式是若干個**乘積項 (Product terms)** 的邏輯加總（OR）。
- 每個乘積項由單一變數或其補數透過 AND 運算組合而成。
- **範例**：
  - 標準 SOP：$F = AB' + CD'E + AC'E'$
  - 退化情況 (Degenerate cases)：$ABC' + DEFG + H$ 亦屬 SOP。
- **反例**：$(A + B)CD + EF$ 不是 SOP，因為第一項包含求和項 $(A + B)$。

### 1.2 硬體實現：AND-OR 兩階電路
SOP 表達式可以直接一對一映射到硬體線路上：
1. **第一階**：一組並行的 AND 閘，每個 AND 閘各自計算一個乘積項。
2. **第二階**：單一個多輸入的 OR 閘，將所有 AND 閘的輸出匯整輸出。

---

## 2. 和之積 (Product-of-Sums, POS)

### 2.1 定義
- 表達式是若干個**求和項 (Sum terms)** 的邏輯相乘（AND）。
- 每個求和項由單一變數或其補數透過 OR 運算組合而成。
- **範例**：
  - 標準 POS：$F = (A + B')(C + D' + E)(A + C' + E')$
  - 退化情況：$(A + B)(C + D + E)F$ 亦屬 POS。
- **反例**：$(A + B)(C + D) + EF$ 不是 POS，因為最後有加法項。

### 2.2 硬體實現：OR-AND 兩階電路
1. **第一階**：一組並行的 OR 閘，各自計算一個求和項。
2. **第二階**：單一個多輸入的 AND 閘，將所有 OR 閘的輸出做乘積。

---

## 3. SOP 與 POS 的對照與工程權衡

| 特性比較 | 積之和 (SOP) | 和之積 (POS) |
|:---|:---|:---|
| **基本結構** | 乘積之和（$AND \rightarrow OR$） | 和之乘積（$OR \rightarrow AND$） |
| **典型兩階閘** | AND-OR 電路 | OR-AND 電路 |
| **反相萬能轉換** | 自然對應 **NAND-NAND** 電路 | 自然對應 **NOR-NOR** 電路 |
| **真值表依據** | 鎖定輸出為 **1** 的輸入組合（Minterms 最小項） | 鎖定輸出為 **0** 的輸入組合（Maxterms 最大項） |

## 4. 展開與因式分解實用技巧
- **POS 轉 SOP (展開)**：
  優先套用第二分配律 $(X + Y)(X + Z) = X + YZ$，可跳過冗長的中間項交叉相乘。
- **SOP 轉 POS (因式分解)**：
  利用 $X + YZ = (X + Y)(X + Z)$ 或 $(X + Y)(X' + Z) = XZ + X'Y$。
  - 例：$A + B'CD = (A + B')(A + C)(A + D)$。

## 關聯頁面
- [[basic-operations-and-truth-tables]]
- [[logic-gates-and-circuits]]
- [[demorgan-laws]]
- [[summary-c02c-sop-pos-and-logic-gates]]
