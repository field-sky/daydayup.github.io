# 观复斋 | 个人灵感与日常积累 (Guan Fu Zhai)

一个优雅、禅意且面向 **GitHub Pages** 托管的静态个人网站/数字书房。采用青花瓷与水墨山水视觉风格，集成了高山湖泊倒影背景壁纸、模块化内容卡片、响应式移动端导航以及基于 Web Audio API 的五声音阶背景音乐合成器。

---

## 🌟 页面特色与设计亮点

1. **青花瓷与水墨意境视觉**
   - **配色方案**：以浓艳青花蓝（`#1A365D`）、澄澈青花蓝（`#2B4C7E`）、山水晨雾蓝（`#EAF2F8`）与朱砂印章红（`#B83232`）为基调。
   - **默认右侧山水画卷**：首页右侧采用喀斯特高山倒影高清壁纸（`assets/images/bg-landscape.jpg`），辅以磨砂玻璃（`backdrop-blur`）悬浮卡片，确保高对比度与典雅排版。

2. **模块化内容导航**
   - **山水画卷 · 首页** (`#module-landscape`)：展示诗意主视觉与板块快速入口及最新更新推送。
   - **探源·研思** (`#module-research`)：深度思考、学术综述与读书反思。
   - **传灯·育新** (`#module-teaching`)：启发式提问与教学手记。
   - **知行·践真** (`#module-practice`)：个人开源项目、自动化脚本与前端实验。
   - **远瞻·智境** (`#module-ai-vision`)：未来 AI 交互、智能体与美学遐想。
   - **清欢·拾光** (`#module-life`)：日常随笔、茶边小记与生活记录。

3. **交互式文章阅读弹窗 (Article Reader Modal)**
   - 点击任意文章卡片可开启模态框阅读完整文章内容，支持文章标签（Tags）展示、附件文档（Markdown/PDF/Images）直接下载及键盘 `Esc` 快捷键关闭。

4. **无依赖 Web Audio 禅意 BGM 音频系统**
   - 内置基于 HTML5 Web Audio API 的中国五声音阶（宫、商、角、徵、羽）随机组合音效，零依赖外部大音频文件，随开随听。
   - 包含《古韵平湖》、《空山新雨》、《竹林听风》多种曲调，同时支持上传本地自定义背景音乐。

5. **全设备响应式设计**
   - 适配 Desktop、Tablet 及 Mobile。移动端提供顶部快捷栏与抽屉式折叠侧边栏。

---

## 📂 项目目录结构

```text
.
├── index.html              # 主页面 HTML / CSS / JS 全套代码
├── AGENTS.md               # Jules AI Agent 内容自动化更新与维护指南
├── assets/
│   ├── images/
│   │   └── bg-landscape.jpg # 默认右侧背景壁纸（喀斯特山水倒影）
│   └── docs/
│       └── sample-reading-notes.md # 示例附件文档
└── README.md               # 项目说明与 GitHub Pages 部署指南
```

---

## 📝 内容维护与更新指南 (`AGENTS.md`)

本项目支持直接通过编辑 `index.html` 中的 `articlesData` 数组扩充与管理内容：

- **添加新文章**：在 `articlesData` 数组中增加文章对象，填入 `id`, `title`, `category`, `readTime`, `topic`, `tags`, `summary`, `content` 以及可选的 `attachmentName` 和 `attachmentUrl`。
- **附件托管**：所有文档、PDF 或 Markdown 笔记可存放于 `assets/docs/` 目录下，并在文章对象的 `attachmentUrl` 中引用。
- **AI 自动化协作**：项目包含 `AGENTS.md`，可指导 AI 代理（如 Jules）按统一规范进行知识扩充与内容发布。

---

## 🚀 GitHub Pages 托管部署指南

将本项目一键部署至 GitHub Pages 极为简单，无需任何复杂的构建步骤或依赖包安装：

### 第一步：新建 GitHub 仓库
1. 登录 [GitHub](https://github.com)，点击右上角 **+** -> **New repository**。
2. 仓库名称可填写 `guanfuzhai` 或 `<your-username>.github.io`（若想作为主个人域名）。
3. 权限选择 **Public**，点击 **Create repository**。

### 第二步：推送项目代码
将本仓库的文件（包含 `index.html`、`assets/` 目录、`AGENTS.md` 以及 `README.md`）推送至 GitHub 仓库的 `main` 分支：

```bash
git init
git add .
git commit -m "feat: 部署观复斋个人网站初始版本"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

### 第三步：开启 GitHub Pages 托管
1. 进入 GitHub 仓库页面，点击 **Settings** (设置) -> 侧边栏 **Pages**。
2. 在 **Build and deployment** 下的 **Source** 中选择 **Deploy from a branch**。
3. **Branch** 选择 `main` 分支，目录选择 `/ (root)`，点击 **Save**。
4. 等待 1-2 分钟，刷新页面即可看到生成的访问网址（例如：`https://<your-username>.github.io/<your-repo-name>/`）。

---

## 📜 许可证

本项目基于 [MIT License](LICENSE) 开源，欢迎自由更改与个性化定制。
