# Vercel 部署指南

## 简介

本项目是一个基于 Docsify 的文档网站，包含了图解计算机基础的相关内容。本指南将帮助你将项目部署到 Vercel 公网。

## 部署步骤

### 1. 准备工作

- 一个 GitHub 账号
- 一个 Vercel 账号（可以使用 GitHub 账号登录）

### 2. 部署到 Vercel

1. 访问 [Vercel 官网](https://vercel.com/)
2. 使用 GitHub 账号登录
3. 点击 "New Project" 按钮
4. 从列表中选择 `rwangrwang31/CS-Base` 仓库
5. 点击 "Import" 按钮
6. Vercel 会自动检测到项目配置（vercel.json）
7. 点击 "Deploy" 开始部署
8. 等待几分钟，部署完成后会提供一个公网访问链接

### 3. 自定义域名（可选）

部署完成后，Vercel 会提供一个类似 `cs-base-xxx.vercel.app` 的域名。如果你有自己的域名，可以在 Vercel 项目设置中添加自定义域名。

## 项目配置说明

本项目包含以下配置文件：

### vercel.json

Vercel 的部署配置文件，定义了项目名称和版本。

```json
{
  "version": 2,
  "name": "cs-base"
}
```

Vercel 会自动检测静态文件并进行部署，无需额外的构建和路由配置。

### .nojekyll

这个空文件告诉 Vercel 和 GitHub Pages 不要使用 Jekyll 处理文件，这对 Docsify 项目是必需的。

### _sidebar.md

侧边栏导航配置文件，定义了网站的导航结构。

### index.html

主页面，包含了 Docsify 的配置：
- 项目名称
- GitHub 仓库链接
- 侧边栏设置
- 搜索功能
- 其他插件

## 本地预览

如果你想在本地预览网站，可以使用以下方法：

### 方法 1: 使用 Python HTTP 服务器

```bash
cd /path/to/CS-Base
python3 -m http.server 8080
```

然后在浏览器中访问 `http://localhost:8080`

### 方法 2: 使用 Docsify CLI

```bash
# 安装 docsify-cli
npm install -g docsify-cli

# 启动本地服务器
cd /path/to/CS-Base
docsify serve .
```

然后在浏览器中访问 `http://localhost:3000`

## 更新内容

部署后，每次你向 GitHub 仓库推送更新时，Vercel 会自动重新部署网站。

## 故障排除

### 网站无法访问

- 检查 Vercel 部署日志，查看是否有错误
- 确保 `vercel.json` 配置正确
- 确保所有必需的文件都已提交到仓库

### 侧边栏不显示

- 确保 `_sidebar.md` 文件存在
- 检查 `index.html` 中的 `loadSidebar: true` 配置
- 检查侧边栏中的链接路径是否正确

### 样式或功能异常

- 检查 CDN 链接是否可访问
- 清除浏览器缓存重试
- 检查浏览器控制台是否有错误信息

## 技术栈

- **Docsify**: 文档网站生成器
- **Vercel**: 静态网站托管平台
- **GitHub**: 代码托管

## 参考链接

- [Docsify 官方文档](https://docsify.js.org/)
- [Vercel 官方文档](https://vercel.com/docs)
- [原项目地址](https://github.com/xiaolincoder/CS-Base)
