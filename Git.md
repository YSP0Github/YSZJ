### 克隆远程仓库到本地
1. **复制远程仓库地址**
   在 GitHub 上进入目标仓库页面，点击“Code”按钮，复制 HTTPS 地址（例如 https://github.com/username/repository.git）。

2. **打开 Git Bash**
   在本地计算机上，进入你希望存放仓库的文件夹（可以使用 cd 路径 导航），然后右键选择“Git Bash Here”或直接打开 Git Bash 终端。

3. **克隆仓库**
   输入以下命令：
   git clone <URL>
   - <URL> 是你在第一步复制的 HTTPS 地址。
   - 执行后，当前文件夹下会生成一个与远程仓库同名的文件夹，包含所有文件和提交历史。

4. **进入仓库目录**
   使用命令：
   cd <repository-name>
   进入刚刚克隆的文件夹，开始后续操作。

---

### 将本地修改推送至 GitHub
如果你在本地修改了文件，想要将这些更改同步到 GitHub，可以按照以下步骤操作：

1. **初始化 Git 仓库（可选）**
   git init
   - 这个命令在当前目录初始化一个新的 Git 仓库。
   - 注意：如果已经通过 git clone 创建了仓库，则无需再次运行此命令，因为克隆的仓库已经是一个 Git 仓库。

2. **添加修改到暂存区**
   git add .
   - 这会将当前目录下所有修改（包括新增、修改、删除的文件）添加到暂存区。
   - 替代选项：如果你只想添加特定文件，可以用 git add <文件名>。

3. **拉取远程最新内容（避免冲突）**
   git pull
   - 从远程仓库拉取最新更改到本地，确保本地与远程同步。
   - 注意：如果本地有未提交的修改，可能会出现冲突，需先提交或暂存本地更改（见下一步）。

4. **提交更改到本地仓库**
   git commit -m "提交信息"
   - 将暂存区的修改提交到本地仓库。
   - "提交信息" 应简洁描述此次更改的内容，例如 "add new feature" 或 "fix bug"。

5. **推送更改到远程仓库**
   git push
   - 将本地仓库的提交上传到 GitHub。
   - 如果是第一次推送，可能需要指定远程分支，例如：
     git push origin main
     （main 是默认分支名，视仓库设置可能是 master 或其他名称）。

---

### 将本地项目上传至 GitHub
如果你有一个本地项目，想将其上传到 GitHub，需要先创建远程仓库并建立关联。以下是完整步骤：

1. **在 GitHub 上创建新仓库**
   - 登录 GitHub，点击右上角的“+”号，选择“New repository”。
   - 输入仓库名称，选择公开（Public）或私有（Private），然后点击“Create repository”。
   - 注意：创建时不要勾选“Initialize this repository with a README”，除非你想从远程开始。

2. **初始化本地 Git 仓库**
   在本地项目文件夹中打开 Git Bash，输入：
   git init

3. **添加文件到暂存区**
   git add .
   - 将项目中的所有文件添加到暂存区。

4. **提交到本地仓库**
   git commit -m "Initial commit"
   - 提交所有文件，标记为初始提交。

5. **关联远程仓库**
   复制 GitHub 新仓库的 HTTPS 地址，然后输入：
   git remote add origin <URL>
   - <URL> 是 GitHub 仓库的地址，例如 https://github.com/username/repository.git。
   - origin 是远程仓库的默认别名。

6. **推送项目到 GitHub**
   git push -u origin main
   - -u 表示设置默认上游分支，以后只需 git push 即可。
   - main 是默认分支名，如果你的分支名不同，请替换为实际名称。

---

### 注意事项
- **身份验证**：首次推送时，可能需要登录 GitHub 或使用 Personal Access Token（PAT）进行身份验证。
- **冲突解决**：如果 git pull 或 git push 出现冲突，需手动合并文件或使用 git stash 暂存本地更改。
- **分支管理**：默认操作基于主分支（如 main），如需使用其他分支，可用 git checkout -b <分支名> 创建并切换。
- **检查状态**：随时使用 git status 查看当前仓库状态。