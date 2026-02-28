# 📥 Git 安装与配置全指南（2026 最新版 · 避坑详解）

> 💡 **写在前面**  
> 很多新手在安装时对着几十个英文选项发呆，或者随便点“Next”导致后续命令报错。别担心，跟着下面的步骤走，保证一次成功！

---

## 📑 目录导航

- [1️ 下载 Git](#1-下载-git)
- [2️ 安装步骤（Windows 篇 - 重点！）](#2-安装步骤windows-篇---重点)
  - [ 关键步骤详解](#-关键步骤详解)
  - [ 避坑指南](#-避坑指南)
- [3️ 安装步骤（Mac 篇）](#3-安装步骤mac-篇)
  - [方法 A：使用 Homebrew（推荐）](#方法-a使用-homebrew推荐)
  - [方法 B：下载安装包](#方法-b下载安装包)
- [4️ 验证安装 & 身份配置（必做！）](#4-验证安装--身份配置必做)
  - [第一步：打开终端](#第一步打开终端)
  - [第二步：检查版本](#第二步检查版本)
  - [第三步：配置身份](#第三步配置身份)
- [5️ 常见问题（FAQ）](#5-常见问题faq)
  - [Q: 提示“不是内部或外部命令”？](#q-提示不是内部或外部命令)
  - [Q: 为什么邮箱要填对？](#q-为什么邮箱要填对)
  - [Q: Mac 用户提示 xcode-select 错误？](#q-mac-用户提示-xcode-select-错误)
- [ 下一步](#-下一步)


---

## 1️⃣ 下载 Git

请始终从官方网站下载，确保软件安全且版本最新。

- **官方网站**: [https://git-scm.com/downloads](https://git-scm.com/downloads)
- **国内加速下载**（如果官网太慢）: [https://registry.npmmirror.com/binary.html?path=git-for-windows/](https://registry.npmmirror.com/binary.html?path=git-for-windows/) （淘宝镜像）

👉 **操作**：进入网站后，它会自动识别你的系统。点击大大的 **Download** 按钮（例如 `Download for Windows`）。

---

## 2️⃣ 安装步骤（Windows 篇 - 重点！）

下载完成后，双击 `.exe` 安装包。**注意：不要全程无脑点 Next，以下几个关键步骤请仔细看！**

### ⚠️ 关键步骤详解

| 步骤 | 界面标题 | ✅ 推荐设置 | 💡 为什么要这样选？ |
| :--- | :--- | :--- | :--- |
| **1** | **Select Components** | 保持默认，但勾选 **`Add a Git Bash Profile to Windows Terminal`** | 让你能在酷炫的 Windows Terminal 里直接用 Git。 |
| **2** | **Choosing Default Editor** | **推荐使用 VS Code**（如果已安装）<br>或保持默认的 **Vim** | Vim 对新手太难退出！选 VS Code 或 Notepad++ 会更友好。 |
| **3** | **Adjusting PATH...** | **✅ 推荐选第二项**: <br>`Git from the command line and also from 3rd-party software` | **最重要的一步！** 这样才能在任意文件夹右键打开终端使用 git 命令。 |
| **4** | **Configuring Line Endings** | **✅ 推荐选第一项**: <br>`Checkout Windows-style, commit Unix-style` | 防止因为换行符不同，导致你和 Mac/Linux 队友协作时报错。 |
| **5** | **Configuring Terminal Emulator** | 选择 **`Use MinTTY`**（默认） | 这是 Git Bash 自带的终端，兼容性最好。 |
| **6** | **Extra Options** | 勾选 **`Enable file system caching`** | 提升大项目下的 Git 速度。 |

### 🚫 避坑指南

> *   **PATH 选项陷阱**：如果你在第 3 步选了第一项（Only use Git from...），那你以后每次用 git 都得打开特定的 Git Bash 窗口，不能在 PowerShell 里用，非常麻烦！**一定要选第二项！**
> *   **路径陷阱**：安装路径建议保持默认 `C:\Program Files\Git`，**千万不要包含中文路径**，否则会出现莫名其妙的乱码错误。

---

## 3️⃣ 安装步骤（Mac 篇）

Mac 用户有两种选择：

### 方法 A：使用 Homebrew（推荐）

如果你已经安装了 Homebrew，一行命令搞定：

```bash
brew install git