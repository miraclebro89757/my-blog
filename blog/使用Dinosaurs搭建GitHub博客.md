
本教程为一次通关系列✅，作者亲自实操，实效性随着发布时间增加可能会失效，新鲜出炉请尽快食用。

### 1. 安装 Node.js 和 npm
- 检查是否安装 Node.js：`node -v` ，要求版本>18.0
- 如未安装或版本过低，从 [Node.js 官网](https://nodejs.org/) 下载并安装升级。

### 2. 初始化项目
- 新建一个本地blog文件夹，进入文件夹后在命令行中运行：
  ```bash
npm init docusaurus@latest my-website classic
  ```

### 3. 配置项目
- 进入项目目录并安装依赖：
  ```bash
  cd my-website 
  npm install
  ```
- 启动开发服务器以检查项目是否正常运行：
  ```bash
  npm start
  ```

### 4.查看本地页面
- 打开浏览器访问 `http://localhost:3000` 查看默认页面，下图为成功截图。![[Pasted image 20250113144715.png]]

### 5. 创建 GitHub 仓库并关联
- 在 GitHub 上创建一个新的仓库，命名为 `my-blog`(注意不要创建LICENSE 等文件，就一个空的仓库就行，点错创建了其他文件可以直接删掉)，点击下图复制你的GitHub仓库地址。![[Pasted image 20250113145034.png]]
- 在本地项目目录中初始化 Git 并关联远程仓库（注意origin后面是你上面复制的GitHub仓库地址）：
  ```bash
  git init
  git remote add origin https://github.com/username/my-blog.git
  ```

### 6. 配置 GitHub Pages
- 安装 `gh-pages`：
  ```bash
  npm install --save-dev gh-pages
  ```
- 在 `package.json` 中添加部署脚本：
  ```json
  "scripts": {
    "deploy": "docusaurus deploy"
  }
  ```
- 检查项目的根目录下`.github/workflows/deploy.yml`的权限是否正确
```yml
permissions:#必须有下面这两行，否则部署时会报错权限不足
	contents: write
	pages: write
```
### 7. 提交代码并部署
- 提交初始代码：
  ```bash
  git add .
  git commit -m "Initial commit"
  git push -u origin main
  ```
### 8. 启用 GitHub Pages
- 在仓库新建`gh-pages`分支![[Pasted image 20250113152251.png]]
- 进入 GitHub 仓库设置，找到 GitHub Pages 部分。
- 选择分支和路径，通常是 `gh-pages` 分支。

### 9. 写博客文章
- 在 `blog` 目录下创建新的 Markdown 文件，编写文章内容。
- 保存后，运行 `npm start` 查看本地预览。
- 提交代码并部署更新：
  ```bash
  git add .
  git commit -m "Add new blog post"
  git push
  npm run deploy
  ```

### 10. 配置域名和主题
- 如有域名，配置 GitHub Pages 的自定义域名，可以购买域名后再做。
- 根据需要配置主题和插件，以增强博客功能和美观度，官方目前只有经典模版，其他的模版暂未推出，也不建议魔改。
