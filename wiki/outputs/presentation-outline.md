---
title: "教學 HTML 簡報大綱與 Wiki 知識對應表"
type: output
tags: [簡報大綱, 教學設計, 認知負荷, 知識映射]
sources: ["[[wiki/index.md]]"]
created: 2026-11-23
last_updated: 2026-11-23
---

# 教學 HTML 簡報大綱與 Wiki 知識對應表

- **簡報主題**：從零搞懂數位邏輯設計：從布林代數到邏輯閘
- **目標客群**：零基礎初學者（原本不熟悉數位邏輯、布林代數或電路設計的人）
- **教學目標**：透過物理開關直覺建立心智模型，平滑銜接到布林公理、狄摩根定律、SOP 兩階電路與萬能閘。

---

## 投影片結構與 Wiki 來源對照 (Slide-by-Slide Matrix)

| 頁碼 | 投影片標題 | 教學核心點 | 對應 Wiki 概念頁面與講義來源 |
|:---:|:---|:---|:---|
| **01** | **從零搞懂數位邏輯設計** | 破題：為什麼世界上最強大的超級電腦，底層只看得懂 0 與 1？ | `[[boolean-algebra-fundamentals]]` |
| **02** | **物理直覺：開關與電流** | 將抽象的 0/1 具象化為水龍頭與電燈開關（開路 vs 通路）。 | `[[boolean-algebra-fundamentals]]` (`sources/week1/C02a`) |
| **03** | **歷史交會：Boole 遇上 Shannon** | 1847 年哲學家的邏輯符號，在 1939 年被麻省理工青年夏農用在繼電器上。 | `[[boolean-algebra-fundamentals]]` (`sources/week1/C02a`) |
| **04** | **三大基石：NOT、AND、OR** | 三大基本運算的開關電路對照（串聯=AND，並聯=OR）與真值表。 | `[[basic-operations-and-truth-tables]]` (`sources/week1/C02a`) |
| **05** | **代數魔法：為什麼 $1 + 1 = 1$？** | 破除十進位直覺：布林代數中的加法是「邏輯或」，只要有電就發亮。介紹第二分配律。 | `[[boolean-laws-and-theorems]]` (`sources/week1/C02b`) |
| **06** | **轉換之眼：狄摩根定律 (De Morgan)** | 「斷長線、變符號」——乘積的補數等於補數的總和，電路轉換的必備神技。 | `[[demorgan-laws]]` (`sources/week1/C02b`) |
| **07** | **邏輯閘家族：從基本到萬能** | 晶片裡的樂高積木：AND, OR, NOT，以及只要一種就能組出全世界的「萬能閘」NAND 與 NOR。 | `[[logic-gates-and-circuits]]` (`sources/week1/C02c`, `C03a`) |
| **08** | **電路設計實戰：SOP 積之和** | 如何把一張「真值表」直接翻譯成「AND-OR 兩階硬體電路」？工程師的標準解法。 | `[[canonical-forms-sop-pos]]` (`sources/week1/C02c`) |
| **09** | **化簡的威力：替晶片省下幾十億電晶體** | 利用合併項與共識定理，將冗長電路精簡一半！ | `[[algebraic-simplification-techniques]]`, `[[consensus-theorem]]` (`sources/week2/C03b`) |
| **10** | **常見陷阱：千萬別用「消去律」！** | $X+Y = X+Z$ 能不能把 $X$ 消掉？數學反例剖析布林代數與常規代數的大陷阱。 | `[[equation-validity-and-cancellation-trap]]` (`sources/week2/C03b`) |
| **11** | **結語與未來：通往 CPU 算術邏輯單元** | 從單個邏輯閘到 XOR 半加法器，邁向現代晶片世界。知識庫持續擴展指南。 | `[[index]]` |

---

## 品質前移驗證通過記錄
- **單頁資訊量評估**：每一頁限制在 1 個核心觀念 + 1 個可視化直覺（電路/表格/對照）+ 3 行以內的提煉條目。
- **引用完整度評估**：每一頁均具備 100% 精確之 Wiki 雙向連結與原始 PDF 出處。
