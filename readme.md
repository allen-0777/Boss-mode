🎯 專案目標
[繁體中文](file:///Users/liyuchan/Desktop/Boss-Mode/README.md) | [English](file:///Users/liyuchan/Desktop/Boss-Mode/README_EN.md)

Boss Mode (老闆模式) 是一個專為 AI 程式開發代理（如 Cursor, Cline, Superpowers）設計的進階提示詞架構與工作流外掛。它的核心目標是將 AI 從「無腦寫 Code 的菜鳥」轉變為「資深技術總監 (Senior Staff Engineer)」—— 在寫下任何一行程式碼之前，強制 AI 先釐清需求、提出架構提案，並取得你的批准。

🚨 解決的痛點
當使用者（老闆）給出高層次或模糊的指令（例如：「幫我加一個可以看營收的後台 Dashboard」），傳統的 AI 往往會自行「通靈」猜測缺少的細節，並立刻產出大量且常常漏洞百出的實作程式碼。這會導致：

產生不必要的技術債。

破壞現有架構或拖垮資料庫效能。

浪費大量 API Token 與無止盡的 Debug 迴圈。

💡 核心機制：三階段護欄 (3-Phase Guardrails)
Boss Mode 在底層實作了嚴格的狀態機 (State Machine) 流程：

Phase 1: 需求收斂 (嚴禁寫實作程式碼)

AI 必須產出：目標對齊 (Summary)、待釐清盲區 (Missing Context)、主推方案 (The Default Proposal)，並主動請求老闆簽核。

Phase 2: 計畫生成 (嚴禁寫實作程式碼)

老闆同意提案後，AI 將產出一份 Markdown 格式的分步執行計畫 (PLAN.md)。

Phase 3: 執行開發

只有當老闆對計畫回覆 "LGTM" (看起來不錯) 或批准後，AI 才能解除封印，開始逐步撰寫程式碼。

🛠️ 技術棧與支援平台
這是一個 Prompt-as-Code (提示詞即程式碼) 的專案，零依賴套件，完美相容於以下工具：

Cursor IDE: 透過 .cursorrules 檔案配置

[Cline (原 Claude Dev) / Roo Code]: 透過 Custom Instructions 配置

Superpowers (obra/superpowers): 透過 .skill.md 技能定義檔配置

Claude Code CLI: 透過 CLAUDE.md 或 skills 配置。

通用大型語言模型: ChatGPT, Claude, Gemini (作為 System Prompts 使用)

🚀 快速開始

Cursor 使用者: 將 [integrations/cursor/.cursorrules](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/cursor/.cursorrules) 複製到你的專案根目錄。

Superpowers 使用者: 匯入 [integrations/superpowers/boss-mode.skill.md](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/superpowers/boss-mode.skill.md)。

Cline 使用者: 使用 [integrations/cline/custom-instructions.md](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/cline/custom-instructions.md) 作為你的 Custom Instructions規定。

Claude Code 使用者: 將 [integrations/claude-code/CLAUDE.md](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/claude-code/CLAUDE.md) 放入專案根目錄，或將 [integrations/claude-code/boss-mode.skill.md](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/claude-code/boss-mode.skill.md) 放入 `.claude/skills/` 中。

觸發方式：只需輸入 "我想開發 [某個功能]，啟動 Boss Mode。" 即可。