## Module 12：制造商介绍（Manufacturer & Supplier）

⚠️ **这个板块特别重要，AI 最容易输出薄弱内容。必须严格执行下述要求。**

═══════════════════════════
执行前必做（One-Shot 模式也要做）
═══════════════════════════

1. **读跨页日志**：尝试 Read `~/.claude/skills/product-seo-zh/track_record_log.md`
   - 若文件存在，查看最近 5 行的"地区组合 / 项目数 / 经验年数 / **核心差异化角度**"
   - 若文件不存在，跳过（生成完后会建）
2. **本次输出必须 vary**：选一组与最近 5 行**至少 2 项不同**的"地区 + 项目数 + 经验年数"组合
3. **吃竞品 brief**：本段第 2 段的"track record / services" 描述里，**至少 1 句**要呼应阶段 0.7 的差异化角度（如差异化是"湿料处理"，就在 service scope 里写 "process design for wet and clay-bound feeds"，而不是泛泛的 "process design"）
4. **生成完后**：用 Edit/Write 追加一行新记录到日志（见下方"执行后必做"），新行字段包括本次的核心差异化角度和竞品参考 URL

```
You are writing the "Manufacturer & Supplier" section (H2) of a product page.

Brand short name: [品牌名简称]
Brand full legal name: [品牌名全称]
Product: [产品名]
Industry: [行业领域]

H2 heading: pick one of these styles (vary across product pages):
- "[产品名] Manufacturer & Supplier — [品牌名简称]"
- "[品牌名简称] — [产品名] Manufacturer & Supplier"
- "Why Choose [品牌名简称] as Your [产品名] Supplier"

═══════════════════════════
⚠️ STRICT FORMAT RULES
═══════════════════════════

❌ DO NOT use bullet lists, numbered lists, or sub-headings inside this section
✅ MUST be flowing paragraphs only
✅ MUST be exactly 2 paragraphs
✅ Total length: 110-170 words

═══════════════════════════
Paragraph 1 (2-3 sentences): Brand positioning
═══════════════════════════

Cover in flowing prose:
- Brand positioning (professional manufacturer of [product category] for [industry])
- ONE specific value statement (use data, not platitudes — e.g., "A correctly specified mobile plant reduces haulage cost by 30–50% compared to fixed lines")
- How [品牌名简称] helps customers spec the equipment (evaluates material / capacity / site conditions)

First sentence MUST use the **full legal name**. Pick ONE of two templates (vary across pages):

TEMPLATE A — "As a manufacturer, Brand delivers..." (verb-first):
"As a professional manufacturer of [行业领域] equipment, [品牌名全称] delivers [产品名] for [primary applications]. [Value statement with data]. [品牌名简称] evaluates your material [hardness / type], capacity needs, and site conditions to configure the right [key spec area]."

TEMPLATE B — "Brand is a manufacturer of..." (subject-first):
"[品牌名全称] is a professional manufacturer of [产品名] for [行业领域], delivering [key value with data anchor]. By evaluating [material characteristics / capacity / site conditions], [品牌名简称] configures the right [chassis / sensor / drive / etc.] for each project."

Pick the template that AVOIDS repeating the hero paragraph's opening structure. If hero opens "Zhongyi provides...", use Template A. If hero opens with company name, use Template B.

═══════════════════════════
Paragraph 2 (3-4 sentences): Track record + services
═══════════════════════════

Cover in flowing prose:
- Years of project experience (varies — see Track Record Policy below)
- Industries / minerals with track record (5-7 specific items, not "various")
- Project geography (regions list — see Track Record Policy below)
- Certifications (ISO9001:2015, CE — match what the brand actually has)
- Service scope (process design / commissioning / training / spare parts)
- Closing line: "[品牌名简称] is a trusted partner for [target customer type] worldwide."

Reference style (Mobile Crusher):
"We have over 18 years of engineering experience in crushing systems for limestone, granite, gold ore, iron ore, and C&D waste, Zhongyi has delivered 500+ mobile crushing units to projects across Southeast Asia, Africa, South America, and the Middle East. Our ISO9001:2015 certified factory and CE-marked components ensure consistent build quality. We provide process layout design, chassis customization, on-site installation supervision, operator training, and a ready stock of wear parts. Zhongyi is a trusted partner for contractors and mining companies seeking field-proven mobile crushing solutions."

═══════════════════════════
Track Record Fabrication Policy
═══════════════════════════

✅ ALLOWED (improves conversion, no Google penalty):
- **Regional lists** — pick 3-5 from: Southeast Asia / South Asia / Africa / South America / Middle East / Europe / North America. VARY combinations across product pages (avoid templated repetition).
- **Cumulative project counts** — plausible range matching brand scale (200+ / 320+ / 380+ / 500+ / 800+). Vary across product lines (flagship products higher, side products lower).
- **Years of experience** — 14-18 years range. Small vary per product page (e.g., main crusher line 18 years, newer color sorter 14 years).
- **Industry list** — 5-7 specific industries (gold, iron, copper, limestone, coal, C&D waste, etc.).

⚠️ MUST VARY across consecutive product pages (per [跨页日志] mechanism):
- Region combination should differ from last 5 entries by ≥2 items
- Project count should land in different range
- Years figure should fluctuate ±2 years

❌ FORBIDDEN (Google penalty / legal risk):
- Specific client/company names (e.g., "PT Adaro Energy", "Tata Steel")
- Specific facility addresses, GPS, block numbers
- Customer testimonials with names + photos
- schema.org Review/Rating markup
- Implausible scale (small Henan SME claiming 50,000+ global installations)
- Same regional combo + same project count + same years across multiple product pages (looks templated, Google flags as low-value generated content)

═══════════════════════════
Rules
═══════════════════════════

- ⚠️ MUST be paragraphs (no bullets, no sub-headings)
- MUST include: years experience, regional track record, project count, certifications, service scope
- Sound like a real corporate intro with substance — not an AI template
- Avoid empty adjectives ("excellent", "premium") — use specific facts

FORBIDDEN words: world-class / industry-leading / unparalleled / top-tier /
state-of-the-art / cutting-edge / paramount / robust / holistic / comprehensive

**Word-count hard cap (see [reference/writing-consistency.md](../reference/writing-consistency.md)):**
- Hard cap **170 words total** (2 paragraphs)
- First paragraph ~70 words (positioning); second ~100 words (track record + service)
- Over cap → cut the weakest sentence; do NOT exempt for "multi-material coverage requires longer scope"
- All certifications, regional lists, and service scope fit within cap by trimming adjectives and merging clauses, NOT by adding sentences

Output H2 + 2 paragraphs directly. No bullets allowed.
```

═══════════════════════════
执行后必做
═══════════════════════════

1. **追加一行到日志** `~/.claude/skills/product-seo-zh/track_record_log.md`：
   ```
   | YYYY-MM-DD | [产品名] | [品牌简称] | [本次地区组合] | [本次项目数] | [本次年数] | [行业列表] | [本次核心差异化角度 1-2 个] | [竞品参考 URL 1-3 个] | ⚠️ 草稿待审 |
   ```
2. 若文件不存在，先创建（含表头，参见 track_record_log.md 当前格式）
3. 自检报告里报告"本篇用 [地区组合] + [项目数] + [年数] + [差异化角度]，已记入跨页日志（状态：⚠️ 草稿待审，发上线后请手动改为 ✅ 已发布）"

**执行说明**：
- ⚠️ **核对输出**：若 AI 偷偷用了项目符号或编号列表，立刻重写为段落
- 第一段第一句必须用全称（如 "Henan Xinzhongyi Environmental Protection Equipment Co., Ltd."），让 Google 抓取到法人主体
- 之后用简称（如 Zhongyi）保持流畅
- 双模板二选一，跟 Hero 段开头结构错开避免重复感
- 跑完后用中文说（仅 step-by-step 模式）："**Module 12 完成**。请核对：(1) 经验年限合理 (2) 认证你公司真有 (3) 地区组合与最近几篇不同 (4) 项目数 plausible。回复'继续'进入 Module 13（FAQ）。"

---

