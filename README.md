# 随机小姐姐视频播放器

一个响应式的随机视频播放器，支持移动端手势操作和自动连播功能。

## 功能特性

- 🎥 随机播放视频内容
- 📱 移动端优化，支持触摸手势
- 🔄 自动连播功能
- 🔇 静音/取消静音控制
- ⚡ 视频预加载优化
- 🎨 现代化UI设计
- 📺 桌面端和移动端自适应

## 部署到 Cloudflare Pages

### 方法一：通过 Git 仓库部署

1. 将代码推送到 GitHub 仓库
2. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
3. 进入 Pages 页面，点击 "Create a project"
4. 选择 "Connect to Git"
5. 选择您的 GitHub 仓库
6. 配置构建设置：
   - **Framework preset**: None
   - **Build command**: 留空
   - **Build output directory**: `/`
7. 点击 "Save and Deploy"

### 方法二：直接上传文件

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 进入 Pages 页面，点击 "Create a project"
3. 选择 "Upload assets"
4. 上传项目文件夹
5. 设置项目名称并部署

### 方法三：使用 Wrangler CLI

```bash
# 安装 Wrangler CLI
npm install -g wrangler

# 登录 Cloudflare
wrangler login

# 部署项目
wrangler pages publish . --project-name=random-video-player
```

## 本地开发

```bash
# 启动本地服务器
npm run dev

# 或者直接使用 Python
python3 -m http.server 8000
```

然后在浏览器中访问 `http://localhost:8000`

## 项目结构

```
.
├── index.html          # 主页面文件
├── package.json        # 项目配置
├── README.md          # 项目说明
└── _headers           # Cloudflare Pages 头部配置（可选）
```

## 使用说明

### 桌面端
- 点击视频暂停/播放
- 使用底部控制按钮切换功能

### 移动端
- 点击视频暂停/播放
- 上滑切换到下一个视频
- 使用底部控制按钮

### 控制按钮
- **自动连播**: 开启后视频结束会自动播放下一个
- **下个视频**: 手动切换到下一个视频
- **开启静音**: 切换音频开关

## 自定义配置

您可以在 `index.html` 中修改以下配置：

- **API_URLS**: 修改视频源API列表
- **样式**: 调整CSS样式以匹配您的品牌
- **功能**: 添加或移除功能按钮

## 技术栈

- HTML5 Video API
- CSS3 动画和响应式设计
- 原生 JavaScript
- Touch Events API（移动端手势）

## 浏览器支持

- Chrome/Edge 60+
- Firefox 55+
- Safari 11+
- 移动端浏览器

## 许可证

MIT License