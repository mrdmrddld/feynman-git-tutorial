# 📸 Ep02: 核心三连 - Add, Commit, Push

> **目标**：掌握 Git 最核心的三个命令，理解“暂存区”的概念，完成第一次版本存档。

## 💡 核心概念：Git 就像一台“智能照相机”

在开始敲命令之前，请先记住这个比喻，它能帮你理解 90% 的 Git 操作：

1.  **工作区 (Working Directory)**：你电脑上正在编辑的文件（比如你刚写好的代码）。
2.  **暂存区 (Staging Area)**：**这是 Git 独有的概念！** 它就像相机的“胶卷”或“取景框”。
    *   你把想拍的文件放进这里 (`git add`)。
    *   你可以只放一部分文件，而不是全部。
3.  **本地仓库 (Repository)**：按下快门后，照片被永久保存的地方 (`git commit`)。
4.  **远程仓库 (Remote)**：云端相册，比如 GitHub (`git push`)。

---

## 🛠️ 实战演练：三步走

假设你已经完成了 [Ep01](./01-hello-world.md) 的初始化，现在我们来修改文件并提交。

### 第 1 步：修改文件 & 查看状态

*  首先，我们创建一个新文件，或者修改现有的文件。
```bash
echo "这是我的第一行代码" > hello.txt
```
*  查看状态（这是你最常用的命令！）
```bash
git status
```
> - **你会看到什么？**`hello.txt` 会显示为 红色 (Untracked)。
> - **这意味着** `Git` 发现了新文件，但你还没有把它放进胶卷。

### 第 2 步：添加到暂存区 (git add)

* 现在，我们要把文件放进“胶卷”里，准备拍照。
```bash
git add hello.txt
```
* 再次查看状态：
```bash
git status
```
> - 变化：`hello.txt` 变成了 绿色 (Changes to be committed)。
> - 这意味着：文件已就绪，等待拍照！
> - 💡 小技巧：如果你想把所有修改过的文件都加进去，可以用 `git add .`（注意最后的点前面有个空格）。

### 第 3 步：提交到本地仓库 (git commit)

* 文件已经在胶卷里了，现在按下“快门”，正式存档！
```bash
git commit -m "第一次提交：创建了 hello.txt"
```
* 命令解析
>  - `git commit`：执行提交。
>  - `-m`：代表 "message"（信息）。
>  - `"..."`：引号里是你的备注。一定要写清楚你做了什么！ 未来的你会感谢现在的自己。

* 成功标志：你会看到类似这样的输出
```bash
[main (root-commit) xxxxxxx] 第一次提交：创建了 hello.txt
1 file changed, 1 insertion(+)
create mode 100644 hello.txt
```

### 第 4 步：推送到远程仓库 (git push)
本地存档完成后，最后一步是把它同步到 GitHub 云端。
```bash
git push -u origin main
```
*(如果你的分支叫 master，就把 main 换成 master)

成功标志：看到进度条跑完，最后显示 branch 'main' set up to track...。

### 🐛 常见报错与解决

#### 1.忘记加 -m

 - **错误命令**：git commit "备注"
 - **报错**：error: pathspec ... did not match any file(s)
 - **原因**：Git 以为你在指定文件名，而不是写备注。
 - ✅ **修正：git commit -m "备注"**

#### 2.忘记 add 直接 commit
 - **现象**：运行 git commit 后，提示 nothing to commit, working tree clean。
 - **原因**：你没有把文件放进“胶卷”（暂存区），相机里是空的，当然拍不了照。
 - ✅ **修正：先运行 git add .，再运行 git commit。**

#### 3.拼写错误
- **错误**：git addd . 或 git commmit
- **结果**：command not found
- ✅ **修正：仔细检查拼写，Git 命令很严谨，多一个字母都不行。**

## 🎉 总结
### 恭喜！你已经掌握了 Git 的灵魂三招：
* git add -> 放进胶卷 (变绿)
* git commit -> 按下快门 (存档)
* git push -> 上传云端 (同步)

接下来，我们可以去配置 SSH，让推送过程不再需要输入密码！👉 前往 Ep03: 免密登录

[🔙 返回主页](../README.md)