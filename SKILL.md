---
name: wechat-article-formatter
description: 将文档转换为适合微信公众号阅读的专业网页排版
license: Apache-2.0
compatibility: costrict
metadata:
  audience: content-creators, writers, marketers
  workflow: content-publishing
---

## What I do

- 将 Word/PDF/TXT 文档转换为微信公众号友好的 HTML 格式
- 应用专业的蓝黑灰配色方案和排版规范
- 生成移动端优先的响应式布局
- 提供模块化的内容样式（高亮框、引用框、步骤列表等）
- 可复制内容到微信公众号编辑器

## When to use me

当您需要将文档内容发布到微信公众号或其他移动阅读平台时使用本技能。特别适合：

- 长文章需要优化阅读体验
- 技术文档、教程、分析报告等专业内容
- 需要保持一致的视觉风格
- 希望快速生成预览网页

## 适用场景

- 将 Word/PDF 文档转换为微信公众号文章
- 优化长文排版，提升阅读体验
- 生成移动端友好的 HTML 网页
- 需要专业、简洁的文章呈现效果

## 设计原则

### 1. 配色方案

**主色调（蓝黑灰体系）**

- 主题蓝：`#1890ff` - 用于标题边框、高亮框、重点标记
- 链接蓝：`#576b95` - 用于超链接
- 纯黑：`#000` - 标题文字
- 深灰：`#333` - 正文文字
- 中灰：`#888` - 次要信息
- 背景灰：`#f5f5f5` / `#f8f8f8` / `#fafafa` - 区块背景

### 2. 排版规范

**布局设计**

- 最大宽度：750px（适配移动端）
- 内边距：20-30px
- 响应式设计：自动适配不同屏幕

**字体系统**

```css
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", 
             "PingFang SC", "Hiragino Sans GB", 
             "Microsoft YaHei", "Helvetica Neue", Helvetica, Arial, sans-serif;
```

**字号规范**

- H1 标题：24px（居中）
- H2 标题：20px（左对齐，左侧蓝色边框 4px）
- H3 标题：18px
- 正文：15px
- 小字：14-15px

**行高与间距**

- 正文行高：1.8
- 正文字间距：1px
- 段落间距：15px
- 标题上边距：30-35px
- 标题下边距：15-20px

### 3. 内容模块样式

#### 元信息框

```css
background: #f8f8f8;
border-left: 3px solid #1890ff;
padding: 15px;
font-size: 14px;
color: #888;
```

**用途**：作者、来源、原文链接、背景信息等

#### 核心观点框

```css
background: #f0f9ff;
border-left: 4px solid #1890ff;
padding: 20px;
border-radius: 0 4px 4px 0;
```

**用途**：核心论点、要点总结、结论等

#### 引用框

```css
background: #fafafa;
border-left: 4px solid #1890ff;
padding: 15px 20px;
font-style: italic;
color: #555;
```

**用途**：引用文字、名言

#### 步骤列表框

```css
background: #f9f9f9;
padding: 20px;
border-radius: 4px;
```

列表项前缀：黑色实心圆点 `•`
**用途**：步骤、流程、清单等

#### 分隔线

```css
height: 1px;
background: linear-gradient(to right, transparent, #ddd, transparent);
margin: 30px 0;
```

#### 图片占位符

```css
background: #f5f5f5;
padding: 40px 20px;
text-align: center;
color: #999;
font-size: 14px;
```

### 4. HTML 结构模板

> **重要**：所有样式必须使用内联 `style` 属性，禁止使用 `<style>` 标签或 CSS 类选择器，确保复制到微信公众号编辑器后样式完整保留。

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[文章标题]</title>
</head>
<body style="margin: 0; padding: 0; background-color: #fff; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', 'Helvetica Neue', Helvetica, Arial, sans-serif; color: #333; font-size: 15px; line-height: 1.8; letter-spacing: 1px;">

    <div style="max-width: 750px; margin: 0 auto; padding: 20px 25px;">

        <h1 style="font-size: 24px; text-align: center; color: #000; margin: 30px 0 15px; font-weight: bold;">[文章标题]</h1>

        <!-- 元信息框 -->
        <div style="background: #f8f8f8; border-left: 3px solid #1890ff; padding: 15px; font-size: 14px; color: #888; margin-bottom: 25px;">
            <p style="margin: 5px 0; font-size: 14px; color: #888;">作者：[作者名]</p>
            <p style="margin: 5px 0; font-size: 14px; color: #888;">原文链接：<a href="[链接]" style="color: #576b95; text-decoration: none;">[链接]</a></p>
        </div>

        <!-- 核心观点框 -->
        <div style="background: #f0f9ff; border-left: 4px solid #1890ff; padding: 20px; border-radius: 0 4px 4px 0; margin-bottom: 25px;">
            <h2 style="font-size: 20px; color: #000; margin: 0 0 10px; border: none; padding: 0;">核心观点</h2>
            <p style="margin: 5px 0; color: #333;">[核心观点内容]</p>
        </div>

        <!-- 分隔线 -->
        <div style="height: 1px; background: linear-gradient(to right, transparent, #ddd, transparent); margin: 30px 0;"></div>

        <!-- 章节标题 -->
        <h2 style="font-size: 20px; color: #000; margin: 30px 0 15px; padding-left: 12px; border-left: 4px solid #1890ff;">[章节标题]</h2>
        <p style="margin-bottom: 15px; color: #333;">[正文内容]</p>

        <!-- 引用框 -->
        <div style="background: #fafafa; border-left: 4px solid #1890ff; padding: 15px 20px; font-style: italic; color: #555; margin-bottom: 20px;">
            <p style="margin: 0; font-style: italic; color: #555;">[引用内容]</p>
        </div>

        <!-- 高亮框 -->
        <div style="background: #f0f9ff; border-left: 4px solid #1890ff; padding: 20px; border-radius: 0 4px 4px 0; margin-bottom: 20px;">
            <p style="margin: 0; color: #333;">[高亮内容]</p>
        </div>

        <!-- 重点内容 -->
        <div style="background: #f8f8f8; border-left: 3px solid #1890ff; padding: 15px; margin-bottom: 20px;">
            <p style="margin: 5px 0; color: #333;"><strong style="color: #000;">[重点标题]</strong>：[重点内容]</p>
        </div>

        <!-- 步骤列表 -->
        <div style="background: #f9f9f9; padding: 20px; border-radius: 4px; margin-bottom: 20px;">
            <ul style="padding-left: 20px; margin: 0;">
                <li style="margin-bottom: 8px; color: #333;">[步骤1]</li>
                <li style="margin-bottom: 8px; color: #333;">[步骤2]</li>
            </ul>
        </div>

        <!-- 参考资料 -->
        <div style="margin-top: 30px; padding-top: 20px; border-top: 1px solid #eee;">
            <h3 style="font-size: 18px; color: #000; margin: 0 0 10px;">附：参考资料</h3>
            <p style="margin: 5px 0; font-size: 14px;"><a href="[链接]" style="color: #576b95; text-decoration: none;">[链接描述]</a></p>
        </div>

    </div>

</body>
</html>
```

## 使用流程

### 第1步：读取源文件

```
使用 read_file 工具读取文档内容（支持 .docx, .pdf, .txt 等）
```

### 第2步：内容分析

- 识别文章结构（标题、段落、引用、列表等）
- 提取元信息（作者、来源、日期等）
- 识别核心观点和重点内容

### 第3步：套用模板

- 使用 HTML 结构模板（所有样式使用内联 `style` 属性）
- 根据内容类型选择对应的样式模块：
  - 标题 → `<h1>`, `<h2>`, `<h3>` + 内联样式
  - 核心观点 → 蓝底左边框容器 + 内联样式
  - 引用 → 灰底左边框斜体容器 + 内联样式
  - 步骤流程 → 灰底圆角列表容器 + 内联样式
  - 章节分隔 → 渐变分隔线 `<div>` + 内联样式
  - 图片说明 → 灰底居中容器 + 内联样式

### 第4步：生成文件

```
使用 write_to_file 创建 HTML 文件
命名建议：[原文件名]_wechat.html
```

### 第5步：预览验证

```
使用 execute_command 在浏览器打开预览：
start [文件名].html  # Windows
open [文件名].html   # macOS
xdg-open [文件名].html  # Linux
```

## 质量检查清单

- [ ] 配色仅使用蓝色和黑灰色系
- [ ] 字号、行高符合规范
- [ ] 最大宽度 750px
- [ ] 所有样式使用内联 `style` 属性（无 CSS 类选择器、无 `<style>` 标签）
- [ ] 链接可点击且颜色正确
- [ ] 响应式设计正常工作
- [ ] 段落间距适中，阅读舒适
- [ ] 标题层级清晰
- [ ] 重点内容已高亮显示

## 注意事项

1. **配色限制**：严格使用蓝黑灰配色，避免使用绿色、黄色、红色等
2. **移动优先**：确保在手机上阅读体验良好
3. **内联样式**：所有样式必须通过 `style` 属性内联，禁止使用 CSS 类选择器、`<style>` 标签或外部样式表
4. **可读性**：保持足够的行高和段落间距
5. **一致性**：同类内容使用相同样式
6. **简洁性**：避免过度装饰，保持专业感
7. **微信公众号编辑器兼容性**：必须使用内联样式（inline style），所有 CSS 直接写在对应 HTML 标签的 `style` 属性中。微信公众号编辑器会剥离 `<style>` 标签、`<script>` 标签、`class` 类名及外部样式表，导致样式丢失。禁止使用 CSS 类选择器、ID 选择器、伪元素（`::before`/`::after`）、CSS 变量等不被编辑器支持的特性。每个元素的样式必须自包含，确保复制粘贴后样式完整保留

## 示例应用

**适合使用高亮框的内容**

- 要点总结
- 核心观点列表
- 关键要点提炼

**适合使用引用框的内容**

- 名人名言
- 他人观点
- 重要论述

**适合使用步骤列表的内容**

- 操作流程
- 工作步骤
- 实施方案

## 输出格式

生成独立的 HTML 文件，包含：

- 完整的内联 CSS 样式（所有样式直接写在 HTML 标签的 `style` 属性中，确保粘贴到微信公众号编辑器后样式不丢失）
- 格式化的文章内容
- 响应式设计代码
- 可直接在浏览器打开预览
- 可直接复制内容粘贴到微信公众号编辑器，样式完整保留

## 技能目标

通过标准化的排版规范和模块化设计，快速将任何文档转换为专业、美观、适合微信公众号阅读的网页格式，提升内容传播效果。

---

## 版权与支持

此 skill 由**CoStrict 团队**使用 AI 编程工具 **CoStrict** 制作。

访问 **[CoStrict 官网](https://costrict.ai)** 获取开源AI编程工具，注册即可获得 200 次免费额度。