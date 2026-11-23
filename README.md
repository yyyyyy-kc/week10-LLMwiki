# LLM Wiki & 教學 HTML 簡報專案 (w10_wikiLLM)

本專案參考 Andrej Karpathy 的 **LLM Wiki** 模式建立，以《數位邏輯設計：從布林代數到邏輯閘》為主題，透過 LLM Agent 攝取 5 份核心教材，編譯為高度結構化、具備雙向鏈接的 Markdown 知識庫，並自動生成可互動瀏覽的現代教學 HTML 簡報。

---

## 快速預覽與成果

- **教學 HTML 簡報**：直接在瀏覽器雙擊開啟根目錄下的 [presentation.html](file:///Users/samyin/Desktop/w10_wikiLLM/presentation.html)
  - 支援鍵盤左右箭頭翻頁、全螢幕 (`F`)、全覽目錄 (`O`)、講者註記 (`S`)、深淺色主題與互動開關模擬器！
- **作業繳交報告完整版**：查看 [SUBMISSION.md](file:///Users/samyin/Desktop/w10_wikiLLM/SUBMISSION.md)
- **Agent 規範守則 (The Schema)**：查看 [AGENT.md](file:///Users/samyin/Desktop/w10_wikiLLM/AGENT.md)
- **Wiki 知識庫總導覽**：查看 [wiki/index.md](file:///Users/samyin/Desktop/w10_wikiLLM/wiki/index.md)
- **Wiki 操作日誌**：查看 [wiki/log.md](file:///Users/samyin/Desktop/w10_wikiLLM/wiki/log.md)

---

## 專案結構

```text
w10_wikiLLM/
├── AGENT.md                 # Agent 操作手冊與工作流定義 (The Schema)
├── presentation.html        # 獨立可瀏覽的教學 HTML 簡報 (零依賴單檔)
├── README.md                # 本說明文件
├── sources/                 # 不可變原始材料 (不可修改來源層)
│   ├── week1/               # C02a, C02b, C02c (布林代數基礎、公理與邏輯閘)
│   ├── week2/               # C03a, C03b (因式分解、代數化簡與等式驗證)
│   ├── week3/               # C04b, C04c
│   └── week4/               # C05a, C05b
└── wiki/                    # LLM 完全維護的持久 Wiki 知識庫
    ├── index.md             # 知識地圖與全站索引
    ├── log.md               # 追加式時間軸操作日誌
    ├── concepts/            # 9 篇原子化核心概念頁
    ├── summaries/           # 5 篇講義深度總結導讀
    └── outputs/             # 簡報大綱與生成產物
```
