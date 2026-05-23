## Module 0：总策划（TDK + URL + 完整架构）

**执行前必做**：拿到阶段 0.7 输出的「竞品 brief」。如果用户跳过了 0.7（不推荐），用中文提醒"未跑竞品研究，本篇 H1-H14 可能与你最近几篇雷同，建议补跑 0.7"，然后再继续。

```
You are a senior B2B SEO strategist designing a product page for [品牌名简称]
(full legal name: [品牌名全称]) in the [行业领域] industry.

Target keyword: [产品名]
Target reader: [目标读者]

Competitor brief (from 阶段 0.7):
- High-frequency H2 topics: [已被讲烂的话题，本篇也要讲但要换角度]
- Low-frequency / unique angles: [独特角度清单，本篇可以借鉴]
- Differentiation lock (1-2 angles): [本篇主推的差异化角度]
- H2 adjustment suggestions: [新增 / 替换 / 砍掉 的 H2]

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
PART 2: Full H1-H14 Architecture (with differentiation)
═══════════════════════════

Standard skeleton (use as default, but ADJUST based on competitor brief):

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

⚠️ DIFFERENTIATION RULES (mandatory — this is what prevents template feel):

1. **Insert 1-2 unique H2** based on competitor brief's "low-frequency / unique angles" list.
   Examples: "Maintenance Cost & Spare Parts Lifecycle" / "Handling Wet & Sticky Materials" /
   "Energy Consumption Benchmarks" / "Used vs New Equipment Decision".
   Position the unique H2 between standard H2s where it fits the buyer journey.

2. **Replace 1 standard H2 with an angle-loaded version** if competitors all use the bland default.
   Example: instead of "How it Works" use "How a [产品名] Handles [Differentiation Angle]";
   instead of "Applications" use "[产品名] in [Specific Differentiation Scenario]".

3. **Cut 1-2 standard H2** if not relevant to this product or already covered by competitor brief
   as low-value (e.g., skip "Types" for a single-model product, skip "vs Comparison" if no
   meaningful competitor product exists).

4. **Final H2 count should be 12-14**, not necessarily exactly 14. Quality > completeness.

For each H2, list 3-6 H3 sub-topics where useful.

Requirements:
- All headings cover search intent (informational + commercial + comparison)
- Naturally integrate 1-2 related keywords per heading — NO stuffing
- H2 styles mixed: question / statement / guide
- Don't make every page H2 identical — vary phrasing
- ⚠️ Compare your H2 list against last 3-5 entries in track_record_log: if ≥3 H2 phrasings
  are identical to a recent page, rewrite them.
```

**执行说明**：
- Title 2 个备选必须**算字符数**写在括号里（如 `(58 chars)`）
- Description 同上
- H2 数量 12-14（按需跳的 Module 4/7/8 决定 + 差异化新增/砍掉决定）
- 输出 H2 列表后，**单独列一段中文**："本篇差异化 H2 是 [X] 和 [Y]，对应阶段 0.7 锁定的角度 [Z]；与最近 N 篇产品页的不同点是 [W]。"
- ⭐ **必跑收尾**：H2 列表 + 差异化说明之后，必须输出**「本篇风格基线」**摘要（见 [reference/writing-consistency.md](../reference/writing-consistency.md)），让后续 11 个生成型 Module 锚定。格式如下：

```
═══════════════════════════
本篇风格基线（后续 Module 锚定）
═══════════════════════════

📏 字数硬上限（**全文 ≤2,000 词总预算反推**，含表格 Module 字数 = 正文 + 全部表格单元格）：
- Module 1 Hero: 短 ≤55 / 长 ≤110
- Module 2 What Is: ≤180
- Module 3 How Works: ≤180
- Module 4 Types: ≤180（150 正文 + 30 小表）
- Module 5 Specs: ≤180（30 prose + 150 双表预算）
- Module 6 Applications: ≤250
- Module 7 Project Case: ≤230（170 叙述 + 60 参数表）
- Module 8 vs Comparison: ≤170（110 散文 + 60 对比表）
- Module 9 Selection Guide: ≤220
- Module 10 Price Factors: ≤200
- Module 11 Custom Solutions: ≤130
- Module 12 Manufacturer: ≤170
- Module 13 FAQ: ≤240 总（每答 ≤30）

**全文累计验算**：跳 7+8 必跑 ~1,985 词 ✓；加 7 或 8 之一会到 ~2,155-2,215，超出 boss 红线
- 跑前确认是否含 7 / 8。如果含，自动把其他模块按各 -10% 同步压缩，保整体 ≤2,100。

✍️ 写作锚点（跨 Module 保持一致）：
- bullet 平均长度：[根据本篇产品复杂度选 短(12-20 词)/ 中(20-30 词)/ 长(30-40 词)]
- 段落平均：[2-3 句 / 段]，每句 [18-30 词]
- 数据密度目标：每 100 词 ≥4 个具体数据点（带单位/区间/百分比/时间）
- 数字区间表示：[选 en dash "–" 或 hyphen "-"，全篇统一]
- 单位表示：[关键单位首次出现时锁定，如 kcal/kg vs kcal per kg]
- em dash 段内密度：每段 ≤2 处（bullet 引导不限），跨 Module 一致

🎯 差异化角度处理原则（必读）：
- 角度落地优先放表格，不蔓延段落
- 每个 bullet 1 句 + 1 数据锚，不扩成 2 句 + 3 数据点
- 角度复杂度高（如 5 物料 × 6 维度）→ 加独立表格放 Module 5/8，不在段落里展开
- "差异化深度 ≠ 段落长度"——深度由数据密度决定，不由字数决定
```

- 跑完后用中文说："**Module 0 完成**，这是总骨架 + 风格基线。请确认 / 调整 H2 标题。回复'继续'进入 Module 1（H1 + 首屏），或说'跳过某 module'。"

---

