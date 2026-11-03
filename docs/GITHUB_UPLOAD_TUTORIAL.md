# 📤 手把手把本项目上传到 GitHub 教程

本教程面向**第一次传 GitHub** 的朋友，一步一步来，照着做就行。目标：把你桌面上的
这个文件夹 `C:\Users\User\Desktop\zabbix-icmp-ping-dns` 变成一个公开的 GitHub
仓库，别人点开就能看到漂亮的 README 和截图。

> 好消息：所有截图、模板文件、说明文档**已经都在这个文件夹里了**，你只需要把它们
> “搬”到 GitHub 上即可，不用再准备任何东西。README 里用相对路径引用了
> `docs/screenshots/*.png`，上传后会**自动显示图片**，无需额外操作。

---

## 一、准备工作

1. 一个 GitHub 账号（没有就去 https://github.com/signup 免费注册）。
2. 本机准备好要上传的文件夹：
   `C:\Users\User\Desktop\zabbix-icmp-ping-dns`
   （确认里面有 `README.md`、`templates/`、`docs/screenshots/` 等）。
3. 选择一种上传方式（推荐**方法一 Git 命令行**，最稳；嫌命令行麻烦可选**方法二
   GitHub Desktop** 图形界面）。

---

## 二、方法一：Git 命令行（推荐，最稳）

### 第 1 步：安装 Git
- 下载：https://git-scm.com/downloads ，一路默认安装。
- 安装完打开 **Git Bash**（开始菜单搜 “Git Bash”）。
- 验证：在 Git Bash 输入 `git --version`，能看到版本号就成功了。

### 第 2 步：配置你的身份（只需一次）
在 Git Bash 里执行（把引号里换成你自己的名字和邮箱，要跟 GitHub 账号一致）：

```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱@example.com"
```

### 第 3 步：进入项目文件夹并初始化
```bash
cd "/c/Users/User/Desktop/zabbix-icmp-ping-dns"
git init
git add .
git commit -m "Initial commit: ICMP Ping DNS Zabbix template"
```

> 说明：`cd` 后面的路径就是桌面那个文件夹；`git add .` 会把里面**所有内容**
> （含子文件夹 `templates/`、`docs/`、`docs/screenshots/`）一起加入。
> `.gitignore` 已自动排除无关文件。

### 第 4 步：在 GitHub 网页上新建仓库
1. 浏览器打开 https://github.com/new
2. **Repository name（仓库名）** 填：`zabbix-icmp-ping-dns`
   （这个名字会显示在地址栏，建议和文件夹同名）
3. **Description（描述）** 填：
   `DNS-driven ICMP monitoring template for Zabbix 7.0 — auto-discover & ping every IP a host resolves to.`
4. 选 **Public（公开）**（想让其他人用就得选公开）。
5. **不要**勾选 “Add a README” / “Add .gitignore” / “Add license”——我们本地已经有了，
   勾了反而冲突。
6. 点击 **Create repository**。

### 第 5 步：把本地仓库推送到 GitHub
创建后会进入一个页面，复制它给出的两行命令（在 “**…or push an existing repository
from the command line**” 下面）。类似这样，在 Git Bash 里粘贴执行：

```bash
git branch -M main
git remote add origin https://github.com/你的用户名/zabbix-icmp-ping-dns.git
git push -u origin main
```

- 第一次推送会弹窗让你登录 GitHub（或让你输入用户名 + 密码/令牌）。
  - 如果要求输入密码但报错，说明 GitHub 已不支持账号密码，需要用
    **Personal Access Token（令牌）** 当密码。生成方法见文末“常见问题”。
- 看到 `main -> main` 和 `done` 就成功了。

### 第 6 步：回到浏览器刷新仓库页面
你会看到 `README.md` 已渲染成漂亮的页面，往下翻能看到所有**截图自动显示**。🎉

---

## 三、方法二：GitHub Desktop（图形界面，零命令）

适合不想敲命令的朋友。

1. 下载安装：https://desktop.github.com/
2. 登录你的 GitHub 账号。
3. 顶部菜单 **File → Add local repository**（添加本地仓库）。
4. 选择文件夹 `C:\Users\User\Desktop\zabbix-icmp-ping-dns`。
   - 如果提示 “This directory does not appear to be a git repository”，点
     **Create a repository** 把它初始化（建议勾选 “Keep this code in
     zabbix-icmp-ping-dns”）。
5. 左下角 **Summary** 填 `Initial commit`，点 **Commit to main**。
6. 点右上角 **Publish repository**（发布仓库）：
   - Name 填 `zabbix-icmp-ping-dns`
   - Description 同上文
   - 勾选 **Keep this code private** 的**反方向**——即保持**不勾选**以公开
   - 点 **Publish**
7. 发布完成后，点 **View on GitHub** 即可打开网页查看。

---

## 四、方法三：网页直接拖拽上传（不推荐，仅应急）

GitHub 网页每个仓库有 **Add file → Upload files**，可以拖文件进去。但这种方式
**不能保留文件夹层级**（会把 `docs/screenshots/` 里的图片拍平），README 里的相对
路径会失效、图片显示不出来。所以**只建议临时补一两个文件用**，首次上传请用方法一
或二。

---

## 五、上传后，让仓库更吸引人（几分钟搞定）

1. **设仓库描述与话题（Topics）**：仓库主页右侧 → About → 点齿轮：
   - 填一句话描述。
   - Topics 添加：`zabbix`、`zabbix-template`、`monitoring`、`icmp`、`dns`、
     `network-monitoring`、`devops`。这能让别人在 GitHub 搜到你的项目。
2. **确认 License**：本仓库已带 `LICENSE`（GPL-2.0），GitHub 会自动识别并在
   仓库右侧显示许可证图标。
3. **社交预览图（可选但很加分）**：仓库主页 → Settings → Social preview → 上传一张
   有代表性的截图（比如 `docs/screenshots/10-latest-data.png`），别人分享链接时
   会显示这张图。
4. **置顶 README**：GitHub 会自动把 `README.md` 渲染在仓库首页，无需额外操作。
5. **加 Star / 分享**：自己先点个 Star，再把链接发到 Zabbix 中文社区、技术论坛、
   V2EX、知乎等，吸引用户。

---

## 六、常见问题

**Q1：推送时要求输入密码但总失败？**
GitHub 已停用账号密码登录，需要用 **Personal Access Token (PAT)** 代替密码：
1. 打开 https://github.com/settings/tokens → **Generate new token (classic)**。
2. 勾选 `repo`（全选该组），设置有效期，点 Generate。
3. **立刻复制**那串令牌（只显示一次）。
4. 推送时用户名填 GitHub 账号，**密码处粘贴这个令牌**。

**Q2：公司网络很慢 / 推不上去？**
可改用 GitHub Desktop（方法二），它对网络更友好；或检查代理设置。

**Q3：想改仓库名 / 转私有？**
仓库主页 → Settings → 最下方 **Rename** 或 **Change visibility**。

**Q4：以后模板更新了怎么同步？**
在 Git Bash 进入文件夹，执行：
```bash
git add .
git commit -m "更新说明"
git push
```

**Q5：README 里的图片没显示？**
确认图片确实在 `docs/screenshots/` 目录下，且 README 里写的是相对路径
`docs/screenshots/xxx.png`。本仓库已经按这个结构放好了，正常上传即可显示。

---

## 七、一句话总结

> 本地文件夹已经齐活 → 用 Git 或 GitHub Desktop 推到 GitHub → 新建公开仓库
> `zabbix-icmp-ping-dns` → 填好描述与话题 → 分享链接。

祝你收获第一个 Star！⭐
