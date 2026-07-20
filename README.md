# 个人主页 (Personal Homepage)

一个简洁、高级的科研人个人主页，纯 HTML + CSS，无需构建工具，可直接托管到 GitHub Pages。

## 文件结构

```
homepage/
├── index.html      # 页面内容（在这里改文字）
├── styles.css      # 样式（改配色 / 字体在文件顶部 :root 里）
├── assets/         # 放头像、论文缩略图、CV 等
│   ├── avatar.jpg
│   ├── cv.pdf
│   ├── pub1.jpg
│   └── pub2.jpg
└── README.md
```

## 本地预览

```bash
cd homepage
python3 -m http.server 8000
# 浏览器打开 http://localhost:8000
```

## 需要修改的内容

1. `index.html` 里所有 `Your Name`、`University Name`、邮箱、链接等占位文字。
2. 把头像放到 `assets/avatar.jpg`，简历放到 `assets/cv.pdf`。
3. 教育经历、科研成果、实习经历分别在 `#education` / `#research` / `#experience` 区块里增删条目。
4. 想换主题色：改 `styles.css` 顶部 `--accent`（默认墨绿）。已内置深色模式（跟随系统）。

## 发布到 GitHub Pages

### 方式一：用户主页（推荐，域名最短）

仓库名必须为 `<你的用户名>.github.io`：

```bash
cd homepage
git init
git add .
git commit -m "init homepage"
git branch -M main
git remote add origin https://github.com/<用户名>/<用户名>.github.io.git
git push -u origin main
```

几分钟后访问：`https://<用户名>.github.io`

### 方式二：项目仓库

1. 新建任意名字的仓库（如 `homepage`），推送代码。
2. 打开仓库 **Settings → Pages**。
3. **Source** 选 `Deploy from a branch`，分支选 `main`，目录选 `/ (root)`，保存。
4. 访问：`https://<用户名>.github.io/homepage/`

> 提示：每次 `git push` 后 GitHub 会自动重新部署，等待 1–2 分钟即可看到更新。
