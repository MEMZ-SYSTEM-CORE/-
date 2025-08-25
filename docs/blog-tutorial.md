# 搭建个人博客教程

本教程将指导你如何使用Docsify搭建一个个人博客网站，就像你现在看到的这个一样。

## 准备工作

在开始之前，确保你的计算机上已经安装了以下软件：
- Node.js (建议使用最新稳定版本)
- npm (通常随Node.js一起安装)

## 安装Docsify

1. 打开命令行工具（Windows用户可以使用PowerShell或CMD）
2. 运行以下命令全局安装Docsify CLI工具：

```bash
npm install -g docsify-cli
```

## 创建博客项目

1. 创建一个新的项目目录：

```bash
mkdir my-blog
cd my-blog
```

2. 初始化Docsify项目：

```bash
docsify init ./docs
```

这会在你的项目中创建一个docs文件夹，包含以下文件：
- index.html: 网站入口文件
- README.md: 主页面内容
- _sidebar.md: 侧边栏配置

## 自定义博客配置

### 1. 配置index.html

打开docs/index.html文件，你会看到类似以下内容：

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
  <meta name="description" content="Description">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0">
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">
</head>
<body>
  <div id="app"></div>
  <script>
    window.$docsify = {
      name: '',
      repo: ''
    }
  </script>
  <!-- Docsify v4 -->
  <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
</body>
</html>
```

你可以根据需要修改标题、描述等信息。

### 2. 编写首页内容

编辑docs/README.md文件，这是你的博客首页。你可以添加欢迎信息、博客介绍等内容。

### 3. 配置侧边栏

编辑docs/_sidebar.md文件来配置侧边栏导航。例如：

```markdown
- [首页](README.md)
- [文章一](article1.md)
- [文章二](article2.md)
```

## 启动本地服务器

在项目根目录运行以下命令启动本地开发服务器：

```bash
docsify serve docs
```

然后在浏览器中访问 http://localhost:3000 查看你的博客。

## 添加新文章

要添加新文章，只需在docs文件夹中创建新的Markdown文件，然后在_sidebar.md中添加相应的链接即可。

例如，创建一个名为"first-post.md"的文件：

```markdown
# 我的第一篇博客

这是我的第一篇博客文章内容。
```

然后在_sidebar.md中添加：

```markdown
- [首页](README.md)
- [我的第一篇博客](first-post.md)
```

## 部署博客

### 部署到GitHub Pages

1. 在GitHub上创建一个新的仓库
2. 将你的项目推送到GitHub：

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/你的用户名/仓库名.git
git push -u origin main
```

3. 在GitHub仓库的Settings页面，找到"Pages"选项
4. 选择"Deploy from a branch"，然后选择main分支和/docs文件夹
5. 保存设置，GitHub会自动部署你的博客

### 部署到其他平台

你也可以将博客部署到Netlify、Vercel等其他静态网站托管平台。

## 自定义主题

Docsify提供了多种主题供你选择：

- vue.css (默认)
- buble.css
- dark.css
- pure.css

要更换主题，只需修改index.html中的CSS链接：

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/dark.css">
```

你也可以创建自定义CSS文件来进一步个性化你的博客外观。

## 添加插件

Docsify支持多种插件来增强博客功能：

### 搜索插件

```html
<script src="//cdn.jsdelivr.net/npm/docsify@4/lib/plugins/search.min.js"></script>
```

### 图片缩放插件

```html
<script src="//cdn.jsdelivr.net/npm/docsify@4/lib/plugins/zoom-image.min.js"></script>
```

### 字数统计插件

```html
<script src="//cdn.jsdelivr.net/npm/docsify@4/lib/plugins/count.min.js"></script>
```

将这些插件添加到index.html文件中相应的位置即可。

## 总结

通过以上步骤，你就可以搭建一个功能完整的个人博客网站。Docsify的优点是无需构建过程，只需编写Markdown文件即可创建美观的文档网站。

随着你的博客内容增加，你可以继续添加新的文章，自定义主题和插件，让你的博客更加个性化和功能丰富。