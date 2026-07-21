# 把 Claude Code 變成你的第二大腦 — 簡報解析

> 來源：聯發科教育基金會 Claude Code 工作坊（Google Slides，共 118 張）
> 原始對象：中小學教師｜本文件另附「醫學生版」改編（見第二部分）

---

## 第一部分：逐段簡報解析

> 118 張投影片中約有一半是純視覺／示範畫面（無講者備註），以下依工作坊敘事弧線分成 12 個段落，逐張列出有內容的投影片。

### 段落 A｜開場與心法（Slide 1–3）

**Slide 1（封面）**
- 核心訊息：今天不是只學會 Claude Code，而是建立一個「跟 AI 一起成長的系統與 mindset」。
- 附 Windows 一鍵安裝指令：
  ```powershell
  irm https://gist.githubusercontent.com/oberonlai/61ef05497999adc560600fceaabfe2b8/raw/install-claude-code-windows.ps1 | iex
  ```

**Slide 2（工作坊定位）**
- 大多數人已會用 ChatGPT / Gemini / Claude App，但每次都要「重新打開 AI、重新說明背景、重新貼資料、重新修改格式」→ AI 省了一點時間，卻沒有改變工作流。
- 核心提問：能不能把腦中珍貴但難以說清楚的**專業判斷**，整理成一套可重複運作的 AI 工作流？
- Claude Code 在終端機操作看似可怕，但它能讓人看清 Agent 的本質：**讀取資料、使用工具、修改檔案、檢查結果、反覆執行流程**。
- 教學法：每 10 分鐘一個小成功 → Agent 概念 → CLAUDE.md → Skill → subagent / loop。
- 最終成果不是記住功能，而是能想像「我工作裡哪件事可以變成工作流」。

**Slide 3（為什麼用實作教）**
- 若一開始就直接建好第二大腦系統，學員會不知道資料夾、CLAUDE.md、Skill 如何運作與連接 → 必須透過實作逐步理解系統架構。

### 段落 B｜什麼是 Agent？什麼是 Harness？（Slide 4–13）

**Slide 5**：拋問「這是 Agent 嗎？」（互動判斷題）

**Slide 7（Harness Engineering — 本簡報的理論核心）**
- **Harness = 模型之外的一切**：System Prompt、Tools、基礎設施、協調邏輯、中間層。
- 模型本身不是 Agent；當 Harness 為它提供「狀態、工具執行、回饋迴圈、可強制執行的限制」時，才成為 Agent。
- Claude Code、Cowork 都是 Harness。
- 演進三部曲：
  1. **Prompt Engineering** — 怎麼把問題問好
  2. **Context Engineering** — 提供 AI 什麼樣的資訊
  3. **Harness Engineering** — 建構 AI 在什麼樣的環境運作（用軟體工程的驗證機制包住 LLM，降低隨機性）

**Slide 8**：網頁版 AI 像「顧問」——他出嘴你動手；Agent 像「助手」——能完成你交辦的事情。

**Slide 9**：Claude Code 會根據**你的資料**回答問題，而不是網路或訓練資料。

### 段落 C｜Claude Code vs 網頁版（Slide 14–20）

**Slide 14**
- 網頁版只能一問一答，無法主動改變資料；Claude Code 像同事：瀏覽資料夾、讀規則、建立／修改檔案、連接更多 App。
- 學員動作：說出過去用聊天 AI 最常卡住的地方。

**Slide 16–19（知識工作者的價值主張）**
- Claude Code 的價值**不只是寫程式**，而是處理「結構化文字工作」：文章、教案、摘要、會議記錄、簡報腳本、專案資料。

### 段落 D｜安裝與環境（Slide 21–28）

**Slide 21**：安裝是最難的第一步，卡住就舉手；小心假冒的詐騙安裝網站。
**Slide 22**：Claude Code 最好搭配 IDE（如 VS Code）使用，才看得到檔案怎麼被變更。
**Slide 25**：**工作目錄原則**——在哪個資料夾啟動，就在那個資料夾內工作。

### 段落 E｜第一次動手（Slide 29–36）

**Slide 34**：進階挑戰——讓 Claude Code 做出「可上傳資料分析」或「抽籤網頁」的小程式。
**Slide 35**：重點是熟悉手感。學員動作：引用（@）一個檔案，請 Claude Code 解釋它。

### 段落 F｜Context 管理（Slide 37–47）

**Slide 37（context 不是無限的）**
- AI 不是無限記憶，**context 用到約 40–60% 就開始錯亂**。
- 學員動作：執行 `/context` 觀察使用情況。
- 伏筆提問：快到臨界點該怎麼辦？

**Slide 40**：什麼是 Context（概念鋪陳）。
**Slide 42**：`/init` — 依現有資料夾結構生成 CLAUDE.md，讓 AI 知道這個資料夾的用途。
**Slide 43**：`/clear` — 對話太長、任務換方向、AI 開始混亂時重新開始。
**Slide 45**：`/rewind` — 狀況不對時回到上一步（類似 Word 的復原）。

### 段落 G｜Markdown 與 CLAUDE.md（Slide 48–60）

**Slide 48**：為什麼用 Markdown——純文字、易保存、易搜尋、可版本控制、AI 容易理解。
**Slide 49**：**LLM 是無狀態的**，所以需要用檔案告訴它現在要做什麼。
**Slide 56–58**：CLAUDE.md = 給 AI 的說明書。「如果沒有說明書，AI 只能猜你的偏好和規則。」

### 段落 H｜Subagent（Slide 61–71）

**Slide 61**：每個 session 有 context 限制 → 用 subagent 解決（各自有獨立 context），代價是比較貴（token 消耗高）。

### 段落 I｜Skill（Slide 72–79）

**Slide 72**：範例：Anthropic 官方 k12 教師 Skill
`https://github.com/anthropics/k12-teacher-skills/tree/main/plugin/skills/k12-lesson-planning`

**Slide 74（SKILL.md 結構）**
- **frontmatter**：告訴 Claude *何時*使用這個 Skill。
- **markdown 內容**：告訴 Claude 使用時要*遵守什麼*。
- 學員動作：選一個常重複的任務，拆成 frontmatter + 參考內容。

**Slide 75–76（Skill 的節制）**
- 太多 Skill 反而讓系統混亂——Claude 會不知道何時該用哪個。
- 原則：刪掉太大的想法，縮小成一個具體任務；整個系統採**漸進式揭露（progressive disclosure）**。

### 段落 J｜示範應用（Slide 80–84）

**Slide 80**：用 Claude Code + Remotion 生成教學影片的多場景 prompt 示範（含打字機效果、圖片過場、影片串接）。
**Slide 81**：HTML 簡報範例 `https://github.com/gatelynch/html-slides`。
**Slide 82**：警語：這類生成很耗 token，研習現場不要示範。

### 段落 K｜進階心法：了解你的未知 + Skill 撰寫科學（Slide 85–99）

**Slide 91（「了解你的未知」— 全簡報最長的一篇備註，改寫自 Anthropic 的 agentic coding 方法論）**

四象限拆解你對任務的認知：
| 象限 | 意義 |
|---|---|
| 已知的已知 | 你寫進 prompt 的內容 |
| 已知的未知 | 意識到自己還不知道的事 |
| 未知的已知 | 顯而易見、從不寫下來，但看到就認得的標準（品味） |
| 未知的未知 | 完全沒考慮過的事 |

配套技巧（依實作階段）：
- **實作前**：盲點掃描（blindspot pass）、腦力激盪與原型（一次做 4 種設計方向讓你挑）、訪談（請 Claude 一次問一題）、參考資料（最好的參考是原始碼／範例檔）、實作計畫（把你最可能調整的決策放最前面）。
- **實作中**：讓 Claude 維護 `implementation-notes.md`，偏離計畫時記錄在 Deviations。
- **實作後**：打包提案文件（pitch）取得認可；請 Claude 出**測驗**考你，通過才 merge——確保你真的理解發生了什麼。

**Slide 92（Skill 撰寫的實證研究 — SkillsBench 等三篇論文的五大發現）**
1. **不要讓模型自己寫 Skill**：專家策劃的 Skill 大幅提升通過率；模型自產的 Skill 平均比無 Skill 還差。
2. **詳盡不是美德**：2–3 個檔案的聚焦型 Skill 勝過百科全書式 Skill；後者甚至低於無 Skill 基準。
3. **載入太多 Skill 會變笨**：整庫 196 個 Skill 全塞進 context，比精選小子集差 16 分、多耗 23% token。
4. **每個 harness 都要實測**：同一 Skill 在不同工具的提升幅度差異巨大（4.1–25.7 分）；Claude Code 的 Skill 利用率最高。
5. **把 Skill 瞄準模型最弱的領域**：軟體工程只提升 4.5 分（預訓練已飽和），**醫療保健提升 51.9 分**——模型覆蓋薄的專業領域才是套利機會。
- 方法論底線：沒有「有 Skill vs 無 Skill」的對照測試，你不知道 Skill 是否有效（84 個任務中有 16 個載入 Skill 後反而變差）。

**Slide 93–94、99**：整合練習——完成第一份 SKILL.md 草稿。
**Slide 95–96（人機分工）**：哪些事你做決定？哪些交給 AI？哪些 AI 做得再好你也不交出去？可以交的，驗收標準在哪？

### 段落 L｜第二大腦落地與收尾（Slide 100–118）

**Slide 100**：MVP 檢查表——你已打造出自己的最小可用系統，逐項打勾。
**Slide 104**：**第二大腦是使用中長大的**，不會一次完成，要定期檢視與調整。學員動作：寫下下週要跑的一個流程。
**Slide 105–107**：用共同範例 repo 練習（git clone 或 Download ZIP），避免一開始就卡在自己的雜亂資料。卡住就截圖問 Claude Code。
**Slide 108**：資料夾規則不是收納術，而是告訴 AI「每份資料現在扮演什麼角色、該遵循什麼規則處理」。
**Slide 109（金句）**：「把所有東西丟進資料夾叫**備份**，不叫第二大腦。第二大腦讓資料重新參與思考，幫你找出沒發現的細節與脈絡。」
**Slide 110**：Git 不是工程課，是保護知識庫的機制；不懂就出張嘴叫 Claude Code 做。
**Slide 118（結語）**：**工具只是入門，真正重要的是系統與流程。**

---

## 第二部分：醫學生版 — 用 Claude Code 打造醫學學習的第二大腦

> 以下把原簡報的每個概念，對應到醫學生（clerk / intern / PGY）的真實場景，並給出可直接使用的檔案範本與指令。

### 1. 為什麼醫學生需要 Agent，而不只是 ChatGPT

原簡報的「顧問 vs 助手」比喻，在醫學學習裡尤其明顯：

| 場景 | 網頁版 AI（顧問） | Claude Code（助手／Agent） |
|---|---|---|
| 讀 paper | 貼上摘要請它總結 | 讀整個資料夾的 PDF，交叉比對後產出結構化文獻表 |
| 考前複習 | 一問一答 | 掃描你整學期的筆記，找出你「從沒寫過筆記」的弱點章節 |
| 病例學習 | 描述病例請它討論 | 讀你的（去識別化）case log，依你的格式產出 SOAP、鑑別診斷樹、學習議題 |
| 做 Anki | 手動複製貼上 | 從筆記自動生成 cloze 卡片檔，直接匯入 |

關鍵差異就是 Slide 9 那句話：**Claude Code 根據「你的資料」回答，而不是憑訓練記憶**——這對醫學至關重要，因為它大幅降低幻覺風險（答案可以 grep 回你的講義與 guideline 原文驗證）。

### 2. 醫學生的第二大腦資料夾架構（對應 Slide 25、108–109）

```
med-brain/
├── CLAUDE.md              # 給 AI 的總說明書（見下方範本）
├── 01_courses/            # 各科講義、上課筆記（.md / .pdf）
│   ├── cardiology/
│   ├── endocrinology/
│   └── ...
├── 02_cases/              # 去識別化病例學習紀錄
│   └── 2026-07-15-dka.md
├── 03_papers/             # 文獻 PDF + 閱讀筆記
├── 04_guidelines/         # ADA、ESC、UpToDate 摘錄等
├── 05_exam/               # 考古題、錯題本、國考複習
├── 06_output/             # AI 產出物（摘要表、Anki 檔、簡報）
└── .claude/
    └── skills/            # 你的 Skill 們
```

Slide 109 的原則在這裡的意義：把 PDF 全丟進 `03_papers/` 只是**備份**；讓 Claude Code 讀它們、和你的病例筆記交叉連結、指出「這個病人的處置和 guideline 第 X 節不一致，為什麼？」——那才是**第二大腦**。

### 3. CLAUDE.md 範本（對應 Slide 48–58）

```markdown
# 我的醫學學習庫

## 我是誰
台灣醫學系六年級學生（clerk），目前在內科實習。母語中文，
醫學術語習慣中英並用（英文術語不翻譯）。

## 資料夾規則
- 01_courses/：講義與筆記，唯讀，不要修改
- 02_cases/：病例紀錄，一律已去識別化；新病例用 02_cases/template.md 格式
- 06_output/：所有 AI 產出物放這裡，檔名用 YYYY-MM-DD-主題.md

## 輸出格式偏好
- 病例討論一律用 SOAP 結構
- 鑑別診斷依「最可能 / 不能漏掉（can't-miss）/ 少見」三層排列
- 藥物劑量必須標註來源（哪份 guideline、哪一年版本）；找不到來源就明講「未在庫內找到」
- 生成內容中的每個數字與判斷，需標註出自哪個檔案，如 [01_courses/endo/dm.pdf p.12]

## 安全紅線
- 絕不生成可直接用於真實病人的醫囑
- 發現筆記內容與 04_guidelines/ 的 guideline 衝突時，要主動指出而不是沿用筆記
- 不確定的醫學論斷一律標註「⚠️ 需查證」
```

### 4. 醫學生必備的四個 Skill（對應 Slide 72–79）

依 Slide 75 的原則：**每個 Skill 只做一件小而具體的事**。而 Slide 92 的研究正說明：**醫療是 Skill 提升幅度最大的領域（+51.9 分）**——因為模型預訓練對在地化醫療流程（台灣國考格式、你們醫院的 present 慣例）覆蓋很薄，你寫下的專業判斷價值極高。

**Skill 1：`case-writeup`（病例整理）**
```markdown
---
name: case-writeup
description: 把零散的病例草稿整理成標準 SOAP + 學習議題。
  當使用者貼上或指向 02_cases/ 的草稿檔時使用。
---
1. 先確認內容已去識別化（無姓名、病歷號、精確日期）；有疑慮就停下來提醒。
2. 整理成 SOAP。Assessment 需含三層鑑別診斷（最可能/can't-miss/少見）。
3. 對照 04_guidelines/ 內相關指引，標出處置差異。
4. 最後列出 3 個 learning issues，各附一個可搜尋的 PICO 問題。
```

**Skill 2：`journal-club`（文獻評讀）**
```markdown
---
name: journal-club
description: 對 03_papers/ 內指定 PDF 做結構化評讀。觸發詞：評讀、journal club、critical appraisal。
---
1. 產出 PICO、研究設計、樣本數、主要結果（含效應量與 95% CI，逐字對照原文）。
2. 依研究類型套用對應 checklist（RCT→CONSORT 重點；觀察型→STROBE）。
3. 明確區分「論文說的」與「你的推論」，推論一律標 ⚠️。
4. 結尾給一段 30 秒口頭報告版本（中文，術語保留英文）。
```

**Skill 3：`anki-gen`（記憶卡片）**
```markdown
---
name: anki-gen
description: 從指定筆記生成 Anki 匯入檔。觸發詞：做卡片、anki、flashcards。
---
1. 只從指定檔案取材，不從一般知識補充；筆記沒寫到的不出題。
2. Cloze 格式，一張卡只考一個概念；數值型知識（劑量、cutoff）優先。
3. 輸出 TSV 到 06_output/，附卡片數量與涵蓋章節清單。
```

**Skill 4：`weak-spot-scan`（考前弱點掃描）**
```markdown
---
name: weak-spot-scan
description: 考前用。比對課綱／考古題範圍與 01_courses+05_exam 的筆記覆蓋度，找出弱點。
---
1. 讀 05_exam/ 的考古題範圍與錯題本。
2. 掃描 01_courses/ 筆記，列出「考過但筆記空白」與「反覆錯」的主題。
3. 產出 7 天複習排程（依弱點加權），存到 06_output/。
```

### 5. 把 Slide 91「了解你的未知」翻成醫學語言

這個框架其實就是臨床推理的後設認知，直接可用在查房前準備：

- **已知的已知**：你寫得出來的——這個病人的 problem list。
- **已知的未知**：你知道要查的——「hyponatremia 的 workup 流程我還不熟」。→ 直接問。
- **未知的已知**：你的品味——看到一份好的 present 就知道它好，但說不出標準。→ 用「參考資料」技巧：把學長姐的優秀病歷給 Claude Code 當範本（Slide 91 的 References 模式）。
- **未知的未知**：主治會電你的地方。→ 用 blindspot pass：
  > 「我明天要 present 這個 DKA 病例。請做一次盲點掃描：一個內分泌主治最可能追問哪些我完全沒準備到的面向？」

考前也可用 Slide 91 的**測驗模式**：「讀完我這份 nephrology 筆記後，出 10 題臨床情境題考我，我答完才給答案與出處。」

### 6. Context 管理的醫學生實務（對應 Slide 37–47）

- 一次餵 20 篇 PDF 會撞上「40–60% 開始錯亂」的牆。→ 正確做法是 Slide 61 的 **subagent**：請 Claude Code 為每篇 paper 派一個 subagent 讀，各自回報結構化摘要，主 session 只彙整。
- 換科（換任務）就 `/clear`；發現它開始把 A 病例的數據混進 B 病例，立刻 `/rewind` 或 `/clear`。
- 每個新資料夾先跑 `/init`，再手動把「安全紅線」段落補進 CLAUDE.md。

### 7. 醫學情境的安全守則（原簡報沒有、但醫學生必須加上的一段）

1. **PHI 絕對紅線**：任何進入資料夾的病例必須先去識別化（姓名、病歷號、床號、精確日期、罕見病的可辨識組合）。這不是 AI 問題，是法律問題（個資法／醫療法）。
2. **AI 輸出不是醫療決策**：所有產出僅供學習；用於真實病人前必須回到原始 guideline 與上級醫師。
3. **可驗證性優先**：這正是第二大腦勝過網頁 AI 之處——要求每個論斷附上檔案出處（`[檔名 p.X]`），你可以 grep 驗證。無出處的內容一律視為未驗證。
4. **Skill 也要做對照測試**（Slide 92 的方法論）：同一批考古題，「有 Skill」vs「無 Skill」各跑一次比較正確率——16/84 的任務載入 Skill 反而變差，醫學內容尤其要驗。

### 8. 第一週上手路線圖（對應 Slide 100–110 的 MVP 精神）

| 天 | 動作 | 對應簡報 |
|---|---|---|
| Day 1 | 安裝 Claude Code + VS Code，建立 med-brain 資料夾 | S21–25 |
| Day 2 | 丟入一科的講義，`/init`，手寫 CLAUDE.md 的偏好與紅線 | S42、48–58 |
| Day 3 | 練手感：`@` 一份講義請它解釋、出 5 題考你 | S35 |
| Day 4 | 寫第一個 Skill（建議從 anki-gen 開始，最小最具體） | S74–76 |
| Day 5 | 用 journal-club Skill 評讀一篇下週 meeting 的 paper | S72–79 |
| Day 6 | 請 Claude Code `git init` 你的知識庫並教你看 `git status` | S110 |
| Day 7 | 回顧：寫下「下週要固定跑的一個流程」 | S104 |

最後回到 Slide 118 的結語，對醫學生同樣成立：**工具只是入門，真正重要的是系統與流程**——你沉澱進 CLAUDE.md 和 Skill 的，其實是你正在成形的臨床判斷本身。
