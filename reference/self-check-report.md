### 一次性模式自检报告模板

整套跑完输出（在最终交付的英文产品页内容**下方**用中文呈现）：

```
═══════════════════════════
本篇产品页自检报告
═══════════════════════════

🎯 差异化锁（来自阶段 0.7 竞品研究）
- 调研竞品：N 个（[竞品 URL 1] / [竞品 URL 2] / ...）
- 本篇主推角度：[角度 1] + [角度 2]
- 落地位置：Module 1 Hero / Module 2 定义 / Module 6 应用 / Module 9 选型 / Module 13 FAQ
- 与最近 N 篇产品页的不同点：[简要说明]

📊 字数统计
- 全文字数：XXXX 字（**boss 红线 ≤2,000 词**；含 Module 7 或 8 → ≤2,100；全跑 → ≤2,200 不推荐）
- 各模块字数 + **硬上限检查**（见 [writing-consistency.md](writing-consistency.md)，**含表格 Module 字数 = 正文 + 全部表格单元格**）：
  Module 1 Hero: XX 字 / 硬上限 55 (短) / 110 (长) [✅/❌]
  Module 2 What Is: XXX 字 / 硬上限 180 [✅/❌]
  Module 3 How Works: XXX 字 / 硬上限 180 [✅/❌]
  Module 4 Types: XXX 字（正文 + 表格）/ 硬上限 180 [✅/❌]
  Module 5 Specs: XXX 字（prose + 主表 + 可选矩阵表全部单元格）/ 硬上限 180 [✅/❌]
  Module 6 Applications: XXX 字 / 硬上限 250 [✅/❌]
  Module 7 Project Case: XXX 字（叙述 + 参数表全部单元格）/ 硬上限 230 [✅/❌]
  Module 8 vs: XX 字（散文 + 对比表全部单元格）/ 硬上限 170 [✅/❌]
  Module 9 How to Choose: XXX 字 / 硬上限 220 [✅/❌]
  Module 10 Price: XXX 字 / 硬上限 200 [✅/❌]
  Module 11 Custom: XX 字 / 硬上限 130（含询盘表 bullet）[✅/❌]
  Module 12 Manufacturer: XXX 字 / 硬上限 170 [✅/❌]
  Module 13 FAQ: XXX 字总 / 硬上限 240（每答 ≤30 词）[✅/❌]
- **任何 ❌ → 必须重写该 Module**，不允许豁免
- **全文 > 2,000 词 → 必须裁**，按各模块 -10% 同步压缩

🎨 风格一致性检查（见 [writing-consistency.md](writing-consistency.md)）
- bullet 平均长度跨 Module 是否在 ±30% 区间：✅/⚠️/❌
- 段落平均长度跨 Module 是否在 ±25% 区间：✅/⚠️/❌
- 数据密度：每 100 词含具体数据点数（目标 ≥4）：X.X 个
- 数字区间表示全篇统一（en dash "–" vs hyphen "-"）：✅/❌
- 单位表示全篇统一（如 kcal/kg）：✅/❌

🔍 品牌词频率检查（领导反馈重点）
- Hero Paragraph 品牌词次数：X / 1 （✅ 0-1 / ❌ ≥2）
- 全文品牌简称密度：XX 次 / YYYY 字 ≈ Z.Z% （目标 0.8%–1.5%，✅/⚠️/❌）
- 如果 Hero ≥ 2 次或全文 > 1.5%：⚠️ 必须重写违规段落

⚠️ 待人工核对（按用户身份套用强度，详见 [reference/user-context.md](user-context.md)）

**默认场景（SEO 服务商代写）**：
- Module 5 参数表：plausibility check — 看是否有明显造假（如小厂 1,000 t/h 微型机），无明显问题可直接发布
- Module 7 案例：**虚构脱敏案例已通过 5 项 plausibility self-check**（行业-区域匹配 / 数据内部一致 / 差异化角度落地 / 不与竞品已发布案例冲突 / 数据在 ±20% 行业基准内）。地点用国家+区域级（如 "northern India"），客户描述通用化（如 "a cement plant operator"），无具体公司名/城市/testimonial。可直接发布；若发布前有客户真实项目数据，可替换。
- Module 12 Manufacturer：本篇用 [地区组合] + "XXX+ units" + "XX+ years experience" + [差异化角度]，已记入跨页日志（状态：⚠️ 草稿待审）
- Module 13 FAQ：数据与 Module 5 表是否一致

**厂家自写场景（用户在阶段 0.5 选了"品牌方"）**：
- Module 5 参数表：⚠️ MUST VERIFY — 必须对照贵司真实产品手册逐行核对
- Module 7 案例：⚠️ MUST REPLACE — 项目地点和数据必须替换为真实项目（叙述模板可保留，数字必须替换）
- Module 12 Manufacturer：⚠️ 经验年数、项目数、认证必须真实
- Module 13 FAQ：数据必须与 Module 5 + 真实产品手册一致

📁 跨页日志已更新：~/.claude/skills/product-seo-zh/track_record_log.md
   状态：⚠️ 草稿待审。**领导审完发上线后，请手动把此行末尾改为 ✅ 已发布**（方便下次跑产品页时主动避开重复角度）。
```

---

