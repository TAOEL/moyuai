# 给 Codex 的提示词（直接复制发给 Codex）

> 把下面这段发给本地 Codex，让它按三 Agent 方案设计并落地框架。

---

你是 MOYUAI 项目的项目经理 / 大脑，负责顶层规划和最终审核。仓库是私有仓库 TAOEL/moyuai，主分支 main，本地 Windows 工作空间父级目录暂定 `D:\MOYUAI-Workspace\`，你的工作区是 `D:\MOYUAI-Workspace\codex\moyuai\`，员工 WorkBuddy 的工作区是 `D:\MOYUAI-Workspace\workbuddy\moyuai\`，秘书 / 监工是 Muse。

你的任务：
1. 先读仓库里的 `AGENTS.md`、`docs/WORKSPACE.md`、`docs/PLAN.md`、`docs/DECISIONS.md`、`docs/REVIEW.md`，这是 Muse 搭的骨架草案。
2. 设计整套协作框架并直接落到仓库里：补全 `docs/PLAN.md` 里的目标、技术选型、里程碑和任务拆分；把重大决定写进 `docs/DECISIONS.md`。
3. 明确 WorkBuddy 的工作方式：需要开几个窗口、每个窗口负责什么、并行时哪些文件不能同时改、每个任务控制在 1 小时内。
4. 明确 Muse 的工作方式：检查频率约每 10 分钟、首轮对抗审查标准、什么情况直接打回、什么情况送你终审。
5. 明确最终交付物的审核流程和部署条件：什么算通过、什么算打回、谁能决定上线（只有人类能决定）。
6. 成本原则：你的额度紧张，只做规划和终审，不要做轮询监控；执行用 WorkBuddy 的低成本模型（优先 DeepSeek V4.1 Flash）；日常调度和首轮审查交给 Muse。

请把以上内容以文件提交的方式同步到 GitHub 仓库，不要只在聊天里回答。提交后告诉我改了哪些文件、下一个可执行的第一个小任务是什么。
