---
title: "講義摘要：Boolean Algebra (Continued) (2) - 開關表達式化簡與等式驗證"
type: summary
tags: [數位邏輯設計, 布林代數, 代數化簡, 冗餘項, 等式驗證, 消去律陷阱]
sources: ["[[sources/week2/20260917_SCLD_C03b.pdf]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 講義摘要：Boolean Algebra (Continued) (2) - 開關表達式化簡與等式驗證

本單元源自 Charles H. Roth & Larry L. Kinney 之《Fundamentals of Logic Design》第 3 章第 2 部分，著重探討如何透過代數操作精簡邏輯閘成本，以及如何嚴謹驗證布林等式，特別警示傳統代數觀念中「消去律」的危險陷阱。

## 1. 邏輯式化簡的三大基本手法
化簡布林表達式可直接降低硬體實作時邏輯閘與輸入腳位的成本：
1. **合併項 (Combining terms)**：
   - 利用 $XY + XY' = X$
   - 例如：$ABC'D' + ABCD' = ABD'$。
   - 利用 $X + X = X$ 複製項目後與其他項目分別配對。
2. **消除項 (Eliminating terms)**：
   - 利用吸收律 $X + XY = X$
   - 利用共識定理 $XY + X'Z + YZ = XY + X'Z$
3. **消除文字 (Eliminating literals)**：
   - 利用 $X + X'Y = X + Y$
   - 範例：$A'B + A'B'C'D' + ABCD' = A'(B + C'D') + ABCD' = A'B + BCD' + A'C'D'$。

## 2. 引入冗餘項以突破化簡瓶頸 (Adding Redundant Terms)
- 透過前三種基本手法處理後，表達式不一定達到最小項數或最少文字數。
- 進階技巧：**人為加入冗餘項（Redundant terms）**以觸發進一步化簡：
  - 加上 $XX' = 0$
  - 乘以 $(X + X') = 1$
  - 人為添加共識項 $YZ$ 至 $XY + X'Z$ 中
  - 範例：$WX + XY + X'Z' + WY'Z'$ 透過加入 $WZ'$ 共識項後，成功消除其他非必要項，最終化簡為 $WX + XY + X'Z'$。

## 3. 證明布林等式有效性的方法 (Proving Validity of an Equation)
若需證明等式 $f(X_1, \dots, X_n) = g(X_1, \dots, X_n)$ 成立：
1. **建構真值表 (Truth Table)**：雖然嚴格可靠，但變數增加時極為繁瑣（$2^n$ 列）。
2. **單邊代數操作**：推導一側使其等於另一側。
3. **雙邊化簡至標準式**：將左右兩側均化簡為相同的 SOP 或 POS。
4. **雙邊進行可逆操作 (Reversible operations)**：
   - 可以在兩邊同時做補數運算（因補數具雙向一對一對應）。
   - **反例警告：在兩邊同時乘或加相同變數不可用於證明！**（因乘與加不可逆，即使推導出相等亦無法回溯證明原式成立）。
5. **反證無效性**：只要找到一組輸入使得左式 $\neq$ 右式，即可立刻斷言等式不成立。

## 4. 關鍵陷阱：布林代數不成立「消去律」 (Cancellation Rule Failure)
- **錯誤範例 1**：若 $X + Y = X + Z$，則推論 $Y = Z$？（**錯誤！**）
  - 反例：令 $X = 1, Y = 0, Z = 1$，則 $1 + 0 = 1 + 1$（$1 = 1$ 成立），但 $Y \neq Z$（$0 \neq 1$）。
- **錯誤範例 2**：若 $XY = XZ$，則推論 $Y = Z$？（**錯誤！**）
  - 反例：令 $X = 0, Y = 0, Z = 1$，則 $0 \cdot 0 = 0 \cdot 1$（$0 = 0$ 成立），但 $Y \neq Z$（$0 \neq 1$）。

## 關聯概念頁面
- [[algebraic-simplification-techniques]]
- [[equation-validity-and-cancellation-trap]]
- [[consensus-theorem]]
- [[boolean-laws-and-theorems]]
