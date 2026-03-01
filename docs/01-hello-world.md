# 🌱 Ep01: 破冰之旅 - Git 是什么？

> **目标**：消除对命令行的恐惧，完成第一次代码提交。

## 1. Git 是什么？(小白版解释)

别被那些高大上的定义吓到。你可以把 Git 想象成一台**“智能照相机”**：
- **工作区**：你正在写的代码文件。
- **暂存区 (`git add`)**：把你想拍的文件放进相机胶卷。
- **本地仓库 (`git commit`)**：按下快门，拍成照片存档。
- **远程仓库 (`git push`)**：把照片上传到云端相册 (GitHub)。

## 2. 准备工作

### 安装 Git
前往 [Git 官网](https://git-scm.com/) 下载并安装。一路 Next 即可。
*(如果你在安装时遇到报错，请查看 [📥 附录：安装指南](./00-install-guide.md))*

### 配置身份 (必须做！)
打开 Git Bash，输入以下命令（替换成你自己的信息）：

```bash
git config --global user.name "你的 GitHub 用户名"
git config --global user.email "你的 GitHub 邮箱"
```

## 3. 第一个 Hello World

### 第一步：创建项目文件夹
```bash
mkdir my-first-repo
cd my-first-repo
```

### 第二步：初始化仓库
```bash
git init
```
*(你会看到提示：Initialized empty Git repository...)*

### 第三步：创建文件
```bash
echo "# Hello Git" > README.md
```

### 第四步：查看状态
```bash
git status
```
*(你会看到 `README.md` 是红色的，表示未跟踪)*

### 第五步：添加到暂存区
```bash
git add README.md
```
*(再次 `git status`，你会发现它变绿了！)*

### 第六步：提交 (拍照)
```bash
git commit -m "第一次提交：创建了 README 文件"
```

## 🎉 恭喜！
你已经完成了本地的第一次提交！接下来就可以把它推送到 GitHub 了。

---
[🔙 返回主页](../README.md)
