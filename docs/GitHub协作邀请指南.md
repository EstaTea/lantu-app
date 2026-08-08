# 邀请太太加入 GitHub 私有仓库协作指南

## 前置条件
- 太太需要有一个 GitHub 账号。如果没有，先在 https://github.com 注册一个（免费）。
- 记下她的 GitHub 用户名（username），比如 `xiaomei` 这样的。

## 邀请步骤（你来操作）

### 方式一：通过网页（最简单）

1. **打开仓库页面**
   访问 https://github.com/EstaTea/lantu-app

2. **进入 Settings**
   点击仓库顶部的 **⚙️ Settings** 选项卡

3. **找到 Collaborators**
   - 左侧菜单找到 **Access** 下的 **Collaborators**
   - 或者直接访问：https://github.com/EstaTea/lantu-app/settings/access

4. **Add people**
   - 点击绿色的 **Add people** 按钮
   - 输入太太的 GitHub 用户名或邮箱
   - 选择权限级别：
     * **Write** —— 推荐（可以 push/pull，不能改仓库设置）
     * **Maintain** —— 高级（可以管理 Issues、PR，但不能删库）
     * **Admin** —— 完全控制（慎用）
   - 点击 **Add [username] to this repository**

5. **等待接受**
   - GitHub 会给太太发送邀请邮件
   - 她需要点击邮件里的链接接受邀请
   - 或者她登录 GitHub 后会在首页看到邀请通知

### 方式二：通过 gh cli（命令行）

如果你更熟悉命令行：

```bash
# 邀请太太（把 xiaomei 换成她的 GitHub 用户名）
gh api repos/EstaTea/lantu-app/collaborators/xiaomei -X PUT -f permission=push
```

权限选项：
- `pull` —— 只读
- `push` —— 读写（推荐）
- `maintain` —— 维护者
- `admin` —— 管理员

## 太太接受邀请后的操作

### 1. 克隆仓库到她的电脑

**如果她用 WorkBuddy：**
- 在 WorkBuddy 里说："帮我克隆 GitHub 仓库 EstaTea/lantu-app"
- 或者自然语言："打开兰途项目"

**如果她用命令行：**
```bash
cd ~/WorkBuddy  # 或者她想要的目录
git clone https://github.com/EstaTea/lantu-app.git
cd lantu-app
```

### 2. 日常协作流程（给太太看）

**每次开始工作前（拉取你的最新改动）：**
```bash
git pull origin main
```

或者在 WorkBuddy 里说："拉取兰途项目的最新代码"

**改完东西后（推送她的改动）：**
```bash
git add .
git commit -m "修改了xxx"
git push origin main
```

或者在 WorkBuddy 里说："把我的改动推送到 GitHub"

### 3. 避免冲突的协作约定（重要！）

根据项目记忆里的约定：
- **你**主要改 `prototype/index.html` 的结构和逻辑
- **太太**主要改 `docs/` 里的文档和原型的文案内容
- 尽量不同时改同一个文件
- 改之前先 `git pull` 拉取最新版
- 如果遇到冲突，WorkBuddy 可以帮她解决

## 常见问题

**Q: 邀请链接在哪？**
A: GitHub 会自动发邮件。如果没收到，让她登录 GitHub 首页，顶部会有通知图标。

**Q: 她不会用 Git 怎么办？**
A: WorkBuddy 可以帮她。她只需要在 WorkBuddy 里用自然语言说"拉取最新代码"、"提交我的改动"就行，AI 会自动翻译成 Git 命令。

**Q: 如果我们同时改了同一个文件会怎样？**
A: Git 会提示冲突。WorkBuddy 能帮你们自动合并或手动选择保留哪个版本。

**Q: 我能看到她改了什么吗？**
A: 能。每次 push 后在 https://github.com/EstaTea/lantu-app/commits/main 可以看到所有提交历史。

## 下一步

1. 你先在网页上邀请她（方式一）
2. 把这个文档发给她，或者直接在她电脑的 WorkBuddy 里说："帮我接受兰途项目的 GitHub 协作邀请"
3. 她接受后，你们就可以开始双人协作了 🎉
