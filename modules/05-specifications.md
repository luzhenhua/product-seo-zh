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
Disclaimer after table (≤30 words, vary phrasing each time)
═══════════════════════════

Pick ONE pattern, swap the specific conditions to match the product:

Pattern A (with reference condition stated):
"Note: Figures based on [medium-hard limestone (bulk density 1.6 t/m³)] with [closed-circuit screening]. Actual capacity varies with material hardness, feed gradation, moisture. Contact [品牌名简称] for a recommendation based on your material test report."

Pattern B (generic reference values):
"Specifications above are reference values. Actual [capacity / sorting accuracy] varies with material type, [key variable 1], and [key variable 2]. Contact [品牌名简称] for model selection based on your process conditions."

Pattern C (shortest):
"These figures are for reference only. Final selection should match actual material characteristics and process conditions."

⚠️ ≤30 words total. Do not use 50+ word disclaimers — they look like AI boilerplate.

═══════════════════════════
Rules
═══════════════════════════

- Capacity range spans small to industrial scale
- Numbers must look credible (not perfectly round)
- Model names follow real industry convention

**Word-count hard cap (see [reference/writing-consistency.md](../reference/writing-consistency.md)):**
- Hard cap **180 words total** = 30 prose (disclaimer + optional matrix-table intro) + 150 table budget
- Counts ALL: every table header + every cell + disclaimer + intro
- If single main spec table only → ~70 words table budget + ≤110 words spare for prose
- If main spec table + differentiation matrix table → main ~70 + matrix ~80 + prose 30 = 180
- If matrix table exceeds 80 → trim main spec rows from 7 to 5-6, NOT expand prose

Output the H2 + table + disclaimer directly. No extra prose.
```

**执行说明**：
- 这是**唯一一个不需要长文字的板块**，主体就是表格
- 表格数据宁可范围（如 15-28 t/h）也不要单值，让采购商有参考也方便后续询盘细化
- 跑完后用中文说："**Module 5 完成**。⚠️ 这些参数是估算值，发布前**必须**核对你公司实际产品手册的数据。回复'继续'进入 Module 6（应用场景）。"

---

