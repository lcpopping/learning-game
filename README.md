# 学习大闯关 - GitHub Pages 部署教程

## 目录
1. [准备工作](#准备工作)
2. [创建 GitHub 仓库](#创建-github-仓库)
3. [上传代码](#上传代码)
4. [启用 GitHub Pages](#启用-github-pages)
5. [手机安装 App](#手机安装-app)
6. [更新游戏](#更新游戏)

---

## 准备工作

### 需要准备的东西
- 一个 GitHub 账号（免费注册：https://github.com/）
- 电脑上的文件夹（就是放这个游戏的文件夹）

### 检查 Git 是否安装
打开"命令提示符"（Windows按 Win+R，输入 cmd，回车），输入：
```
git --version
```
如果显示类似 `git version 2.x.x` 就说明安装了。

如果没有安装，下载：https://git-scm.com/download/win

---

## 创建 GitHub 仓库

### 步骤 1：登录 GitHub
打开浏览器访问 https://github.com ，登录你的账号。

### 步骤 2：创建新仓库
1. 点击右上角的 "+" → "New repository"
2. 按下图填写：

```
Repository name: learning-game
Description: 学习大闯关 - 收集奥特曼和三国人物！
```

3. 选择 **Public**（公开）
4. **不要**勾选 "Add a README file"（我们已有）
5. 点击 "Create repository"

### 步骤 3：记住仓库地址
创建成功后，页面显示类似：
```
https://github.com/你的用户名/learning-game
```
**把"你的用户名"换成你实际的用户名，记住这个地址！**

---

## 上传代码

### 步骤 1：打开命令提示符
Windows 按 Win+R，输入 `cmd`，回车。

### 步骤 2：进入游戏文件夹
假设你的游戏文件夹在桌面，学习大闯关 文件夹里。
```
cd Desktop\学习大闯关
```
如果不知道路径，先打开文件夹，看地址栏复制路径。

### 步骤 3：初始化 Git
```
git init
```

### 步骤 4：添加所有文件
```
git add .
```

### 步骤 5：提交（相当于确认保存）
```
git commit -m "Initial commit - 学习大闯关游戏"
```

### 步骤 6：连接 GitHub 仓库
**把下面的"你的用户名"换成你实际的 GitHub 用户名！**
```
git remote add origin https://github.com/你的用户名/learning-game.git
```

### 步骤 7：上传代码
```
git push -u origin main
```

第一次推送可能会要求登录 GitHub，按提示输入用户名和密码（或 Token）即可。

**上传成功后，会显示类似：**
```
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
...
To https://github.com/你的用户名/learning-game.git
 * [new branch]     main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

---

## 启用 GitHub Pages

### 步骤 1：打开仓库设置
在 GitHub 仓库页面，点击顶部的 "Settings"（设置）。

### 步骤 2：找到 GitHub Pages
往下滑，找到 "GitHub Pages" 部分。

### 步骤 3：配置
- Source（来源）：选择 **Deploy from a branch**
- Branch（分支）：选择 **main**
- Folder（文件夹）：选择 **/ (root)**

### 步骤 4：获取访问地址
等待 1-2 分钟，页面会显示：
```
Your site is published at https://你的用户名.github.io/learning-game/
```

**这就是你的游戏网址！**

---

## 手机安装 App

### 步骤 1：访问网址
用手机浏览器（推荐 Chrome 或 Safari）打开上面的地址。

### 步骤 2：添加到主屏幕
- **iPhone Safari**：点击底部"分享"按钮 → "添加到主屏幕"
- **安卓 Chrome**：点击右上角菜单 → "添加到主屏幕"

### 步骤 3：完成
桌面上会出现学习大闯关的图标，点击就能像 App 一样打开！

---

## 更新游戏

如果修改了游戏代码，想更新到网上：

### 步骤 1：修改代码
用记事本或 VS Code 编辑 `index.html` 等文件。

### 步骤 2：上传更新
打开命令提示符，进入文件夹，输入：
```
git add .
git commit -m "更新说明"
git push
```

### 步骤 3：等待生效
等 1-2 分钟，刷新网址即可看到更新。

---

## 常见问题

### Q: 推送时要求输入用户名密码？
这是 GitHub 要求使用 Personal Access Token。解决方法：
1. GitHub → Settings → Developer settings → Personal access tokens → Generate new token
2. 勾选 "repo" 权限
3. 生成后复制 Token（只显示一次！）
4. 推送时密码输入这个 Token

### Q: 上传失败？
检查网络连接，确保已连接 GitHub。

### Q: 网站打不开？
等 2-5 分钟让 GitHub Pages 生成完成。

### Q: 想换主题颜色？
编辑 `index.html` 中的 `:root` 部分：
```css
:root {
    --primary: #6C5CE7;  /* 改成你喜欢的颜色 */
}
```

---

## 文件说明

| 文件 | 作用 |
|------|------|
| index.html | 游戏主文件（包含所有代码） |
| manifest.json | PWA 配置文件 |
| sw.js | 离线缓存（让游戏离线也能玩） |
| README.md | 说明文档 |

**只需要上传这 4 个文件即可！**
