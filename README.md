# 把 Claude Code 變成你的第二大腦（醫學生版）

改編自「聯發科教育基金會 Claude Code 工作坊」，將工作坊內容重新設計為醫學生適用的教學素材。

## 內容

| 檔案 | 說明 |
|---|---|
| [`deck/index.html`](deck/index.html) | **HTML 簡報（22 頁）**——下載後用瀏覽器打開，← / → 鍵翻頁、P 鍵列印成 PDF |
| [`claude-code-second-brain-slides-parsed.md`](claude-code-second-brain-slides-parsed.md) | 原工作坊 118 頁簡報的逐段解析＋醫學生版完整改編（CLAUDE.md 範本、四個 Skill、安全紅線、第一週路線圖） |
| [`slides-raw-notes-118.txt`](slides-raw-notes-118.txt) | 原簡報 118 頁講者備註原文 |

## 線上觀看

**簡報：https://zinojeng.github.io/cc_medical_teach/deck/**

或在本機開啟：

```bash
git clone https://github.com/zinojeng/cc_medical_teach.git
open cc_medical_teach/deck/index.html
```

## 簡報目錄

**為什麼是 Agent**

1. 封面
2. 顧問 vs 助手——網頁版 AI 與 Agent 的差別
3. Agent＝模型＋Harness（Prompt → Context → Harness Engineering）
4. 根據「你的資料」回答——可驗證性

**打地基**

5. med-brain 資料夾架構
6. LLM Wiki 模式——讓 AI 幫你「編譯」知識
7. 三層架構 × 三操作（Raw / Wiki / Schema；Ingest / Query / Lint）
8. 何時用 LLM Wiki vs RAG＋醫學 wiki 目錄結構＋幻覺擴散風險
9. 醫學文獻搜尋 → Wiki 的六步工作流
10. CLAUDE.md——給 AI 的說明書
11. 醫學情境的四條安全紅線
12. Context 不是無限的（`/context`、`/clear`、`/rewind`、subagent）

**多 Agent 協作**

13. 八個專科 Agent 組成的研究產線
14. Systematic Review 的九站流水線——每站的輸入輸出契約

**Skill**

15. SKILL.md 解剖（frontmatter × 內容）
16. 醫學生的四個必備 Skill
17. 醫療是 Skill 回報最大的領域（SkillsBench +51.9 vs 軟體 +4.5）

**臨床後設認知與收尾**

18. 了解你的未知（四象限）
19. 查房前的盲點掃描
20. 第一週上手路線圖
21. 備份 vs 第二大腦
22. 結語：工具只是入門，系統與流程才重要

## 參考來源

- [Andrej Karpathy — LLM Wiki（原始 gist）](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- [Kenming — Karpathy LLM Wiki 知識系統實踐：基礎安裝與建置篇](https://kenming.idv.tw/karpathy-llm-wiki-fundamental/)
- [Andrej Karpathy's LLM Wiki: Create your own knowledge base（Medium）](https://medium.com/@urvvil08/andrej-karpathys-llm-wiki-create-your-own-knowledge-base-8779014accd5)
- [zinojeng/academic-research-agents](https://github.com/zinojeng/academic-research-agents) — 八個學術研究 Agent 與 systematic review／meta-analysis 工作流範本
- SkillsBench (arXiv:2602.12670) — 各領域 Skill 提升幅度實證
