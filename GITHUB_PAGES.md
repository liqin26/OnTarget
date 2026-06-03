# GitHub Pages 发布说明

GitHub Pages 只能托管静态网页，不能运行 OnTarget 的 Flask 后端、SQLite 数据库、PubMed 抓取任务或 AI API 请求。因此推荐把 Pages 用作项目介绍页和使用文档，实际应用后端仍需部署到 VPS、Render、Railway、Fly.io、Docker 主机或其他 Python Web 服务环境。

## 发布静态项目页

1. 确认仓库已经包含 `docs/index.md`。
2. 提交并推送到 GitHub：

```bash
git add .
git commit -m "Add custom API configuration and Pages docs"
git push
```

3. 打开仓库设置：

`https://github.com/liqin26/OnTarget/settings/pages`

4. 在 **Build and deployment** 中选择：

- Source: `Deploy from a branch`
- Branch: `main`
- Folder: `/docs`

5. 点击 **Save**。
6. 等待 GitHub Pages 构建完成。通常几分钟后访问：

`https://liqin26.github.io/OnTarget/`

## 如果要发布真正可用的 OnTarget 应用

GitHub Pages 不适合部署后端。需要使用支持 Python 服务的环境，并配置环境变量：

```env
API_PROVIDER=deepseek
API_KEY=your-api-key
API_BASE_URL=https://api.deepseek.com
MODEL=deepseek-chat
PUBMED_EMAIL=your_email@example.com
SECRET_KEY=replace-with-a-random-secret
WEB_HOST=0.0.0.0
WEB_PORT=5500
WEB_DEBUG=False
```

部署后端后，可在 GitHub Pages 的 `docs/index.md` 中添加实际在线服务地址。
