# 🚀 Cloudflare Pages 部署指南

## 快速部署（推荐）

### 方法一：使用部署脚本
```bash
# 给脚本执行权限（已完成）
chmod +x deploy.sh

# 运行部署脚本
./deploy.sh

# 或指定自定义项目名称
./deploy.sh my-video-player
```

### 方法二：手动使用 Wrangler CLI
```bash
# 1. 安装 Wrangler CLI
npm install -g wrangler

# 2. 登录 Cloudflare
wrangler login

# 3. 部署项目
wrangler pages publish . --project-name=random-video-player
```

## 详细部署步骤

### 准备工作
1. 确保您有 Cloudflare 账户
2. 安装 Node.js (推荐 v16+)

### 通过 Git 仓库部署
1. **创建 Git 仓库**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Random video player"
   git remote add origin https://github.com/yourusername/random-video-player.git
   git push -u origin main
   ```

2. **在 Cloudflare Dashboard 中设置**
   - 访问 [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - 进入 "Pages" 页面
   - 点击 "Create a project"
   - 选择 "Connect to Git"
   - 选择您的 GitHub 仓库
   - 构建设置：
     - **Framework preset**: None
     - **Build command**: 留空
     - **Build output directory**: `/`
   - 点击 "Save and Deploy"

### 直接文件上传部署
1. 访问 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 进入 "Pages" 页面
3. 点击 "Create a project"
4. 选择 "Upload assets"
5. 将整个项目文件夹拖拽上传
6. 设置项目名称并部署

## 本地测试

```bash
# 启动本地开发服务器
npm run dev

# 或使用 Python
python3 -m http.server 8000
```

访问 `http://localhost:8000` 测试功能

## 自定义域名

部署成功后，您可以：
1. 在 Cloudflare Pages 项目设置中添加自定义域名
2. 配置 DNS 记录
3. 启用 HTTPS（自动）

## 环境变量（如需要）

如果您需要配置环境变量：
1. 在 Cloudflare Pages 项目设置中
2. 进入 "Settings" > "Environment variables"
3. 添加所需的环境变量

## 性能优化

项目已包含以下优化：
- ✅ 静态资源缓存配置 (`_headers`)
- ✅ 安全头部设置
- ✅ 视频预加载优化
- ✅ 移动端性能优化

## 故障排除

### 常见问题
1. **部署失败**
   - 检查 Wrangler CLI 是否最新版本
   - 确认已正确登录 Cloudflare

2. **视频无法播放**
   - 检查 API 端点是否可访问
   - 确认浏览器支持 HTML5 视频

3. **移动端手势不工作**
   - 确认浏览器支持 Touch Events
   - 检查是否在 HTTPS 环境下访问

### 获取帮助
- [Cloudflare Pages 文档](https://developers.cloudflare.com/pages/)
- [Wrangler CLI 文档](https://developers.cloudflare.com/workers/wrangler/)

## 项目文件说明

- `index.html` - 主页面文件
- `package.json` - 项目配置
- `_headers` - Cloudflare Pages 头部配置
- `wrangler.toml` - Wrangler CLI 配置
- `deploy.sh` - 自动部署脚本
- `.gitignore` - Git 忽略文件配置