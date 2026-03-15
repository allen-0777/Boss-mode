📖 Boss Mode 技術文件 (Technical Documentation)
本文件詳細說明 Boss Mode 的底層設計邏輯、支援的技術棧，以及在不同 AI Agent 平台上的部署與安裝方式。

1. 系統架構與技術棧 (Architecture & Tech Stack)
Boss Mode 不依賴任何傳統的後端伺服器，它建立在現代 LLM (大型語言模型) 的上下文理解與指令遵循能力之上。

核心範式: Prompt Engineering, State Machine (狀態機), Zero-shot/Few-shot prompting.

配置語言: Markdown (用於撰寫 Prompt 與結構化指令), YAML/JSON (視不同 Agent 平台的設定檔格式而定).

目標執行環境 (Target Platforms):

Cursor IDE (基於 VS Code 的 AI 編輯器)

Cline / Roo Code (VS Code Extension)

obra/superpowers (基於終端機與檔案系統的 AI Agent 框架)

相容的底層 LLM: Claude 3.5 Sonnet (推薦，指令遵循能力最強), GPT-4o, Gemini 1.5 Pro.

2. 核心狀態機邏輯 (Core State Machine Logic)
Boss Mode 的核心是一個 強制性的單向狀態機。AI 必須被限制在這個狀態機內，無法跨越階段執行操作。我們透過 System Prompt 中的 [Phase X] 標籤來鎖定 AI 的行為邊界。

State 0: Idle (閒置) - 等待使用者輸入需求。

State 1: Requirement Alignment (需求收斂)

觸發條件: 收到模糊指令或 /boss-mode 指令。

權限限制: WRITE_CODE = FALSE

必須輸出: 🎯 目標對齊、🚨 待釐清盲區、💡 主推方案、🛑 請求簽核。

流轉條件: 使用者明確同意提案 (Approval)。

State 2: Planning (計畫生成)

權限限制: 只能寫入 PLAN.md 檔案，WRITE_IMPLEMENTATION_CODE = FALSE

必須輸出: 將實作拆解為可驗證的步驟清單 (Phase 1, Phase 2...)。

流轉條件: 使用者回覆 "LGTM" (Looks Good To Me) 或明確批准。

State 3: Execution (執行開發)

權限限制: WRITE_CODE = TRUE

行為準則: 嚴格按照 PLAN.md 執行，每完成一步需更新狀態並自我驗證。

3. 部署與安裝指南 (Deployment & Installation)
由於這是一個 Plugin/Extension 概念的專案，部署 (Deployment) 意指將配置檔導入到使用者的開發環境中。

部署方式 A：整合至 Cursor IDE
Cursor 支援透過專案根目錄的 .cursorrules 檔案來定義 AI 的全域行為。

在你的專案根目錄建立一個名為 .cursorrules 的檔案。

將本專案 integrations/cursor/.cursorrules 的內容複製貼上。

驗證: 在 Cursor 的 AI Chat 視窗輸入：「我要做一個購物車系統」，觀察 AI 是否有先給出「主推方案」而不是直接噴 Code。

部署方式 B：整合至 obra/superpowers
superpowers 透過 .skill.md 來定義 AI 的技能。

找到你的 superpowers 安裝目錄（通常位於 ~/.superpowers/skills/ 或專案設定內）。

將本專案的 integrations/superpowers/manage-up.skill.md 複製到該目錄下。

驗證: 啟動 superpowers，使用指令 @manage-up 我需要一個會員登入功能 觸發工作流。

部署方式 C：整合至 Cline / Roo Code
Cline 允許自定義 System Instructions。

打開 VS Code，進入 Cline 的設定 (Settings) 面板。

找到 "Custom Instructions" 區塊。

將 integrations/cline/custom-instructions.md 的內容貼入並儲存。

（可選）在專案根目錄建立 cline_rules.md 進行覆蓋設定。

4. 擴展功能與自訂 (Extensibility)
開發者可以根據自己的團隊習慣微調 Boss Mode：

修改 Default Proposal 的偏好: 可以在 Prompt 中寫死團隊的技術棧（例如：「主推方案必須預設使用 Next.js + TailwindCSS + Supabase」）。

增加驗證閘門 (Validation Gates): 可以在 State 2 到 State 3 之間，加入強制 AI 撰寫 TEST_PLAN.md 的步驟。