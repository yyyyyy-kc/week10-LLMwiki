---
title: "講義摘要：Boolean Algebra (3) - 標準式、邏輯閘與複合電路"
type: summary
tags: [數位邏輯設計, 布林代數, SOP, POS, 邏輯閘, XOR, XNOR, NAND, NOR]
sources: ["[[sources/week1/20260910_SCLD_C02c.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 講義摘要：Boolean Algebra (3) - 標準式、邏輯閘與複合電路

本單元源自 Charles H. Roth & Larry L. Kinney 之《Fundamentals of Logic Design》第 2 章第 3 部分，重點探討表達式的標準化展開（SOP 與 POS）、電路直接映射以及複合邏輯閘（XOR, XNOR, NAND, NOR）。

## 1. 積之和 (SOP) 與 和之積 (POS)
- **積之和式 (Sum-of-Product, SOP)**：
  - 定義：所有的乘積項（Product terms）皆由單一變數（或其補數）相乘構成，最後將這些乘積項相加。
  - 範例：$AB' + CD'E + AC'E'$。
  - 電路實現：**兩層電路架構**，前級由多個 AND 閘接收輸入，輸出全部匯入後級單一 OR 閘（AND-OR 結構）。
- **和之積式 (Product-of-Sum, POS)**：
  - 定義：所有的求和項（Sum terms）皆由單一變數（或其補數）相加構成，最後將這些求和項相乘。
  - 範例：$(A + B')(C + D' + E)(A + C' + E')$。
  - 電路實現：前級多個 OR 閘匯入後級單一 AND 閘（OR-AND 結構）。
- **展開與因式分解 (Multiplying Out and Factoring)**：
  - 展開時優先應用第二分配律 $(X + Y)(X + Z) = X + YZ$ 可大幅加快展開速度。
  - 因式分解時亦可藉由提取公因項或第二分配律快速將 SOP 轉為 POS。

## 2. 互斥或 (Exclusive-OR, XOR)
- **定義與符號**：
  - $0 \oplus 0 = 0$
  - $0 \oplus 1 = 1$
  - $1 \oplus 0 = 1$
  - $1 \oplus 1 = 0$
- **表達式**：$X \oplus Y = X'Y + XY'$
- **實務重要性**：電腦算術運算（加法器 Adder、同位檢查器 Parity Checker）的核心基礎。
- **重要定理**：
  - $X \oplus 0 = X$
  - $X \oplus 1 = X'$
  - $X \oplus X = 0$
  - $X \oplus X' = 1$
  - 滿足交換律與結合律：$(X \oplus Y) \oplus Z = X \oplus (Y \oplus Z) = X \oplus Y \oplus Z$。

## 3. 同位與等價閘 (Equivalence / XNOR)
- **定義與真值表**：
  - $X \equiv Y$ 或 $(X \oplus Y)'$：兩者輸入相同時輸出為 1，相異時輸出為 0。
  - 表達式：$X \equiv Y = XY + X'Y'$。
  - 又稱為 Exclusive-NOR (XNOR) 閘。

## 4. 萬能邏輯閘 (Universal Gates: NAND & NOR)
- **NOR 閘**：$(A + B + \dots + N)'$（OR 輸出反相）。
- **NAND 閘**：$(A \cdot B \cdot \dots \cdot N)'$（AND 輸出反相）。
- **特點**：根據狄摩根定律，僅使用 NAND 閘或僅使用 NOR 閘即可完整組裝出 NOT、AND、OR 等任何數位邏輯電路。

## 關聯概念頁面
- [[canonical-forms-sop-pos]]
- [[logic-gates-and-circuits]]
- [[demorgan-laws]]
