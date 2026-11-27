# 工作空间说明（Windows，路径暂定）

## 父级目录（暂定）

```
D:\MOYUAI-Workspace\
```

如果 D 盘不方便，改为 `C:\Users\<用户名>\MOYUAI-Workspace`，只改这一行，子文件夹名不变。

## 两个独立工作区

```
D:\MOYUAI-Workspace\
├── codex\                 # Codex 工作空间
│   └── moyuai\            # 克隆 TAOEL/moyuai，大脑用
├── workbuddy\             # WorkBuddy 工作空间
│   └── moyuai\            # 克隆 TAOEL/moyuai，员工用
└── handoff\               # 可选：本地草稿区，不放代码
```

## 绑定方法

1. 在 Codex 里绑定 `D:\MOYUAI-Workspace\codex` 为主工作区。
2. 在 WorkBuddy 里绑定 `D:\MOYUAI-Workspace\workbuddy` 为主工作区。
3. 各自在自己的 `moyuai` 文件夹里 `git clone https://github.com/TAOEL/moyuai.git`（私有仓库，需已登录 TAOEL 账号）。
4. 三个 Agent 统一用同一个 GitHub 账号 TAOEL。

## 铁律

- Codex 只动 `codex\moyuai`，WorkBuddy 只动 `workbuddy\moyuai`。
- 不在本地文件夹之间直接复制、覆盖文件。
- 改完先 `git pull`，再开分支、提交、推到 GitHub、提 PR。
- Muse 只看 GitHub，看不到本地没推上去的内容。没推上去，就等于没做完。
