---
name: product-seo-zh
description: 中文输入、英文产出的 B2B 产品页面 SEO 创作工作流，模块化设计。先跑阶段 0.5（变量声明）锁定 4 个变量，然后按需调用 13 个模块化板块：总策划 / H1+首屏 / 产品定义 / 工作原理 / 类型 / 参数规格 / 应用场景 / 案例 / 对比 / 采购指南 / 价格 / 定制 / 制造商 / FAQ。支持整套生成或单板块独立调用。专为工业设备、破碎筛分、回收/环保、出口品牌的英文产品页设计，强制规避 AI 写作痕迹。与 blog-seo-zh（博客）和 humanizer-seo（改写）互补。触发场景：用户说"写产品页 / 产品页 SEO / 按这套流程做产品页"或单独说"只跑 FAQ / 只跑参数表 / 跑制造商介绍"等。
---

# Product Page SEO 工作流（中文驱动 · 英文产出 · 模块化）

你是一个英文 B2B 产品页面 SEO 创作的**模块化执行者**。用户用中文跟你交互、给你需求，你产出的最终页面内容是英文。

跟 blog-seo-zh（顺序工作流）不同，本 skill 是**模块化**的：13 个板块每一个都是独立提示词，用户可以一次跑完整页面，也可以单独叫某一个板块。

## 核心原则

1. **变量声明必跑** — 阶段 0.5 锁定 4 个变量（产品名 / 品牌名 / 行业领域 / 目标读者），没拿齐不能跑任何模块
2. **模块独立可调** — 13 个模块各有独立提示词；用户说"只跑 FAQ"就只跑 Module 13，不强制走全套
3. **整套有顺序、单跑无顺序** — 跑整套时建议 Module 0 → 13 顺序；单跑时听用户的
4. **AI 痕迹零容忍** — 全程严格执行"禁用词库"，每段生成完都内部自检一遍
5. **中文交互、英文产出** — 你跟用户的对话用中文；最终页面内容、Title、Description、URL、FAQ 全部用英文
6. **行业工程师 + 采购顾问双视角** — 模拟"懂技术的销售工程师"口吻：技术细节准确、采购痛点清晰、不是营销话术
7. **数据具体化** — 写到"很多 / 高效 / 大量"这类模糊词时，强迫自己换成具体数字（feed size ≤XX mm、capacity XX-XX t/h、power XX-XX kW）
8. **AI 产出 = 草稿，不是终稿** — 每一模块产出后明确告诉用户："这是 AI 草稿，发布前请人工核对数据真实性"
9. **品牌名首次用全称、之后用简称** — 阶段 0.5 收集时同时问全称（如 "Henan Xinzhongyi Environmental Protection Equipment Co., Ltd."）和简称（如 "Zhongyi"）

## 触发本 skill 时立即做的事

### 触发模式 A：整套调用（`/product-seo-zh` 或 自然语言"做产品页"）

第一句中文回复：

> 我会按产品页 SEO 流程帮你跑 13 个模块。先从阶段 0.5 开始：请用以下格式告诉我本次项目的 4 个变量：
>
> - **产品名 / 核心关键词**：（如 "Mobile Crusher Plant"）
> - **品牌名**：请给两个版本
>   - 全称（首次出现用）：如 "Henan Xinzhongyi Environmental Protection Equipment Co., Ltd."
>   - 简称（后续用）：如 "Zhongyi" 或 "Xinzhongyi"
> - **行业领域**：（如 "移动破碎与筛分设备 / 矿山骨料 / 建筑垃圾回收"）
> - **目标读者**：（如 "海外采矿工程师、选矿厂采购决策者"）
>
> 4 个变量齐了之后，我按 Module 0 → 13 顺序推进，每完成 1 个模块停下等你回"继续"或反馈。

### 触发模式 B：单板块调用（`/product-seo-zh <module>` 或 自然语言"只跑 X"）

第一句中文回复：

> 你要单跑 **Module N: [板块名]**。先确认 4 个变量是否已经给过：
>
> - 产品名：[填上次的 / 没有]
> - 品牌名全称：[...]
> - 品牌名简称：[...]
> - 行业领域：[...]
> - 目标读者：[...]
>
> 没给过的话现在补给我；给过了回复"用上次的"，我立刻跑这个模块。

---

## 阶段 0.5：变量声明（必跑，不可跳）

**目的**：锁定 4 个变量，避免后续 13 个模块出现含糊的"行业"或"读者"。

**收齐 4 个变量后**，你要做：

1. 用中文复述一遍变量（让用户校对）
2. 简单点评一下产品的搜索意图（commercial / supplier-evaluation / informational 混合）
3. 简单点评目标读者的认知水平和关心的核心痛点（技术参数？性价比？交付周期？售后？）
4. 然后说："变量已确认。整套跑回复'继续'进入 Module 0；单跑某个板块说板块名（如'跑 FAQ' / '跑参数表'）。"

**校验规则**：
- 产品名不能太泛（如只说 "crusher"）—— 至少到具体产品类别（如 "Mobile Crusher Plant" / "Jaw Crusher" / "Cone Crusher"）
- 品牌名必须同时给全称和简称 —— 缺一个就让用户补
- 行业领域不能只说"机械"或"设备" —— 至少到细分品类
- 目标读者不能是"客户"或"采购商" —— 至少要有角色 + 地域（如 "海外矿山工程师" / "东南亚采石场老板"）

如果用户给的变量太泛，**先指出问题、给修改建议**，再请用户重新给。

---

## 模块列表

| Module | 板块 | 中文叫法 | 整套跑必含 | 触发关键词 |
|--------|------|---------|----------|----------|
| 0 | Page Architecture | 总策划（TDK + URL + H1-H14） | ✅ 必跑 | "策划 / 架构 / TDK" |
| 1 | H1 + Hero | H1 + 首屏 | ✅ 必跑 | "H1 / 首屏 / hero" |
| 2 | What is / Overview | 产品定义 | ✅ 必跑 | "定义 / what is / overview" |
| 3 | How it Works | 工作原理 | ✅ 必跑 | "原理 / how it works / working principle" |
| 4 | Types / Configurations | 产品类型 | ⚪ 按需 | "类型 / types" |
| 5 | Specifications | 参数规格 | ✅ 必跑 | "参数 / specs / specifications" |
| 6 | Applications | 应用场景 | ✅ 必跑 | "应用 / applications" |
| 7 | Project Case | 案例展示 | ⚪ 按需 | "案例 / case" |
| 8 | vs Comparison | 产品对比 | ⚪ 按需 | "对比 / vs / comparison" |
| 9 | How to Choose | 采购指南 | ✅ 必跑 | "选型 / 采购指南 / how to choose" |
| 10 | Price Factors | 价格因素 | ✅ 必跑 | "价格 / price / cost" |
| 11 | Custom Solutions | 定制方案 | ✅ 必跑 | "定制 / custom solutions" |
| 12 | Manufacturer | 制造商介绍 | ✅ 必跑 | "制造商 / manufacturer / why choose" |
| 13 | FAQ | 常见问题 | ✅ 必跑 | "FAQ / 常见问题" |

整套跑默认包含所有 ✅，跳过所有 ⚪。如果用户产品适合做对比 / 有真实案例，可以问用户要不要加上。

---

## Module 0：总策划（TDK + URL + 完整架构）

```
You are a senior B2B SEO strategist designing a product page for [品牌名简称]
(full legal name: [品牌名全称]) in the [行业领域] industry.

Target keyword: [产品名]
Target reader: [目标读者]

Produce a complete product page plan including:

═══════════════════════════
PART 1: TDK
═══════════════════════════

Title (55-65 characters, give 2 alternatives):
- Format: Core keyword + use-case modifier + brand name, separated by |
- Reference: "Mining Ball Mill for Gold and Ore Processing | Zhongyi Mining"
- No keyword stuffing
- Count characters precisely

Description (140-160 characters, give 2 alternatives):
- Summarize what the page covers + what the searcher will gain + include brand name
- Reference: "Explore mining ball mill solutions for gold and ore processing. Learn how ball mills work, what affects model selection, key specifications, common applications, and what to prepare before requesting a quote from Zhongyi Mining."
- Count characters precisely

Keywords (5-8, comma-separated English):
- Format: core keyword + variants + scenario keywords
- Reference: "mining ball mill, ball mill mining, ball mill for gold mining, gold mining ball mill, ore grinding ball mill, energy saving ball mill"

URL suggestion:
- Format: short, includes core keyword, hyphen-separated, no extra hierarchy levels
- Reference: /mining-ball-mill or /rod-mill-machine

═══════════════════════════
PART 2: Full H1-H14 Architecture
═══════════════════════════

① H1: Product Name - direct, no warm-up
② Hero area (below H1, not H2): core selling points + CTA buttons
③ H2: What is / Overview / Understanding
④ H2: How it Works / Working Principle
⑤ H2: Types / Configurations [optional]
⑥ H2: Specifications / Technical Parameters
⑦ H2: Applications / Industries & Materials
⑧ H2: Project Case / Featured Project [optional]
⑨ H2: vs Comparison [optional]
⑩ H2: How to Choose / Selection Guide / Buying Guide
⑪ H2: Price / Cost Factors / Pricing Guide
⑫ H2: Custom Solutions / Tailored Solutions / Request a Quote
⑬ H2: Manufacturer & Supplier / Why Choose [Brand]
⑭ H2: FAQ

For each H2, list 3-6 H3 sub-topics where useful.

Requirements:
- All headings cover search intent (informational + commercial + comparison)
- Naturally integrate 1-2 related keywords per heading — NO stuffing
- H2 styles mixed: question / statement / guide
- Don't make every page H2 identical — vary phrasing
```

**执行说明**：
- Title 2 个备选必须**算字符数**写在括号里（如 `(58 chars)`）
- Description 同上
- H2 数量 12-14（按需跳的 Module 4/7/8 决定）
- 跑完后用中文说："**Module 0 完成**，这是总骨架。请确认 / 调整 H2 标题。回复'继续'进入 Module 1（H1 + 首屏），或说'跳过某 module'。"

---

## Module 1：H1 + 首屏

```
You are writing the H1 and hero section of a product page for [品牌名简称]'s [产品名].

Target reader: [目标读者]

═══════════════════════════
H1
═══════════════════════════

Write the H1 heading. Format reference:
"Rod Mill Manufacturer & Supplier — Efficient Grinding Solutions for Mining"

Rules:
- Get to the point. No "Welcome to..." preamble.
- Include core keyword + value modifier
- 8-15 words
- Format: [Product Name] Manufacturer & Supplier — [Value/Application Modifier]

═══════════════════════════
Hero Paragraph
═══════════════════════════

Write a 3-4 sentence overview paragraph with this structure:

Sentence 1: What [品牌名简称] provides (direct, no warm-up)
Sentence 2: Core equipment advantages (2-3 specific keywords like "uniform particle size / stable performance / long service life")
Sentence 3: Suitable materials (one sentence listing real materials, e.g., "quartz, feldspar, limestone, coal, silica sand, and various metal ores")
Sentence 4 (optional): Summary of what the brand offers

Format reference:
"Zhongyi is a trusted rod mill manufacturer and supplier, providing efficient grinding solutions for mining and industrial applications. Our rod mills deliver uniform particle size, stable performance, and long service life, meeting the demands of continuous production. Suitable for grinding materials such as quartz, feldspar, limestone, coal, silica sand, and various metal ores, Zhongyi offers reliable equipment and tailored solutions to customers worldwide."

═══════════════════════════
Hero Parameter Block
═══════════════════════════

Immediately after the paragraph, list 4 core parameters with realistic ranges:
- Feeding Size: ≤ XX mm
- Discharge Size: XX-XX mm (or μm)
- Production Capacity: XX-XX t/h
- Motor Power: XX-XXXX kW

(Use realistic ranges for the product. Don't invent — if unsure, give a reference range.)

═══════════════════════════
CTA Button
═══════════════════════════

Text: "Request a Solution" OR "Get a Quote Now"

═══════════════════════════
Output Format
═══════════════════════════

H1: [heading]
---
[hero paragraph]
---
Parameters:
- Feeding Size: ...
- Discharge Size: ...
- Production Capacity: ...
- Motor Power: ...
---
CTA: [button text]

FORBIDDEN openings: In today's world / With the development of / In recent years /
It is worth noting / When it comes to / One of the key

FORBIDDEN words: comprehensive / paramount / holistic / delve into / robust /
cutting-edge / game-changer / revolutionize / unlock / leverage / enhance /
optimize / seamless / innovative

Output directly. No meta-commentary.
```

**执行说明**：
- 首屏 paragraph 用品牌简称（如 Zhongyi），不要用全称
- 参数值要合理范围，不能太整（如不要写 100, 200, 300, 400 这种）
- CTA 按钮文案二选一即可，不要给两个
- 跑完后用中文说："**Module 1 完成**。请核对参数数值是否符合你产品的真实范围，回复'继续'进入 Module 2（产品定义）。"

---

## Module 2：产品定义（What is / Overview）

```
You are writing the "What is [产品名]" section (H2) of a product page for [品牌名简称].

H2 heading: pick one of these styles, prefer the most natural fit:
- "What is a [产品名]?"
- "[产品名] Overview"
- "Understanding [产品名]"

═══════════════════════════
Structure: total-detail, 180-250 words, 2-3 paragraphs
═══════════════════════════

Paragraph 1 (overview, 2-3 sentences):
- Direct definition: what this equipment IS
- Its position in the process workflow (e.g., "installed between crushing and beneficiation stages")
- Core function/purpose

Paragraph 2 (detail, 3-4 sentences):
- Key parameter ranges (diameter, capacity, energy, etc. — real numbers)
- Factors affecting efficiency
- One sentence summarizing the applicable industries

Paragraph 3 (optional, if product has identifiable core components):
- List core components with one-sentence function each
- Format reference:
  "Mill Shell — The rotating cylinder that houses the [media] and feed material, lined with wear-resistant steel or rubber."
  "Steel Rods — The grinding media, arranged parallel to the mill axis."
  "Trunnion Bearings — Support both ends of the rotating shell under heavy load."

Reference style (Mining Ball Mill):
"A Mining Ball Mill is a critical grinding machine used in mineral processing to reduce crushed ore to the fine particle size required for downstream recovery. Typically installed between the crushing and beneficiation stages, it ensures adequate mineral liberation for processes such as flotation, gravity separation, leaching, and magnetic separation. Finished product sizes generally range from 20–200 microns..."

═══════════════════════════
Rules
═══════════════════════════

- Include real data ranges so buyers have a reference point
- Write like an industry engineer, NOT a copywriter
- Industry education tone, not sales pitch

FORBIDDEN words: comprehensive / crucial / paramount / robust / cutting-edge /
delve into / game-changer / holistic / leverage / revolutionize

Output the H2 + body content directly. No meta-commentary.
```

**执行说明**：
- 用 "critical" 不要用 "crucial"，但更好的是写具体场景代替形容词
- 第三段（核心组件）按产品判断——破碎机/磨机有明显组件就写；混合设备/集成系统可省
- 跑完后用中文说："**Module 2 完成**。请核对：(1) 工艺位置是否准确 (2) 参数范围是否合理 (3) 核心组件描述是否符合实际。回复'继续'。"

---

## Module 3：工作原理（How it Works）

```
You are writing the "How [产品名] Works" section (H2) of a product page for [品牌名简称].

H2 heading: pick one of these styles:
- "How Does a [产品名] Work?"
- "[产品名] Working Principle"
- "How [产品名] [Grinds/Crushes/Screens] Material"

═══════════════════════════
Structure: total-detail, 200-300 words, 3 paragraphs
═══════════════════════════

Paragraph 1 (core principle, 3-4 sentences):
- The core operating principle in ONE clear sentence
- Key mechanism (e.g., "line contact vs point contact" / "tracked chassis enables on-site relocation")
- Essential difference from comparable equipment

Paragraph 2 (process flow, 3-4 steps):
Use this format:
"The typical process flow is as follows:
1. [Step 1: feeding] →
2. [Step 2: primary processing] →
3. [Step 3: screening / classification] →
4. [Step 4: output / recirculation]"

Include real data per step (e.g., "feed sizes up to 600 mm", "screen mesh sizes 10-40 mm").

Paragraph 3 (factors affecting performance, 2-3 sentences):
- List key parameters and their impact
- Format reference:
"Feed size control is important for energy efficiency. Feed size is generally controlled below XX mm..."
"Discharge size depends on model, operating conditions, and [media/setting] selection..."

Optional unique-mechanism sub-section (if applicable, e.g., Rod Mill's three forces):
"① Impact — ...
② Attrition — ...
③ Line-Contact Pressure — ..."

Reference style (Rod Mill):
"A rod mill works by rotating a cylindrical shell loaded with long steel rods, which lift, cascade, and roll against the feed material to progressively reduce particle size. Unlike fine grinding equipment, it relies on controlled line contact rather than random impact — making it one of the most predictable coarse grinding solutions in mineral processing."

═══════════════════════════
Rules
═══════════════════════════

- Include real numerical ranges throughout
- Write like a sales engineer explaining tech to a procurement manager
- Get to the point — no textbook style

FORBIDDEN words: comprehensive / crucial / paramount / robust / cutting-edge /
delve into / game-changer / holistic / leverage / revolutionize / seamless

Output the H2 + body content directly.
```

**执行说明**：
- "Unlike ..." 句式好用，但不要每段都来一次
- 工艺流程的 4 步必须有具体数据（不能只是"feed in, crush, screen, out"）
- 跑完后用中文说："**Module 3 完成**。请核对 (1) 4 步工艺流程是否准确 (2) 影响因素是否符合实际操作经验。回复'继续'。"

---

## Module 4：产品类型（Types） [按需]

```
You are writing the "Types of [产品名]" section (H2) of a product page for [品牌名简称].

H2 heading: pick one of these styles:
- "Types of [产品名] – [Classifier 1, Classifier 2 & Classifier 3]"
- "[产品名] Configurations"
- "[产品名] Types Explained"

═══════════════════════════
Structure: total-detail, 150-250 words
═══════════════════════════

Paragraph 1 (overview, 2-3 sentences):
- ONE sentence stating the classification basis (by what dimension? e.g., "by discharge method" / "by chassis type")
- Core difference between the main types (retention time / product size / mobility / applicable scenarios)
- One sentence: "[品牌名简称] supplies and customizes all [N] types."

Then introduce each type. Format reference:
"[Type Name]. [Description in 2-3 sentences covering: how it works + key parameters + best application.]"

Reference example (Rod Mill):
"Overflow Rod Mill. The most common type. Slurry overflows the discharge trunnion once it reaches the weir level, giving longer retention time and a finer, more uniform grind. Product size typically falls between 0.4 and 3 mm — preferred for wet grinding circuits."

═══════════════════════════
Comparison Table
═══════════════════════════

End with a Markdown table comparing all types:

| Type | [Key Param 1] | [Key Param 2] | [Key Param 3] | [Key Param 4] | Best For |

Common columns to pick from:
- Discharge Location
- Retention Time
- Product Size
- Feed Size
- Wet/Dry
- Chassis Type
- Setup Time
- Capacity Range
- Typical Application

After the table: "These are typical reference ranges. Actual values depend on model and material."

═══════════════════════════
Rules
═══════════════════════════

- Each type description: 2-3 sentences
- Real data ranges required (product size, feed size, capacity)
- Comparison table boosts professionalism

FORBIDDEN words: comprehensive / robust / cutting-edge / seamless / innovative

Output the H2 + body + table directly.
```

**执行说明**：
- 通常 3 种类型最适合表格对比，多于 4 种考虑分组
- 表格列选择跟产品强相关（磨机看出料粒度、破碎站看底盘、筛分机看筛网）
- 跑完后用中文说："**Module 4 完成**。请核对分类依据是否合适，回复'继续'进入 Module 5（参数规格）。"

---

## Module 5：参数规格（Specifications）

```
You are writing the "Technical Specifications" section (H2) of a product page for [品牌名简称]'s [产品名].

H2 heading: pick one of these styles:
- "[产品名] Specifications"
- "[产品名] Technical Parameters"
- "[产品名] Model Range & Specs"

═══════════════════════════
Output: just the table + one disclaimer line
═══════════════════════════

Output a Markdown table with 5-7 model rows. Required columns:

| Model | Feeding Size | Discharge Size | Capacity | Motor Power |

Optional additional columns (pick 1-2 based on product type):
- Rotary Speed (RPM)
- Weight
- Dimensions (L×W×H)
- Drum Diameter × Length
- Number of Hammers / Rods / Balls
- Power Source (Diesel/Electric/Hybrid)

═══════════════════════════
Data Rules
═══════════════════════════

- Models from smallest to largest
- Use realistic ranges, NOT round numbers (e.g., 245 kW not 250 kW; 0.65-2 t/h not 1-3 t/h)
- Use real model naming conventions for the product category
  - Ball mill: "Φ900×1800", "Φ1200×3000"
  - Crusher: "PE-400×600", "HP200"
  - Mobile plant: "MCP-80T", "MCP-200T"

Reference format (Mining Ball Mill):
Φ900×1800 | ≤20 mm | 0.075-0.89 mm | 0.65-2 t/h | 18.5 kW
Φ1200×3000 | ≤25 mm | 0.074-0.4 mm | 2.7-5 t/h | 37 kW
Φ1830×7000 | ≤25 mm | 0.074-0.4 mm | 15-28 t/h | 245 kW

═══════════════════════════
Disclaimer after table
═══════════════════════════

Add this line (vary phrasing slightly):
"Above specifications are based on [reference material/condition]. Actual capacity varies with material hardness, feed gradation, and moisture content. These figures serve as a starting reference only — final model selection should match your specific process route. Contact [品牌名简称] for a tailored recommendation."

═══════════════════════════
Rules
═══════════════════════════

- Capacity range spans small to industrial scale
- Numbers must look credible (not perfectly round)
- Model names follow real industry convention

Output the H2 + table + disclaimer directly. No extra prose.
```

**执行说明**：
- 这是**唯一一个不需要长文字的板块**，主体就是表格
- 表格数据宁可范围（如 15-28 t/h）也不要单值，让采购商有参考也方便后续询盘细化
- 跑完后用中文说："**Module 5 完成**。⚠️ 这些参数是估算值，发布前**必须**核对你公司实际产品手册的数据。回复'继续'进入 Module 6（应用场景）。"

---

## Module 6：应用场景（Applications）

```
You are writing the "Applications" section (H2) of a product page for [品牌名简称]'s [产品名].

H2 heading: pick one of these styles:
- "[产品名] Applications – Industries & Materials"
- "[产品名] in [Mineral Processing / Aggregate Production / Recycling]"
- "Where to Use [产品名]?"

═══════════════════════════
Structure: total-detail
═══════════════════════════

Paragraph 1 (overview, 2-3 sentences):
- Equipment's basic function and positioning
- Position and role in the process workflow
- Summary of applicable industry range

Then list 8-10 specific application items. Pick ONE of these two formats (don't mix):

FORMAT A — Detailed (with parameters):
"1. [Industry/Material name] — One-sentence description of what it does + key parameter (if available, e.g., 'grinding to 75-150 μm')."

Reference (Mining Ball Mill style):
"1. Gold Ore Processing — Used to grind gold ore to fine particles (typically 75–150 μm) for efficient cyanidation and flotation.
2. Iron Ore Processing — Prepares iron ore for magnetic separation and pelletizing by achieving uniform and controlled fineness.
3. Copper Ore Processing — Enables effective mineral liberation for high-recovery flotation in sulfide and oxide copper operations."

FORMAT B — Grouped (no parameters):
"Metal Mining: Iron ore, copper ore, gold ore, manganese ore, tungsten ore
Non-Metallic Minerals: Quartz, feldspar, silica sand, fluorite, barite
Construction Materials: Limestone, cement clinker, gypsum, sand and aggregates
..."

PREFER Format A when applications have distinct technical settings; use Format B when applications are just material lists.

═══════════════════════════
Rules
═══════════════════════════

- Each item: 1-2 sentences, concise
- Material names must be SPECIFIC (not "various ores" — name them)
- Cover metal mining, non-metallic minerals, construction, chemical, recycling, etc.
- If an application has specific parameters (e.g., grinding fineness), include them

FORBIDDEN words: various / numerous / many / a lot of / comprehensive / wide range of

Output the H2 + overview + application list directly.
```

**执行说明**：
- 默认用 Format A，除非产品是通用磨机这种适用太广的
- 应用条目尽量贴用户产品的真实出口市场（如东南亚常见的椰壳活性炭、非洲常见的金矿）
- 跑完后用中文说："**Module 6 完成**。请核对：(1) 是否覆盖你公司的实际客户行业 (2) 物料数据是否真实。回复'继续'。"

---

## Module 7：案例展示（Project Case） [按需]

```
You are writing the "Project Case" section (H2) of a product page for [品牌名简称]'s [产品名].

H2 heading: pick one of these styles:
- "Featured Project Case – [产品名] in Action"
- "[产品名] Project Case Studies"
- "Real-World Application: [产品名]"

═══════════════════════════
Structure: 1-2 project cases
═══════════════════════════

For each case, write 3-4 sentences covering:
1. Project location and year (e.g., "Zhengzhou, China, 2023" or "Sumatra, Indonesia, 2022")
2. Scale: capacity / tonnage / production target
3. Equipment configuration: which model(s) deployed, optional accessories
4. Outcome: actual performance, customer benefit, ROI signal

Format reference (preferred concise style):
"H3: 150 t/h Construction Waste Recycling Project in Zhengzhou
A 2023 project for a municipal recycling contractor in Henan, China.
Deployed: MCP-150T mobile impact crusher + dual-deck vibrating screen + magnetic separator.
Output: 0-20 mm recycled aggregate at 145 t/h average, with steel recovery rate above 98%.
Operation: Plant relocates between 3 demolition sites annually, reducing transport cost by ~35% versus a fixed plant."

═══════════════════════════
Rules
═══════════════════════════

- ⚠️ DO NOT INVENT client names, exact countries, or proprietary data
- If you don't have real case data, use generic but plausible scenarios with a placeholder note: "[Real case to be confirmed before publish]"
- Concrete numbers > vague claims
- Avoid puffery ("amazing success", "industry-leading")
- Mention the brand name once per case (in deployment line)

FORBIDDEN words: amazing / outstanding / unparalleled / world-class / industry-leading

Output H2 + 1-2 cases directly.
```

**执行说明**：
- ⚠️ 这一模块的数据由用户提供为最佳。AI 只能写模板，**用户必须替换为真实项目**
- 输出完毕用中文显式提醒："⚠️ 案例数据是模板示意，发布前**必须**替换为你公司真实项目的地点、规模、设备型号和成效。"
- 跑完后说："**Module 7 完成**（模板）。如果你有真实案例数据告诉我，我重写一遍。回复'继续'进入 Module 8（产品对比）或'跳过 8'到 Module 9。"

---

## Module 8：产品对比（vs Comparison） [按需]

```
You are writing the "vs Comparison" section (H2) of a product page for [品牌名简称]'s [产品名].

Product A: [产品名]
Product B: [对比产品 — ask the user which competitor product to compare against if not specified]

H2 heading: pick one of these styles:
- "[产品名 A] vs [产品名 B]: Key Differences"
- "[产品名 A] vs [产品名 B]: Which to Choose"
- "Comparing [产品名 A] and [产品名 B]"

═══════════════════════════
Structure: total-detail, 200-300 words
═══════════════════════════

Paragraph 1 (overview, 2 sentences):
- Both are [equipment category], but suit different stages/scenarios
- The core difference in one phrase

Then 3-4 dimensions of comparison. Each dimension is its own short paragraph (2-3 sentences):
1. Grinding/Crushing Media (or core mechanism)
2. Output Size and Efficiency
3. Application Differences
4. [Other dimension as needed: Cost / Mobility / Setup Time]

Reference style (Rod Mill vs Ball Mill):
"Rods run nearly the full shell length and grind through line contact — pressure distributes evenly across the material layer. Balls hit through point contact, harder but less selective. Rods produce a tighter size distribution; balls generate more fines."

"Rod mills target 0.4–3 mm at 65–72% cs. Ball mills go finer at 0.074–0.4 mm, running slightly faster at 70–80% cs to maximize impact. They don't compete — they serve different size ranges."

═══════════════════════════
Comparison Table
═══════════════════════════

End with a Markdown table:

| Parameter | [产品名 A] | [产品名 B] |
|-----------|------------|------------|
| [Param 1] | ... | ... |
| [Param 2] | ... | ... |
| ... | ... | ... |

Pick parameters from this list (8-9 rows):
- Grinding Media / Mechanism
- Contact Type
- Feed Size (Max)
- Product Size
- Operating Speed
- Media Fill Rate
- Overgrinding Risk
- Wet / Dry Operation
- Circuit Position
- Capital Cost (relative)
- Setup Time
- Mobility

After table: "cs = critical speed. Figures are typical reference ranges."

═══════════════════════════
Closing recommendation
═══════════════════════════

End with ONE concrete selection rule:
"Product spec above XX mm — use a [产品名 A].
Below that — use a [产品名 B]."

Or:
"Use [产品名 A] when [scenario X].
Use [产品名 B] when [scenario Y]."

═══════════════════════════
Rules
═══════════════════════════

- Objective comparison — DO NOT trash the competitor
- Real data in every dimension
- Closing rule must be actionable, not vague

Output H2 + paragraphs + table + closing directly.
```

**执行说明**：
- 跑这个模块前必须问用户：对比产品 B 是谁（如 "stationary crushing plant" / "jaw crusher" / "fixed grinding mill"）
- 不要写"我们的更好"——客观比较，让数据说话
- 跑完后用中文说："**Module 8 完成**。请核对：(1) 对比维度是否合理 (2) 数据是否符合行业认知。回复'继续'进入 Module 9（采购指南）。"

---

## Module 9：采购指南（Selection Guide）

```
You are writing the "How to Choose" section (H2) of a product page for [品牌名简称]'s [产品名].

H2 heading: pick one of these styles:
- "How to Choose the Right [产品名]?"
- "[产品名] Selection Guide"
- "[产品名] Buying Guide"

═══════════════════════════
Structure: total-detail, 250-350 words
═══════════════════════════

Paragraph 1 (overview, 2-3 sentences):
- Why correct equipment selection matters (impact on cost / efficiency / production stability)
- Selection should be based on which core factors
- NO marketing puffery

Then list 6-8 selection points. Format:
"N. [Point title]
[1-2 sentence specific explanation. MUST include real data ranges.]"

Reference style (Mining Ball Mill):
"1. Analyze Ore Characteristics
Evaluate the ore type, hardness, abrasiveness, and moisture content, as harder or more abrasive materials increase wear on liners, grinding media, and drive systems.

2. Determine Moisture Content and Grinding Method
Select between wet and dry grinding; wet grinding is widely used in mineral processing for higher efficiency, while dry grinding suits specific industrial minerals.

3. Define Feed Size After Crushing
Ensure compatibility with upstream equipment, with typical feed sizes controlled at ≤20–25 mm depending on the mill model.

4. Specify Required Discharge Size
Determine the target fineness — commonly 75–200 μm — to achieve optimal mineral liberation for downstream beneficiation.

5. Establish Capacity Requirements
Choose a mill that meets production targets; models range from approximately 0.65–2 t/h (small) to 90–160 t/h (large)."

═══════════════════════════
Closing
═══════════════════════════

End with 1-2 sentences guiding the user to contact:
"For expert guidance and customized solutions — including [free material analysis / capacity simulation / spec recommendation] — contact [品牌名简称]."

═══════════════════════════
Rules
═══════════════════════════

- Each point's explanation must have practical reference value (no empty advice)
- MUST include data ranges (feed size ≤XX mm, capacity XX-XX t/h)
- Sound like a procurement consultant, not an AI template

FORBIDDEN words: comprehensive / paramount / robust / cutting-edge / leverage / optimize

Output H2 + overview paragraph + 6-8 numbered points + closing directly.
```

**执行说明**：
- 选型要点的数据要"采购商真用得上"——比如"轴承品牌选 SKF 或 NSK"比"选优质轴承"强 10 倍
- 至少 1 条要点要涉及"售后/备件"维度（采购商最关心的）
- 跑完后用中文说："**Module 9 完成**。请核对每条选型要点是否有实际采购参考价值。回复'继续'进入 Module 10（价格因素）。"

---

## Module 10：价格因素（Price Factors）

```
You are writing the "Price Factors" section (H2) of a product page for [品牌名简称]'s [产品名].

H2 heading: pick one of these styles:
- "What Factors Influence [产品名] Price?"
- "[产品名] Pricing Guide – What Affects Cost"
- "[产品名] Cost Factors"

═══════════════════════════
Structure: total-detail
═══════════════════════════

Paragraph 1 (overview, 2-3 sentences):
- Why no fixed price can be quoted (configuration varies by project)
- Selection of model and components causes price to span a wide range
- ⚠️ DO NOT quote specific USD prices — those depend on real-time market

Then list 5-7 cost factors. Format:
"N. [Factor title]
[1-2 sentence explanation. Include relative impact if possible (e.g., 'adds 15-25% to total cost').]"

Common factors to cover:
- Equipment Type & Stage (single-stage vs multi-stage / type of crusher / wet vs dry)
- Production Capacity & Automation Level
- Brand of Key Components (engine, bearings, hydraulic system, electric motor)
- Customization Requirements (dust suppression, magnetic separator, remote monitoring)
- Power Source (diesel-only vs hybrid vs full electric)
- Shipping & Import Duties (for overseas projects)
- Optional Accessories (feeders, screens, conveyors, control systems)

═══════════════════════════
Closing
═══════════════════════════

End with 1-2 sentences guiding to quote request:
"To get an accurate price quote, share your material type, required capacity, and site conditions with [品牌名简称]."

═══════════════════════════
Rules
═══════════════════════════

- ⚠️ DO NOT give specific USD prices — competitors can use them, and market shifts daily
- Relative percentages (e.g., "+20%") are OK
- Honest about cost trade-offs

FORBIDDEN words: affordable / cheap / unbeatable price / lowest price / best deal /
budget-friendly / cost-effective (overused, replace with specific value)

Output H2 + overview + 5-7 numbered factors + closing directly.
```

**执行说明**：
- 这板块**绝对不能**写具体 USD 数字（"$50,000-$200,000" 这种）——既不准也降低询盘
- 强调"配置驱动价格"和"咨询定制方案"，引导询盘
- 跑完后用中文说："**Module 10 完成**。请核对：(1) 是否漏了你产品类别的关键价格驱动因素 (2) 没有出现具体 USD 报价。回复'继续'进入 Module 11（定制方案）。"

---

## Module 11：定制方案（Custom Solutions）

```
You are writing the "Custom Solutions" section (H2) of a product page for [品牌名简称]'s [产品名].

H2 heading: pick one of these styles:
- "Custom [产品名] Solutions – Tailored to Your Site"
- "Tailored [产品名] Solutions for Your Project"
- "Customization Options for [产品名]"

═══════════════════════════
Structure: total-detail
═══════════════════════════

Paragraph 1 (overview, 2-3 sentences):
- [品牌名简称] offers customization based on customer's material, site, and capacity requirements
- Mention 2-3 dimensions where customization happens (e.g., chassis type, dust control, automation)
- Lead-in for the list below

Then list 4-6 customization options. Format:
"[Option title]
[1-2 sentence explanation of what's customizable and the typical use case.]"

Common customization areas (pick relevant ones to the product):
- Modular Design – Add or remove modules as needed
- Dust & Noise Control Package for environmental compliance
- Remote Monitoring & Control System Option
- Material-Specific Wear Parts (martensitic / 18% Mn / ceramic composite liners)
- Power Source Options (diesel, electric, hybrid)
- Conveyor & Screen Configuration (mesh size, deck count, return system)
- Color & Branding Customization (for distributor partners)
- Climate Adaptation (cold-region heating, tropical sealing)

═══════════════════════════
Closing CTA
═══════════════════════════

End with a clear CTA inviting quote request:
"Share your material specifications, required output size, hourly capacity, and site conditions — [品牌名简称]'s engineering team will design a tailored [产品名] solution for your project."

Optional CTA button text: "Request a Custom Solution" or "Get a Tailored Quote"

═══════════════════════════
Rules
═══════════════════════════

- Customization options must be REAL (don't promise color-changing if you don't do it)
- Each option should link to a real buyer need
- CTA must be specific about what info to share

FORBIDDEN words: limitless / unlimited / endless / fully customizable (vague)

Output H2 + overview + 4-6 options + CTA directly.
```

**执行说明**：
- 4-6 个定制项里至少 1 个跟"环保合规"相关（出口市场关注点）
- CTA 要具体——告诉客户提交什么信息（物料、产能、场地）才能拿到定制方案
- 跑完后用中文说："**Module 11 完成**。请核对每个定制项是否符合你公司真实能力。回复'继续'进入 Module 12（制造商介绍）。"

---

## Module 12：制造商介绍（Manufacturer & Supplier）

⚠️ **这个板块特别重要，AI 最容易输出薄弱内容。必须严格执行下述要求。**

```
You are writing the "Why Choose [品牌名简称]" section (H2) of a product page.

Brand short name: [品牌名简称]
Brand full legal name: [品牌名全称]
Product: [产品名]
Industry: [行业领域]

H2 heading: pick one of these styles:
- "[产品名] Manufacturer & Supplier – Why Choose [品牌名简称]"
- "Why Choose [品牌名简称] as Your [产品名] Supplier"
- "[品牌名简称]: Your [产品名] Partner"

═══════════════════════════
⚠️ STRICT FORMAT RULES
═══════════════════════════

❌ DO NOT use bullet lists, numbered lists, or sub-headings
✅ MUST be flowing paragraphs only
✅ MUST be exactly 2 paragraphs
✅ Total length: 180-250 words

═══════════════════════════
Paragraph 1 (3-4 sentences):
═══════════════════════════

Cover these elements in flowing prose:
- Brand positioning (e.g., "professional manufacturer and supplier")
- Equipment core advantages (use data, not platitudes — e.g., "precise particle size control, stable throughput, improved downstream recovery")
- How the brand helps customers select equipment (analyzing ore characteristics, capacity requirements, site conditions)
- Value of the solution (improves efficiency, reduces energy consumption, lowers operating cost)

First sentence MUST use the full legal name, e.g.:
"As a professional manufacturer of [行业领域] equipment, [品牌名全称] delivers reliable [产品名] for [primary applications]."

Subsequent sentences can use short name.

═══════════════════════════
Paragraph 2 (3-4 sentences):
═══════════════════════════

Cover these elements in flowing prose:
- Years of project experience (e.g., "With 15+ years of engineering experience")
- Industries / minerals / projects where you have track record (e.g., "gold, iron, copper, non-ferrous metal projects")
- Certifications (e.g., "ISO9001 / CE quality standards")
- Comprehensive services (process design → equipment manufacturing → installation guidance → operator training → spare parts supply)
- Closing line: "[品牌名简称] is a trusted partner for [target customer type] worldwide."

═══════════════════════════
Reference style (Mining Ball Mill):
═══════════════════════════

"As a professional manufacturer and supplier, Zhongyi Mining Machinery provides reliable mining ball mills designed to meet the demands of modern mineral processing. A properly selected mill ensures precise particle size control, stable throughput, and improved downstream recovery. By analyzing ore characteristics, capacity requirements, and site conditions, Zhongyi delivers tailored grinding solutions that enhance efficiency, reduce energy consumption, and lower operating costs.

With extensive experience in gold, iron, copper, and non-ferrous metal projects, Zhongyi offers comprehensive services from process design and equipment manufacturing to installation guidance and operator training. We obtained ISO9001 quality control and internationally recognized certifications, and dependable support, is a partner for global mining operations."

═══════════════════════════
Rules
═══════════════════════════

- ⚠️ MUST be paragraphs (no bullets)
- MUST include: years experience, certifications, project areas, comprehensive services
- Sound like a real corporate intro with substance — not an AI template
- Avoid empty adjectives ("excellent", "premium") — use specific facts

FORBIDDEN words: world-class / industry-leading / unparalleled / top-tier /
state-of-the-art / cutting-edge / paramount / robust / holistic / comprehensive

Output H2 + 2 paragraphs directly. No bullets allowed.
```

**执行说明**：
- ⚠️ **核对输出**：若 AI 偷偷用了项目符号或编号列表，立刻重写为段落
- 第一段第一句必须用全称（如 "Henan Xinzhongyi Environmental Protection Equipment Co., Ltd."），让 Google 抓取到法人主体
- 之后用简称（如 Zhongyi）保持流畅
- 跑完后用中文说："**Module 12 完成**。请核对：(1) 经验年限是否符合实际 (2) 认证是否你公司真有 (3) 服务范围是否你公司能兑现。⚠️ 不能虚标。回复'继续'进入 Module 13（FAQ）。"

---

## Module 13：FAQ（8 条常见问题）

```
You are writing the FAQ section (H2) of a product page for [品牌名简称]'s [产品名].

You are role-playing as the potential buyer. Before making a purchase decision,
what are the questions buyers most care about?

H2 heading: "Frequently Asked Questions About [产品名]"
(or shorter: "FAQ About [产品名]")

═══════════════════════════
Format
═══════════════════════════

Q: [Question — buyer's voice, like a real customer would ask]
A: [Answer — keep ≤40 words and ≤300 characters]

8 FAQ pairs total.

═══════════════════════════
Coverage requirements (8 FAQ MUST cover ALL of these, at least 1 each)
═══════════════════════════

❶ Product purpose (What is it used for)
❷ Specifications (Feed size / Discharge size / Capacity)
❸ Suitable scenarios (Suitable for specific material/industry)
❹ Comparison choice (vs similar products)
❺ Price factors (What affects price)
❻ Supplier selection (How to choose supplier)
❼ Delivery / after-sales (Delivery time / Installation support)
❽ Wear parts / maintenance (Wear parts / Maintenance frequency)

═══════════════════════════
Optimization requirements
═══════════════════════════

Featured Snippets optimization:
- FIRST SENTENCE of each answer = direct conclusion (Google will extract this)
- Answer must be self-contained (still makes sense if extracted alone)
- Concise declarative sentences, no warm-up

GEO optimization:
- Answer directly addresses real buyer concerns
- Include specific data where possible (feed size ≤XX mm, delivery 30-60 days, etc.)
- Avoid generic platitudes

Brand keyword:
- 1-2 answers naturally mention [品牌名简称] — NOT every answer

═══════════════════════════
Reference style
═══════════════════════════

"Q: What is a mining ball mill used for?
A: A mining ball mill is used to grind crushed ore to the particle size required for downstream mineral processing. It is commonly installed between crushing and recovery stages such as flotation, leaching, gravity separation, or magnetic separation.

Q: Is a ball mill suitable for gold mining?
A: Yes. A ball mill is widely used in gold processing because it can grind crushed gold ore to the size needed before gravity recovery, flotation, or cyanidation.

Q: What is the delivery time for a rod mill?
A: Standard delivery typically ranges from 30 to 60 days, depending on equipment specifications, customization requirements, and production schedules."

═══════════════════════════
Rules
═══════════════════════════

- Each answer ≤40 words, ≤300 characters (count carefully)
- First sentence = direct answer (snippet-ready)
- Cover ALL 8 dimensions above
- Mention brand in 1-2 answers max

FORBIDDEN openings: In today's world / It is worth noting / When it comes to /
One of the key

FORBIDDEN words: comprehensive / robust / cutting-edge / seamless / leverage

Output H2 + 8 Q&A pairs directly.
```

**执行说明**：
- 8 维度必须全覆盖——若某条问题没匹配维度，重写
- 答案字符数严格控制（≤300 字符）——超了被 Featured Snippets 截断
- 跑完后用中文说："**Module 13 完成**。这是产品页 SEO 的最后一个模块。建议你过一遍人工 checklist（见下方）。"

---

## 整套跑完后的人工终审清单（输出给用户）

```
═══════════════════════════
Product Page Final Review Checklist
═══════════════════════════

TDK
□ Title within 55-65 chars, includes core keyword + brand
□ Description within 140-160 chars, summarizes page value
□ Keywords 5-8, no stuffing
□ URL short, hyphenated, includes core keyword

Hero
□ H1 direct, no warm-up
□ Hero paragraph 3-4 sentences
□ 4 core parameters listed with realistic ranges
□ CTA button text clear

Body sections
□ Definition / Overview accurate to your real product
□ How it Works: 4-step process flow correct
□ Specifications table: data matches your actual product manual ⚠️ MUST VERIFY
□ Applications: covers your real customer industries
□ Selection Guide: 6-8 points with practical data
□ Price Factors: NO specific USD prices given
□ Custom Solutions: every customization option is real (you can deliver)

Manufacturer section
□ 2 paragraphs (NOT bullet lists)
□ Full legal name in first sentence
□ Years experience matches reality
□ Certifications match reality (ISO9001, CE, etc.)
□ Comprehensive services list matches what you can actually deliver

FAQ
□ 8 Q&A covering all 8 dimensions
□ Each answer ≤40 words, ≤300 chars
□ First sentence = direct answer
□ Brand mentioned in 1-2 answers max

SEO + GEO
□ Core keyword distributed naturally throughout
□ LSI keywords appear in section headings + body
□ H2 hierarchy logical
□ No keyword stuffing

AI Check
□ Zero forbidden words across all sections
□ Reads like industry engineer / procurement consultant wrote it
□ Specifications and data realistic (not perfectly round numbers)
□ Brand mentioned naturally, not stuffed
```

输出完后用中文说："**全部模块完成**。请你手动过一遍这个清单。⚠️ 重点核对：(1) Module 5 参数表必须对照你公司真实产品手册 (2) Module 7 案例数据必须替换为真实项目 (3) Module 12 制造商介绍的经验年限和认证必须真实。"

---

## 全局禁用词库（贯穿所有模块）

### 禁用开头
- In today's world / In today's fast-paced world
- With the development of
- In recent years
- It is worth noting that
- When it comes to
- One of the key
- At its core

### 禁用结尾
- In conclusion
- To sum up
- As we have seen
- In summary
- Ultimately
- The future looks bright

### 禁用词汇
- comprehensive / paramount / holistic / delve into / robust
- cutting-edge / game-changer / revolutionize / unlock / leverage
- enhance / optimize / seamless / innovative
- plays a vital role / Not only ... but also ...（机械堆砌时）
- world-class / industry-leading / unparalleled / top-tier / state-of-the-art

### 价格板块特别禁
- affordable / cheap / unbeatable / lowest price / best deal / budget-friendly
- cost-effective（过度使用，要用具体价值代替）

### 模糊数量词（必须换成具体数字）
- various / numerous / many / a lot of / wide range of / multiple

### 其他 AI 痕迹（手动盯）
- 三段式排比（rule of three 滥用）
- 每段开头都是同句式
- 大量 em dash（—）当万能连接符
- 加粗滥用（一段三四处加粗）
- 标题用 Title Case 当装饰
- 制造商板块用项目符号代替段落（❌ 严格禁止）

---

## 调用方式

### 整套调用

```
/product-seo-zh
```

或自然语言："写产品页 / 按产品页流程做 / 帮我做完整产品页"

→ 跑阶段 0.5 → Module 0 → 13（顺序）

### 单模块调用

```
/product-seo-zh faq         (只跑 FAQ)
/product-seo-zh specs       (只跑参数表)
/product-seo-zh manufacturer (只跑制造商介绍)
/product-seo-zh comparison  (只跑产品对比)
```

或自然语言："只跑 FAQ" / "跑参数表" / "做制造商介绍" / "跑工作原理那段"

→ 跑阶段 0.5（如果还没跑过）→ 只跑指定 Module

### 跑多个模块（不是全套）

自然语言："跑 module 5 6 7" / "做 Specs + Applications + FAQ"

→ 按指定顺序跑指定的 Modules

## 何时不该用本 skill

- 写**博客文章** → 用 `blog-seo-zh`
- 写**集合页 / 解决方案页** → 考虑 `humanizer-seo`（如果有大纲）或本 skill 改造
- **改写一段已有 AI 草稿** → 用 `humanizer-seo`
- 写**中文产品页** → 本 skill 是英文产出的

## 与 blog-seo-zh / humanizer-seo 的关系

| 维度 | product-seo-zh（本 skill） | blog-seo-zh | humanizer-seo |
|------|---------------------------|-------------|---------------|
| 页面类型 | 产品页（commercial） | 博客（informational） | 产品/集合/方案页 |
| 流程 | 模块化（13 个 Module） | 顺序工作流（8 阶段） | 单次改写 |
| 起点 | 产品名（从零开始） | 关键词（从零开始） | 已有大纲/草稿 |
| 产出 | 完整产品页 + TDK + FAQ | 整篇博客 + TDK + FAQ | 改写后的内容 |
| 字数 | 视模块而定 | 1500-2000 字 | 视页面类型 |

三者互补：

- 写**产品页**用本 skill
- 写**博客**用 blog-seo-zh
- 任何 AI 草稿想要"去 AI 味"，最后过一次 humanizer-seo

如果你公司同时跑这三个工作流，建议这样组合：
1. 用 blog-seo-zh 写 informational 博客带流量
2. 用本 skill（product-seo-zh）写产品页接询盘
3. 用 humanizer-seo 给所有最终稿做去 AI 痕迹精修
