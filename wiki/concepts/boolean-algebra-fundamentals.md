---
title: 布林代數基礎概念 (Boolean Algebra Fundamentals)
type: concept
tags: [布林代數, 歷史, 夏農, 開關代數, 二值邏輯]
sources: ["[[sources/week1/20260910_SCLD_C02a.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 布林代數基礎概念 (Boolean Algebra Fundamentals)

## 1. 什麼是布林代數？
**布林代數 (Boolean Algebra)**，又稱**開關代數 (Switching Algebra)**，是專門處理只有兩種真假狀態（二值）的數學代數系統。

- **變數定義**：布林變數 $X \in \{0, 1\}$。
- **無數值含義**：在傳統算術中，數字具有大小與數量意義（例如 $1 + 1 = 2$）；然而在布林代數中，「0」與「1」僅是代表不同邏輯狀態的抽象符號：
  - `0`：開路 (Open)、低電位 (Low)、假 (False)、關閉 (OFF)
  - `1`：閉路 (Closed)、高電位 (High)、真 (True)、開啟 (ON)

## 2. 歷史的交會：從哲學邏輯到電晶體革命
- **1847 年，喬治·布爾 (George Boole)**：
  - 英國數學家與哲學家，在著作《An Investigation of the Laws of Thought》中首次提出將形式邏輯命題以代數符號系統表達，開創了現代符號邏輯。
- **1939 年，克勞德·夏農 (Claude Shannon)**：
  - 資訊理論之父。他在麻省理工學院 (MIT) 的碩士論文《A Symbolic Analysis of Relay and Switching Circuits》中，天才般地發現布林代數可以精確描述繼電器（Relays）與開關組成的電氣迴路。
  - 這一發現直接奠定了現代所有電腦中央處理器 (CPU) 與數位晶片的理論架構。

## 3. 開關模型 (Switching Model)
夏農建立了開關與代數運算之間的對應關係：
- **常開開關 (Normally Open)**：未受激發時為 0（斷路）；受激發時為 1（通路）。
- **常閉開關 (Normally Closed)**：未受激發時為 1（通路）；受激發時為 0（斷路），對應**反相 (NOT)**。
- **串聯電路 (Series Circuit)**：電流必須同時流經兩者方能導通，等價於 **AND (邏輯乘法)**。
- **並聯電路 (Parallel Circuit)**：電流只要流經任一通路即可導通，等價於 **OR (邏輯加法)**。

## 關聯頁面
- [[basic-operations-and-truth-tables]]
- [[boolean-laws-and-theorems]]
- [[logic-gates-and-circuits]]
- [[summary-c02a-intro-and-basic-operations]]
