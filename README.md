# Product SEO ZH

A Claude Code / OpenCode skill for building English B2B product pages from scratch, driven by Chinese interaction. Modular design — generate the full page or invoke individual sections (FAQ, specs, comparison, etc.) independently. Purpose-built for industrial equipment, crushing & screening machinery, recycling equipment, and export-oriented brands.

中文输入、英文产出的 B2B 产品页面 SEO 创作工作流 skill。模块化设计：13 个独立板块，支持整套生成或单板块独立调用。专为工业设备、破碎筛分、回收/环保、出口品牌的英文产品页设计。

## 适用场景

- 工业设备 / 制造业品牌的英文产品页面生产
- 出口型 B2B 网站的商业转化页（commercial intent）
- 需要谷歌 SERP + Featured Snippets 双优化的产品页
- 模块化工作场景：已有半成品页面、只需要某个板块（FAQ / 参数表 / 对比表）
- 中文运营者驱动、英文产出的工作流

如果你写的是**博客 / informational 内容**，请用 [blog-seo-zh](https://github.com/luzhenhua/blog-seo-zh)，不是这个 skill。

## 13 个模块化板块

每个板块都是独立提示词，可以单独跑，也可以整套跑。

| Module | 板块 | 整套必含 | 触发关键词 |
|--------|------|---------|----------|
| 0 | 总策划（TDK + URL + H1-H14 架构） | ✅ | "策划 / 架构 / TDK" |
| 1 | H1 + 首屏 | ✅ | "H1 / 首屏 / hero" |
| 2 | 产品定义（What is / Overview） | ✅ | "定义 / overview" |
| 3 | 工作原理（How it Works） | ✅ | "原理 / working principle" |
| 4 | 产品类型（Types） | ⚪ 按需 | "类型 / types" |
| 5 | 参数规格（Specifications，含表格） | ✅ | "参数 / specs" |
| 6 | 应用场景（Applications，8-10 条） | ✅ | "应用 / applications" |
| 7 | 案例展示（Project Case） | ⚪ 按需 | "案例 / case" |
| 8 | 产品对比（vs Comparison，含表格） | ⚪ 按需 | "对比 / vs" |
| 9 | 采购指南（How to Choose，6-8 条） | ✅ | "选型 / how to choose" |
| 10 | 价格因素（Price Factors） | ✅ | "价格 / price" |
| 11 | 定制方案（Custom Solutions） | ✅ | "定制 / custom" |
| 12 | 制造商介绍（Manufacturer，⚠️ 必须段落） | ✅ | "制造商 / manufacturer" |
| 13 | FAQ（8 条，Featured Snippets 优化） | ✅ | "FAQ / 常见问题" |

## 核心特性

- **变量声明**：阶段 0.5 锁定 4 个变量（产品名 / 品牌名全称+简称 / 行业领域 / 目标读者），太泛的输入会被驳回
- **模块化执行**：整套跑用 `/product-seo-zh`；单跑用 `/product-seo-zh faq` 或自然语言"只跑 FAQ"
- **AI 痕迹零容忍**：内置 40+ 禁用词 / 开头 / 结尾模式，每段自检后才交付
- **数据真实性**：参数表型号 5-7 行，数值要"看起来可信"（不能太整），强制带免责声明
- **段落 vs 列表强校验**：制造商板块、产品定义板块强制段落；对比板块、参数板块强制带表格
- **品牌名规则**：首次出现用全称（如 "Henan Xinzhongyi Environmental Protection Equipment Co., Ltd."），之后用简称（如 "Zhongyi"）
- **价格禁锢**：价格板块严禁出现具体 USD 数字（既不准也降低询盘），只给影响因素
- **Featured Snippets 优化**：FAQ 首句直答、定义清晰、段落结构利于 Google 抓取
- **行业工程师 + 采购顾问双视角**：技术细节准确 + 采购痛点清晰，不是营销话术

## 安装

### Claude Code

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/luzhenhua/product-seo-zh.git ~/.claude/skills/product-seo-zh
```

### OpenCode

```bash
mkdir -p ~/.config/opencode/skills
git clone https://github.com/luzhenhua/product-seo-zh.git ~/.config/opencode/skills/product-seo-zh
```

> OpenCode 也会扫描 `~/.claude/skills/`，所以装到 `~/.claude/skills/product-seo-zh/` 一次即可两端通用。

## 使用

### 整套调用

```text
/product-seo-zh
```

或自然语言："写产品页 / 按产品页流程做 / 帮我做完整产品页"

→ 跑阶段 0.5（变量声明）→ 按 Module 0 → 13 顺序，每完成 1 个停下让你校对

### 单模块调用

```text
/product-seo-zh faq         # 只跑 FAQ
/product-seo-zh specs       # 只跑参数表
/product-seo-zh manufacturer # 只跑制造商介绍
/product-seo-zh comparison  # 只跑产品对比
```

或自然语言："只跑 FAQ" / "跑参数表" / "做制造商介绍" / "跑工作原理那段"

→ 跑阶段 0.5（如果还没跑过）→ 只跑指定 Module

### 跑多个模块

自然语言："跑 module 5 6 7" / "做 Specs + Applications + FAQ"

### 触发后的交互

调用后第一步会让你给 4 个变量：

```text
- 产品名 / 核心关键词：如 "Mobile Crusher Plant"
- 品牌名：
  - 全称（首次出现用）：如 "Henan Xinzhongyi Environmental Protection Equipment Co., Ltd."
  - 简称（后续用）：如 "Zhongyi" 或 "Xinzhongyi"
- 行业领域：如 "移动破碎与筛分设备 / 矿山骨料 / 建筑垃圾回收"
- 目标读者：如 "海外采矿工程师、选矿厂采购决策者"
```

## 输入示例

```text
产品名：Mobile Crusher Plant
品牌名全称：Henan Xinzhongyi Environmental Protection Equipment Co., Ltd.
品牌名简称：Zhongyi
行业领域：移动破碎与筛分设备
目标读者：海外采矿工程师、选矿厂采购决策者
```

## 产出示例（节选）

- **Module 0**（总策划）：2 个备选 Title（含字符数）、2 个备选 Description、URL、完整 H1-H14
- **Module 1**（H1 + 首屏）：H1 + 3-4 句段落 + 4 个核心参数 + CTA 按钮
- **Module 5**（参数表）：Markdown 表格 5-7 行型号 + 免责声明
- **Module 8**（产品对比）：3-4 维度对比段 + Markdown 对比表 + 选型建议
- **Module 12**（制造商）：2 段流畅段落（⚠️ 必须段落不能列表）共 180-250 词
- **Module 13**（FAQ）：8 条 Q&A，每条答案 ≤40 词且首句直答

## 与 blog-seo-zh / humanizer-seo 的关系

| 维度 | product-seo-zh | blog-seo-zh | humanizer-seo |
|------|----------------|-------------|---------------|
| 页面类型 | 产品页（commercial） | 博客（informational） | 产品/集合/方案页 |
| 流程 | 模块化（13 个 Module） | 顺序工作流（8 阶段） | 单次改写 |
| 起点 | 产品名（从零开始） | 关键词（从零开始） | 已有大纲/草稿 |
| 产出 | 完整产品页 + TDK + FAQ | 整篇博客 + TDK + FAQ | 改写后的内容 |
| 模块化 | ✅ 单板块可独立调 | ❌ 必须从头跑 | ✅ 单段可独立改 |

三者互补：

- 写**博客**用 `blog-seo-zh`
- 写**产品页**用本 skill
- 任何 AI 草稿想要最后一次"去 AI 味"精修，过一次 `humanizer-seo`

## 注意事项

- AI 产出 ≠ 终稿。每个模块产出都是草稿，发布前必须人工编辑
- **参数表（Module 5）的数据是估算值**，发布前必须对照你公司真实产品手册核对
- **案例展示（Module 7）只是模板**，必须替换为真实项目数据
- **制造商介绍（Module 12）的经验年限 / 认证 / 服务范围**必须符合你公司真实能力，不能虚标
- 价格板块**严禁**出现具体 USD 数字（既不准也降低询盘）
- 本 skill 仅适用于英文产出。如需写中文产品页，请勿使用本 skill

## 设计哲学

这套 skill 解决三个 AI 写产品页的常见痛点：

1. **AI 写得像 AI** —— 用 40+ 禁用词库 + 段落自检解决
2. **AI 写得太泛** —— 用变量声明驳回 + 每板块强制带数据范围解决
3. **AI 工作流不灵活** —— 用模块化设计解决（不强迫你从头写整页）

工作流参考了实际外贸 B2B 业务场景中的产品页结构，覆盖：技术参数、应用场景、采购决策、对比、定制、信任建立、常见问题等用户从浏览到询盘的完整心智路径。

## License

MIT
