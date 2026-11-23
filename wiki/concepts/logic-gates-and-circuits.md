---
title: 邏輯閘與電路實現 (Logic Gates and Circuit Realization)
type: concept
tags: [邏輯閘, AND, OR, NOT, NAND, NOR, XOR, XNOR]
sources: ["[[sources/week1/20260910_SCLD_C02a.pdf]]", "[[sources/week1/20260910_SCLD_C02c.pdf]]", "[[sources/week2/20260917_SCLD_C03a.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 邏輯閘與電路實現 (Logic Gates and Circuit Realization)

**邏輯閘 (Logic Gates)** 是數位電腦硬體的最小物理運算單元。每個邏輯閘都是一個將連續電壓訊號（如 0V 與 3.3V/5V）抽象為離散 0 與 1 的電子開關網絡（由 MOSFET 電晶體構成）。

---

## 1. 基本邏輯閘 (Primary Gates)

### 1.1 反相器 (Inverter / NOT Gate)
- **符號**：三角形加前端小圓圈（Bubble，代表反相）。
- **邏輯式**：$F = X'$
- **行為**：輸入 0 輸出 1，輸入 1 輸出 0。

### 1.2 及閘 (AND Gate)
- **符號**：直背、圓弧頭的 D 型符號。
- **邏輯式**：$F = A \cdot B$
- **行為**：所有輸入皆為 1 時輸出 1。

### 1.3 或閘 (OR Gate)
- **符號**：凹背、尖頭弧形符號。
- **邏輯式**：$F = A + B$
- **行為**：任一輸入為 1 時輸出 1。

---

## 2. 萬能邏輯閘 (Universal Gates)

### 2.1 反及閘 (NAND Gate)
- **符號**：AND 閘前端加上代表反相的小圓圈。
- **邏輯式**：$F = (A \cdot B)'$
- **真值表**：僅當所有輸入皆為 1 時輸出 0；其餘情況輸出皆為 1。

### 2.2 反或閘 (NOR Gate)
- **符號**：OR 閘前端加上代表反相的小圓圈。
- **邏輯式**：$F = (A + B)'$
- **真值表**：僅當所有輸入皆為 0 時輸出 1；其餘情況輸出皆為 0。

> **為什麼被稱為萬能？**
> 任何複雜的數位電路（包括算術加法器、微處理器、暫存器）都可以**百分之百只用 NAND 閘**或**百分之百只用 NOR 閘**搭建完成。

---

## 3. 算術核心閘：XOR 與 XNOR

### 3.1 互斥或閘 (Exclusive-OR / XOR Gate)
- **符號**：OR 閘後方再加一道弧線。
- **邏輯式**：$F = A \oplus B = A'B + AB'$
- **行為**：**相異為 1，相同為 0**。
- **代數特徵**：
  - $X \oplus 0 = X$
  - $X \oplus 1 = X'$（可充當受控反相器！）
  - $X \oplus X = 0$
  - $X \oplus X' = 1$
- **應用場景**：半加法器（Half-Adder）的求和項（Sum）、奇偶同位檢查碼（Parity Check）。

### 3.2 同位 / 反互斥或閘 (Equivalence / XNOR Gate)
- **符號**：XOR 閘前端加上反相圓圈。
- **邏輯式**：$F = (A \oplus B)' = AB + A'B'$
- **行為**：**相同為 1，相異為 0**（又稱比較器 Comparator）。

---

## 4. 邏輯閘的層級與傳遞延遲 (Propagation Delay)
- 兩階邏輯（SOP 的 AND-OR，或 POS 的 OR-AND）具有最快的訊號傳遞速度（僅經歷 2 個 Gate Delays）。
- 但當輸入腳位過多（Fan-in 限制）時，必須拆解為多階電路（Multi-level circuits），這是在電路面積、晶片接腳數與反應延遲之間的經典工程取捨。

## 關聯頁面
- [[basic-operations-and-truth-tables]]
- [[demorgan-laws]]
- [[canonical-forms-sop-pos]]
- [[summary-c02c-sop-pos-and-logic-gates]]
