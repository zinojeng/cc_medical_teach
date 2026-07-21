# 把 Claude Code 變成你的第二大腦（醫學生版）

改編自「聯發科教育基金會 Claude Code 工作坊」，將工作坊內容重新設計為醫學生適用的教學素材。

## 內容

| 檔案 | 說明 |
|---|---|
| [`deck/index.html`](deck/index.html) | **HTML 簡報（18 頁）**——下載後用瀏覽器打開，← / → 鍵翻頁、P 鍵列印成 PDF |
| [`claude-code-second-brain-slides-parsed.md`](claude-code-second-brain-slides-parsed.md) | 原工作坊 118 頁簡報的逐段解析＋醫學生版完整改編（CLAUDE.md 範本、四個 Skill、安全紅線、第一週路線圖） |
| [`slides-raw-notes-118.txt`](slides-raw-notes-118.txt) | 原簡報 118 頁講者備註原文 |

## 觀看簡報

```bash
git clone https://github.com/zinojeng/cc_medical_teach.git
open cc_medical_teach/deck/index.html
```

或啟用 GitHub Pages（Settings → Pages → main branch）後直接以 `https://zinojeng.github.io/cc_medical_teach/deck/` 播放。

## 簡報目錄

1. 封面
2. 顧問 vs 助手——為什麼是 Agent
3. Agent＝模型＋Harness
4. 根據你的資料回答（可驗證性）
5. med-brain 資料夾架構
6. LLM Wiki 模式——讓 AI 幫你「編譯」知識（[Karpathy 原文](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)）
7. 三層架構 × 三個日常操作（Raw sources / Wiki / Schema；Ingest / Query / Lint）
8. CLAUDE.md——給 AI 的說明書
9. 醫學情境的四條安全紅線
10. Context 不是無限的
11. SKILL.md 解剖
12. 醫學生的四個必備 Skill
13. 醫療是 Skill 回報最大的領域（SkillsBench +51.9）
14. 了解你的未知（四象限）
15. 查房前的盲點掃描
16. 第一週上手路線圖
17. 備份 vs 第二大腦
18. 結語：工具只是入門，系統與流程才重要
