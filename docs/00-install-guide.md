📥 附录：Git 安装与配置全指南 (2026 最新版)
💡 写在前面：很多新手在安装时对着几十个英文选项发呆，或者随便点“Next”导致后续命令报错。别担心，跟着下面的步骤走，保证一次成功！
1️⃣ 下载 Git
请始终从官方网站下载，确保软件安全且版本最新。
官方网站: https://git-scm.com/downloads
国内加速下载 (如果官网太慢): https://registry.npmmirror.com/binary.html?path=git-for-windows/ (淘宝镜像)
👉 操作：进入网站后，它会自动识别你的系统。点击大大的 Download 按钮（例如 Download for Windows）。
2️⃣ 安装步骤 (Windows 篇 - 重点！)
下载完成后，双击 .exe 安装包。注意：不要全程无脑点 Next，以下几个关键步骤请仔细看！
表格
步骤	界面标题	✅ 推荐设置	💡 为什么要这样选？
1	Select Components	保持默认，但勾选 Add a Git Bash Profile to Windows Terminal	让你能在酷炫的 Windows Terminal 里直接用 Git。
2	Choosing Default Editor	推荐使用 VS Code (如果已安装)
或者保持默认的 Vim	Vim 对新手太难退出！选 VS Code 或 Notepad++ 会更友好。
3	Adjusting PATH...	✅ 推荐选第二项:
Git from the command line and also from 3rd-party software	最重要的一步！ 这样才能在任意文件夹右键打开终端使用 git 命令。
4	Configuring Line Endings	✅ 推荐选第一项:
Checkout Windows-style, commit Unix-style	防止因为换行符不同，导致你和 Mac/Linux 队友协作时报错。
5	Configuring Terminal Emulator	选择 Use MinTTY (默认)	这是 Git Bash 自带的终端，兼容性最好。
6	Extra Options	勾选 Enable file system caching	提升大项目下的 Git 速度。
⚠️ 避坑指南：
如果你在第 3 步选了第一项（Only use Git from...），那你以后每次用 git 都得打开特定的 Git Bash 窗口，不能在 PowerShell 里用，非常麻烦！一定要选第二项！
安装路径建议保持默认 C:\Program Files\Git，千万不要包含中文路径，否则会出现莫名其妙的乱码错误。
3️⃣ 安装步骤 (Mac 篇)
Mac 用户有两种选择：
方法 A：使用 Homebrew (推荐)
如果你已经安装了 Homebrew，一行命令搞定：
bash

编辑



brew install git
方法 B：下载安装包
访问 git-scm.com/downloads。
点击 Download for macOS。
双击下载的 .dmg 文件，按照提示一路点击“继续”即可。
4️⃣ 验证安装 & 身份配置 (必做！)
安装完成后，Git 还不知道“你是谁”。如果不配置，你提交代码时会报错，或者显示奇怪的计算机名。
第一步：打开终端
Windows: 在桌面右键，选择 Open Git Bash here 或者在开始菜单搜索 Git Bash。
Mac: 打开 Terminal (终端)。
第二步：输入以下命令检查版本
bash

编辑



git --version
如果输出了类似 git version 2.47.0.windows.1，说明安装成功！🎉
第三步：配置你的名字和邮箱 (全局配置)
⚠️ 注意：这里的邮箱建议和你 GitHub/Gitee 注册的邮箱 一致，这样你的贡献图才会变绿！
bash

编辑



# 1. 设置用户名 (引号内改成你的名字，可以是中文)
git config --global user.name "mrdmrddld"

# 2. 设置邮箱 (引号内改成你的邮箱)
git config --global user.email "your-email@example.com"

# 3. 检查是否配置成功
git config --list
如果在输出列表中看到了刚才设置的 name 和 email，恭喜你，环境彻底准备好了！🚀
5️⃣ 常见问题 (FAQ)
Q: 输入 git 提示“不是内部或外部命令”？
A: 99% 是因为安装时的 PATH 选项 没选对（见上文步骤 3）。
解决: 重新运行安装包，选择 Repair (修复)，然后在 PATH 步骤务必选择 第二项。
Q: 为什么我的邮箱要填对的？
A: Git 是通过邮箱来关联作者身份的。如果你填错了，GitHub 就不知道这段代码是你写的，你的头像就不会出现在贡献者列表里，贡献图也不会变绿。
Q: Mac 用户提示 xcode-select 错误？
A: 这是因为缺少命令行工具。运行 xcode-select --install 并按照弹窗提示安装即可。