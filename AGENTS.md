# 观复斋 (Guan Fu Zhai) - AGENTS.md

本文件为 AI 智能助手（Jules 等）在此 GitHub Pages 个人网站仓库中协助内容自动化编写、文章发布与资源管理的规则与规范约定。

---

## 1. 网站架构与内容分类 (Category Mapping)

网站采用青花水墨古风主题，包含以下 5 大核心板块：

| 分类 ID (`category`) | 板块名称 | 领域与主题说明 |
| :--- | :--- | :--- |
| `research` | **探源·研思** | 学术论文综述、哲学反思、知识拓扑与深度考据 |
| `teaching` | **传灯·育新** | 启发式提问、教学手记、研讨课反思与对话记录 |
| `practice` | **知行·践真** | 自动化工具、开源代码实验、Canvas卡片排版等实操项目 |
| `ai-vision` | **远瞻·智境** | AI 智能体交互形态、生成式算法美学与未来智境遐想 |
| `life` | **清欢·拾光** | 重读经典随想、茶边小记、读书散记与日常生活碎片 |

---

## 2. Jules 自动化写作与发布规范 (Automated Writing Workflow)

当收到诸如 `jules new "写一篇关于...的文章，分类为..."` 的指令时，Jules 应遵循以下约定：

### 2.1 文章格式标准 (Article Data Model)
在 `index.html` 的 `articles` 数组中增加新条目，或生成对应格式的 Markdown 数据：

```javascript
{
    id: "唯一英文ID或拼音",
    title: "文章标题",
    category: "research | teaching | practice | ai-vision | life",
    categoryLabel: "分类显示名",
    date: "YYYY-MM-DD",
    readTime: "X mins read",
    summary: "文章摘要（100字左右）",
    tags: ["标签1", "标签2"],
    content: `HTML/Markdown格式的文章正文`,
    attachments: [
        { name: "附件名称.pdf", path: "assets/docs/附件名称.pdf", icon: "fa-file-pdf" },
        { name: "示例图片.png", path: "assets/images/示例图片.png", icon: "fa-file-image" }
    ]
}
```

---

## 3. 附件与媒体资源管理规范 (Assets Guidelines)

所有静态资源统一存储于仓库根目录的 `assets/` 文件夹中：

```text
assets/
├── images/       # 存放文章插图、流程图、古风卡片等图片资源 (.png, .jpg, .svg, .webp)
└── docs/         # 存放 PDF 文档、Word 手记、代码压缩包等离线附件 (.pdf, .zip, .docx)
```

### 3.1 引用规则
- 在正文中使用相对路径引用资源：`assets/images/filename.png` 或 `assets/docs/filename.pdf`
- 并在文章条目的 `attachments` 属性中添加下载链接，便于读者点击下载。

### 3.2 隐私安全规则 (Privacy & Security Notice)
⚠️ **绝对安全准则**：GitHub Pages 仓库中的所有文件均为公开展示。在添加任何附件时，绝不能包含身份证件、个人手机号、敏感合同或密钥凭证。

---

## 4. Jules 自动化批量管理指令范例 (Example Prompts)

- **新增文章**："写一篇关于庄子‘心斋’与个人修行的文章，分类为清欢·拾光，标签是[修行, 庄子, 读书笔记]，包含一个 PDF 导图附件"
- **更新索引**："将最新发布的 3 篇文章列入首页‘最新更新 (Latest Updates)’面板中"
- **批量处理**："清理 `assets/images/` 未被引用的旧图片，并检查所有文章里的附件下载链接"
