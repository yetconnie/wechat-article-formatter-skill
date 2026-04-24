  # 微信公众号文章排版技能
  将 Word / PDF / TXT /markdown 等文档一键转换为简洁、专业的微信公众号 HTML 排版
  
<p>
  <img src="https://img.shields.io/badge/license-Apache--2.0-blue" alt="License">
  <img src="https://img.shields.io/badge/platform-CoStrict-green" alt="Platform">
  <img src="https://img.shields.io/badge/compatible-WeChat%20Editor-orange" alt="WeChat Compatible">
</p>


---

## 特性

- **蓝黑灰专业配色** ：统一的视觉体系，告别花哨配色
- **移动端优先**：750px 最大宽度，完美适配手机阅读
- **模块化样式** ：高亮框、引用框、步骤列表等即插即用
- **编辑器兼容** ：纯内联样式，复制粘贴到微信公众号编辑器样式零丢失
- **一键生成** ：读取文档 → 自动分析 → 输出 HTML → 可复制粘贴至微信公众号 
- **支持word\pdf\markdown**：增加对运营常用的文档格式word和pdf文档的支持

## 适用场景

| 场景         | 说明                           |
| ------------ | ------------------------------ |
| 长文章排版   | 优化行高、字间距，提升阅读体验 |
| 技术文档发布 | 教程、分析报告等专业内容       |
| 团队内容规范 | 保持多篇文章视觉风格一致       |
| 快速预览     | 浏览器直接打开预览效果         |

## 设计规范

### 配色方案

| 角色   | 色值                              | 用途                       |
| ------ | --------------------------------- | -------------------------- |
| 主题蓝 | `#1890ff`                         | 标题边框、高亮框、重点标记 |
| 链接蓝 | `#576b95`                         | 超链接                     |
| 纯黑   | `#000`                            | 标题文字                   |
| 深灰   | `#333`                            | 正文文字                   |
| 中灰   | `#888`                            | 次要信息                   |
| 背景灰 | `#f5f5f5` / `#f8f8f8` / `#fafafa` | 区块背景                   |

### 排版参数

| 项目     | 规格                           |
| -------- | ------------------------------ |
| H1 标题  | 24px，居中                     |
| H2 标题  | 20px，左对齐，左侧蓝色边框 4px |
| H3 标题  | 18px                           |
| 正文     | 15px，字间距 1px               |
| 小字     | 14-15px                        |
| 行高     | 1.8                            |
| 段落间距 | 15px                           |
| 最大宽度 | 750px                          |

### 内容模块

```
┌─────────────────────────────────┐
│ 元信息框                      │  ← 灰底 + 蓝色左边框 3px
│ 作者 / 来源 / 原文链接         │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│ 核心观点框                    │  ← 浅蓝底 + 蓝色左边框 4px
│  要点总结 / 核心论点            │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│ 引用框                        │  ← 浅灰底 + 蓝色左边框 4px + 斜体
│ 名言 / 他人观点               │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│ 步骤列表框                    │  ← 灰底 + 圆角
│    • 步骤1                       │
│    • 步骤2                       │
└─────────────────────────────────┘

────────── 渐变分隔线 ──────────   ← 透明→灰→透明渐变
```

## 预览效果
- [超越 CodeRabbit 和 GitHub Copilot，CoStrict CodeReview 做对了什么](https://mp.weixin.qq.com/s/cbLMJGI4xcP2t44jmTpokA)
- [单任务稳定运行1000+ Steps，CoStrict 的 Harness Engineering 实战拆解](https://mp.weixin.qq.com/s/r29P4HK9eV-QY9yVW8ES-Q)

## 使用方式

本技能可以运行在 [CoStrict](https://costrict.ai)、[Claude Code](https://claude.com/product/claude-code)、[OpenCode](https://opencode.ai/) 等AI 编程工具中，安装后即可使用。

以CoStrict为例（其他工具可参考官网文档）：
1. 在安装目录下找到.config/costrict文件，新建skills文件夹（如果已有可忽略）
2. 新建一个wechat-article-formatter文件夹（注：文件夹名称需要与SKILL.md的name名称保持一致）。
3. 将本仓库的SKILL.md下载至wechat-article-formatter文件夹，确保SKILL全大写。
4. Frontmatter检查：确认SKILL.md 文件中包含了必需的name和 description字段。
5. 检查名称唯一性：检查所有扫描路径下是否存在同名的skill。skill 名称必须是唯一的，如果出现冲突，加载行为可能不确定。
6. 打开CoStrict CLI，在对话框中输入「skill」，如果出现wechat-article-formatter这个skill，表明skill已经成功加载。

### 工作流程

```
📄 源文档          🔍 内容分析          🧩 套用模板          📦 输出 HTML
(Word/PDF/Markdown) → (结构/元信息/重点) → (内联样式排版) → (预览 & 复制)
```

1. **读取源文件** — 支持 `.docx`、`.pdf`、`.txt` 、`Markdown`等格式
2. **内容分析** — 自动识别标题、段落、引用、列表等结构
3. **套用模板** — 匹配内容类型到对应样式模块
4. **生成文件** — 输出 `[原文件名]_wechat.html`
5. **预览验证** — 浏览器打开预览，确认效果

### 微信公众号发布

生成 HTML 文件后：

1. 在浏览器中打开 HTML 文件
2. `Ctrl+A` 全选页面内容 → `Ctrl+C` 复制
3. 打开微信公众号编辑器 → `Ctrl+V` 粘贴
4. 样式完整保留，无需二次调整 ✅

> **为什么用内联样式？** 微信公众号编辑器会自动剥离 `<style>` 标签、`class` 类名、外部样式表、伪元素等。本技能将所有 CSS 写在 HTML 标签的 `style` 属性中，确保粘贴后样式零丢失。

## 文件结构

```
wechat-article-formatter/
├── SKILL.md      # 技能定义文件（完整规范）
└── README.md     # 本文件
```

## 注意事项

- **配色限制** — 严格使用蓝黑灰配色，不使用绿、黄、红等颜色
- **内联样式** — 所有 CSS 通过 `style` 属性内联，禁止 CSS 类选择器和 `<style>` 标签
- **移动优先** — 确保手机端阅读体验
- **简洁性** — 避免过度装饰，保持专业感

## 许可证

[Apache-2.0](http://www.apache.org/licenses/LICENSE-2.0)

---

<p align="center">
  此技能由 <strong>CoStrict 团队</strong>使用 AI 编程工具 <strong>CoStrict</strong> 制作<br>
  访问 <a href="https://costrict.ai">CoStrict 官网</a> 获取开源 AI 编程工具，注册即可获得500 次免费额度
</p>

