# MOYUAI — 三 Agent 协作规则

仓库：TAOEL/moyuai（私有），主分支 main。
唯一事实来源是 GitHub。本地没推上去的东西，其他 Agent 看不到。

## 角色

- **大脑 / 项目经理：Codex（本地 Windows）**
  只做规划、拆任务、定优先级、终审。决定只写在 `docs/PLAN.md` 和 `docs/DECISIONS.md`。
  不直接写业务代码，不用 Codex 轮询监控，不拿它盯进度，省额度。
- **员工：WorkBuddy（本地 Windows，模型优先 DeepSeek V4.1 Flash）**
  只按 Issue 干活。一个任务一个分支，做完提 PR。
  单个任务控制在 1 小时内能做完。不要改规划、不要自己加需求、不要直接合进 main。
- **秘书 / 监工：Muse**
  负责传话、拆任务、盯进度、首轮对抗审查。
  每 10 分钟左右检查一次 GitHub 上的 Issue / 提交 / PR 进度（以 GitHub 实际变化为准）。
  初审不合格直接打回重写，合格才送 Codex 做第二轮审查，最后由人类决定是否部署上线。

## 工作空间（Windows，路径暂定）

```
D:\MOYUAI-Workspace\
├── codex\moyuai\       # Codex 的工作区，只动这里
└── workbuddy\moyuai\   # WorkBuddy 的工作区，只动这里
```

各自绑定自己的文件夹为主工作区，绝不串门改对方的文件夹。
所有交流走 git：推到 GitHub、拉取最新、开分支、提 PR。不要直接在本地文件夹之间复制文件。

三个 Agent 统一登录同一个 GitHub 账号 TAOEL，同步规划和任务文件。

## 工作流

1. 人类给目标。
2. Codex 写规划到 `docs/PLAN.md`，重大决定记到 `docs/DECISIONS.md`，并同步到 GitHub。
3. Muse 把规划拆成小任务，写成 Issue，写清目标、验收标准、能改哪些文件、分支名。
4. WorkBuddy 按 Issue 干活，一个任务一个分支，推分支、提 PR。
5. Muse 首轮对抗审查：对照规划、跑通逻辑、检查幻觉和漏洞，不合格打回。
6. Codex 第二轮审查：方向、架构、验收。
7. 人类最终决定部署。

## 分支与 PR

- 分支命名：`workbuddy/<任务号>-<简述>`，例如 `workbuddy/3-homepage-ui`。
- Muse 的骨架 / 规则类分支：`muse/<简述>`。
- 每个 PR 必须关联一个 Issue，写清改了什么、怎么验证。
- main 受保护的思路：不直接推 main，只合 PR。

## 审查标准（简版，详见 docs/REVIEW.md）

- 是否符合 Codex 的规划和决策记录。
- 是否完成 Issue 的验收标准，有没有多做或少做。
- 有没有明显幻觉、硬编码、假实现、逻辑漏洞。
- 有没有破坏已有功能，命名和结构是否一致。
