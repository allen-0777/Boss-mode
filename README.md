# 🎯 Boss Mode (Project Goals)
Boss Mode is an advanced prompt framework and workflow plugin designed specifically for AI development agents (e.g., Cursor, Cline, Superpowers). Its core mission is to transform AI from a "clueless junior coder" into a "Senior Staff Engineer" — forcing the AI to clarify requirements, propose architectural designs, and obtain your approval before writing a single line of code.

---

[English](#english) | [繁體中文](#繁體中文)

---

<a name="english"></a>
## English

🚨 **Pain Points Solved**
When a user (The Boss) gives high-level or vague instructions (e.g., "Add a dashboard to view revenue"), traditional AI agents often "hallucinate" missing details and instantly produce massive amounts of buggy code. This leads to:
- Unnecessary technical debt.
- Broken architectures or database performance issues.
- Wasted API tokens and endless debugging loops.

💡 **Core Mechanism: 3-Phase Guardrails**
Boss Mode implements a strict State Machine:

**Phase 1: Requirement Alignment (No Implementation Code Allowed)**
AI must produce: **Goal Alignment (Summary)**, **Missing Context**, and a **Default Proposal**, then explicitly request your approval.

**Phase 2: Planning (No Implementation Code Allowed)**
Once the proposal is approved, AI generates a step-by-step execution plan in Markdown format (`PLAN.md`).

**Phase 3: Execution**
Only after you reply "LGTM" or approve the plan, the AI is "unlocked" to start writing code step-by-step.

🛠️ **Tech Stack & Supported Platforms**
This is a Prompt-as-Code project with zero dependencies, perfectly compatible with:
- **Cursor IDE**: Configured via `.cursorrules`.
- **Cline (Formerly Claude Dev) / Roo Code**: Configured via Custom Instructions.
- **Superpowers (obra/superpowers)**: Configured via `.skill.md` definitions.
- **Claude Code CLI**: Configured via CLAUDE.md or skills.
- **Antigravity**: Configured via workflow defined in `.agents/workflows/boss-mode.md`.
- **General LLMs**: ChatGPT, Claude, Gemini (as System Prompts).

🚀 **Quick Start**

**Cursor Users**: Copy [integrations/cursor/.cursorrules](./integrations/cursor/.cursorrules) to your project root.

**Antigravity Users**: Use the [boss-mode workflow](./.agents/workflows/boss-mode.md) or check [integrations/antigravity/README.md](./integrations/antigravity/README.md).

**Superpowers Users**: Import [integrations/superpowers/boss-mode.skill.md](./integrations/superpowers/boss-mode.skill.md).

**Cline Users**: Use [integrations/cline/custom-instructions.md](./integrations/cline/custom-instructions.md) for your Custom Instructions.

**Claude Code Users**: Place [integrations/claude-code/CLAUDE.md](./integrations/claude-code/CLAUDE.md) in your project root, or [integrations/claude-code/boss-mode.skill.md](./integrations/claude-code/boss-mode.skill.md) in `.claude/skills/`.

**Trigger**: Simply type: "I want to develop [feature], start Boss Mode."

---

<a name="繁體中文"></a>
## 繁體中文

🎯 **專案目標**
Boss Mode (老闆模式) 是一個專為 AI 程式開發代理（如 Cursor, Cline, Superpowers）設計的進階提示詞架規與工作流外掛。它的核心目標是將 AI 從「無腦寫 Code 的菜鳥」轉變為「資深技術總監 (Senior Staff Engineer)」—— 在寫下任何一行程式碼之前，強制 AI 先釐清需求、提出架構提案，並取得你的批准。

🚨 **核心痛點與解決方案 (The Philosophy)**
> **✨「讓 Boss Mode 的精神大腦，驅動 Superpowers 的強大肉體。」**

當使用者（老闆）給出高層級或模糊指令（例如：「幫我加一個可以看營收的後台」），傳統 AI 往往會自行「通靈」並瞬間產出大量充滿技術債的程式碼。

Boss Mode 旨在成為 **「軟體工程的防禦塔 (Macro-level Defense)」**：
- **Superpowers (obra/superpowers) 是「資深實作工程師」**：負責精準地切分 Git 分支、寫自動化測試、處理底層髒活（How to build it right）。
- **Boss Mode 則是「資深技術總監 (Senior Staff Engineer)」**：負責在第一時間擋下寫 Code 的衝動，逼迫 AI 與你對齊商業邏輯、畫好架構藍圖（What is the right thing to build）。

**解決的痛點：**
- 減少不必要的技術債與錯誤的架構方向。
- 防止 AI 破壞現有資料庫效能。
- 節省大量 API Token 與無止盡的 Debug 迴圈。
- **強制產出技術文件 (TECH_DOC.md)**：開發前、中、後永遠保持文件最新狀態。

💡 **核心機制：三階段護欄 (3-Phase Guardrails)**
Boss Mode 在底層實作了嚴格的狀態機 (State Machine) 流程：

**Phase 1: 需求收斂 (嚴禁寫實作程式碼)**
AI 必須產出：目標對齊 (Summary)、待釐清盲區 (Missing Context)、主推方案 (The Default Proposal)，並主動請求老闆簽核。

**Phase 2: 計畫生成 (嚴禁寫實作程式碼)**
老闆同意提案後，AI 將產出一份 Markdown 格式的分步執行計畫 (PLAN.md)。

**Phase 3: 執行開發**
只有當老闆對計畫回覆 "LGTM" (看起來不錯) 或批准後，AI 才能解除封印，開始逐步撰寫程式碼。

🛠️ **技術棧與支援平台**
這是一個 Prompt-as-Code (提示詞即程式碼) 的專案，零依賴套件，完美相容於以下工具：
- **Cursor IDE**: 透過 .cursorrules 檔案配置
- **[Cline (原 Claude Dev) / Roo Code]**: 透過 Custom Instructions 配置
- **Superpowers (obra/superpowers)**: 透過 .skill.md 技能定義檔配置
- **Claude Code CLI**: 透過 CLAUDE.md 或 skills 配置。
- **Antigravity**: 透過 `.agents/workflows/boss-mode.md` 定義的工作流配置。
- **通用大型語言模型**: ChatGPT, Claude, Gemini (作為 System Prompts 使用)

🚀 **快速開始**

**Cursor 使用者**: 將 [integrations/cursor/.cursorrules](./integrations/cursor/.cursorrules) 複製到你的專案根目錄。

**Antigravity 使用者**: 使用 [boss-mode 工作流](./.agents/workflows/boss-mode.md) 或查看 [integrations/antigravity/README.md](./integrations/antigravity/README.md)。

**Superpowers 使用者**: 匯運用 [integrations/superpowers/boss-mode.skill.md](./integrations/superpowers/boss-mode.skill.md)。

**Cline 使用者**: 使用 [integrations/cline/custom-instructions.md](./integrations/cline/custom-instructions.md) 作為你的 Custom Instructions 規定。

**Claude Code 使用者**: 將 [integrations/claude-code/CLAUDE.md](./integrations/claude-code/CLAUDE.md) 放入專案根目錄，或將 [integrations/claude-code/boss-mode.skill.md](./integrations/claude-code/boss-mode.skill.md) 放入 `.claude/skills/` 中。

**觸發方式**：只需輸入 "我想開發 [某個功能]，啟動 Boss Mode。" 即可。

