# 🚀 Git & GitHub 新手通关指南：从入门到实战

> **🎯 项目愿景**：基于**费曼学习法**，用“教”来促进“学”。
> 这里记录了我（一个纯新手）从零开始学习 Git 的全过程。没有晦涩的理论堆砌，只有最真实的踩坑记录和傻瓜式操作指南。
> 
> 👨‍💻 **作者**：[mrdmrddld](https://github.com/mrdmrddld)  
> 📅 **最后更新**：2026-02-28  
> 🏷️ **状态**：持续更新中...

---

## 📖 为什么会有这个教程？

如果你和我一样：
- ❌ 看到黑色的命令行窗口就害怕；
- ❌ 分不清 `add`, `commit`, `push` 的区别；
- ❌ 被 `Connection reset` 或 `Permission denied` 报错搞得心态爆炸；
- ❌ 看了很多教程，一动手就废；

那么，这个教程就是为你准备的！我不讲复杂的底层原理，只告诉你**“怎么做能跑通”**以及**“出错了怎么修”**。

---

## 🗺️ 学习路线图 (Course Map)

本教程采用**微课 + 实战**的形式，每个章节解决一个具体问题。

| 章节 | 主题 | 核心内容 | 状态 |
| :---: | :--- | :--- | :---: |
| **Ep01** | 🌱 **破冰之旅** | Git 是什么？安装配置与第一个 `hello world` | ✅ 已完成 |
| **Ep02** | 📸 **核心三连** | 详解 `add` (暂存), `commit` (提交), `push` (推送) | ✅ 已完成 |
| **Ep03** | 🔑 **免密登录** | **重点！** 手把手配置 SSH Key，彻底告别密码和连接错误 | ✅ 已完成 |
| **Ep04** | 🕵️ **排错实录** | 常见报错分析：拼写错误、HTTPS vs SSH、网络重置 | 🚧 编写中 |
| **Ep05** | ⏪ **时光倒流** | 使用 `git log` 查看历史，以及如何回退版本 | ⏳ 计划中 |
| **Ep06** | 🌿 **分支魔法** | 创建分支 (`branch`) 与合并代码 (`merge`) | ⏳ 计划中 |

---

## 🔥 精彩抢先看 (Highlights)

### 💡 核心概念：Git 就像一台“智能照相机”
- **工作区**：你在电脑上写的代码。
- **暂存区 (`git add`)**：把想拍的文件放进相机胶卷。
- **本地仓库 (`git commit`)**：按下快门，拍成照片存档。
- **远程仓库 (`git push`)**：把照片上传到云端相册 (GitHub)。

### 🛠️ 避坑指南：我踩过的雷，你不用再踩
#### 1. 拼写错误陷阱
> **错误现场**：`git push -u orgin master`  
> **报错**：`fatal: 'orgin' does not appear to be a git repository`  
> **原因**：把 `origin` 少打了一个 `i`。Git 找不到叫 `orgin` 的地方。  
> **✅ 修正**：仔细检查命令，确保是 `origin`。

#### 2. 网络连接重置
> **错误现场**：使用 HTTPS 推送时，报错 `Recv failure: Connection was reset`。  
> **原因**：国内网络环境直连 GitHub 不稳定。  
> **✅ 修正**：**强烈建议配置 SSH！** (详见 [Ep03 教程](./03-ssh-setup.md))

#### 3. 协议混淆
> **现象**：明明配了 SSH，推送时还是走 HTTPS。  
> **排查**：运行 `git remote -v`。如果看到 `https://` 开头，说明没改成功。  
> **✅ 修正**：运行 `git remote set-url origin git@github.com:用户名/仓库.git`。

---

## 🚀 快速开始 (Quick Start)

> 💡 **还没安装 Git？** 别急！如果你还没有安装 Git，或者在安装过程中遇到了报错，请先阅读这份保姆级指南：
> 👉 **[📥 附录：Git 安装与配置全指南 (含避坑详解)](./docs/00-install-guide.md)**

### 1. 配置身份

```bash
git config --global user.name "你的用户名"
git config --global user.email "你的邮箱"
```

### 2. 初始化仓库

```bash
mkdir my-first-repo
cd my-first-repo
git init
```

### 2. 日常提交三板斧
```bash
git add .
git commit -m "这里是修改说明"
git push -u origin main
```

> 💡 **提示**：如果是第一次推送，可能会遇到权限错误或网络错误。
> - 遇到 `Permission denied`？请前往 [🔑 Ep03: 免密登录](./docs/03-ssh-setup.md) 配置 SSH。
> - 遇到 `Connection reset`？请前往 [🕵️ Ep04: 排错实录](./docs/04-troubleshooting.md) 查看解决方案。

---

## 📚 详细教程章节 (Detailed Chapters)

点击以下链接，进入每个章节的深度学习（包含图文详解和避坑指南）：

### 🌱 Ep01: 破冰之旅
*   **内容**：Git 是什么？安装配置与第一个 `hello world`。
*   **状态**：✅ 已完成
*   🔗 **[点击进入 Ep01 详情页 >>](./docs/01-hello-world.md)**

### 📸 Ep02: 核心三连
*   **内容**：详解 `add` (暂存), `commit` (提交), `push` (推送) 的核心逻辑。
*   **状态**：✅ 已完成
*   🔗 **[点击进入 Ep02 详情页 >>](./docs/02-core-commands.md)**

### 🔑 Ep03: 免密登录
*   **内容**：手把手配置 SSH Key，彻底告别密码输入和 HTTPS 连接错误。
*   **状态**：✅ 已完成
*   🔗 **[点击进入 Ep03 详情页 >>](./docs/03-ssh-setup.md)**

### 🕵️ Ep04: 排错实录
*   **内容**：常见报错分析：拼写错误、HTTPS vs SSH 混淆、网络重置。
*   **状态**：🚧 编写中
*   🔗 **[点击进入 Ep04 详情页 >>](./docs/04-troubleshooting.md)**

### ⏪ Ep05: 时光倒流
*   **内容**：使用 `git log` 查看历史，以及如何回退版本。
*   **状态**：⏳ 计划中
*   🔗 **[点击进入 Ep05 详情页 >>](./docs/05-time-travel.md)**

### 🌿 Ep06: 分支魔法
*   **内容**：创建分支、切换分支与合并代码的最佳实践。
*   **状态**：⏳ 计划中
*   🔗 **[点击进入 Ep06 详情页 >>](./docs/06-branching.md)**

---

## 🤝 如何参与贡献？

本教程基于**费曼学习法**构建，欢迎任何新手或大佬提出建议：
- 🐛 发现错别字或命令错误？请提 **Issue**。
- 💡 有更好的解释方式？请提 **Pull Request**。
- 📢 想要增加新的章节？请在讨论区留言。

---

## 📜 许可证 (License)

本项目采用 [MIT License](LICENSE) 协议开源。希望它能帮助你轻松掌握 Git！

> **"教是最好的学。" —— 理查德·费曼**