# Track Record Log

本文件由 `product-seo-zh` skill 自动维护。

**用途**（两个）：
1. 跑 Module 12 Manufacturer 前 AI 自动读，避免连续多篇产品页用同一组地区 / 项目数 / 年数，防止 Google 把站点判定为"模板化生成内容"。
2. 跑阶段 0.5（变量声明）和 Module 0（总策划）前 AI 自动读，看历史"核心差异化角度"和"H2 结构"，主动避开已用过的角度，让每篇产品页都不一样。

**机制**：
- 阶段 0.5 / Module 0 / Module 12 跑之前 → Read 此文件
- 生成时 → 主动 vary 地区、项目数、年数、**以及核心差异化角度和 H2 结构**
- 生成后 → 用 Edit 追加新行，并标注是否已发布

**规则**：
- 地区池：Southeast Asia / South Asia / Africa / South America / Middle East / Europe / North America
- 每篇用 3-5 个地区（不要全列 7 个，会失真）
- 项目数：plausible 范围 200+ / 320+ / 380+ / 500+ / 800+
- 经验年数：14-18 年区间小幅 vary
- **核心差异化角度**：每篇必填 1-2 个"竞品没怎么讲但本篇重点讲"的角度（如 "维护成本对比" / "湿料处理" / "热回收"）
- **已发布状态**：✅ 已发布 / ⚠️ 草稿待审 / ❌ 弃稿。领导审完发上线后回来更新

---

## 历史记录

| 日期 | 产品 | 品牌 | 地区组合 | 项目数 | 经验年数 | 行业列表 | 核心差异化角度 | 竞品参考 URL | 状态 |
|---|---|---|---|---|---|---|---|---|---|
| <!-- 示例：2026-05-20 | Vibrating Screen | Zhongyi | SEA + Africa + ME | 320+ | 15+ | coal, aggregate, recycling | 湿料防堵 + 节能驱动 | competitorA.com/x, competitorB.com/y | ✅ 已发布 --> |
| 2026-05-20 | Alumina Rotary Kiln | Zhongyi | SEA + S.Asia + ME + S.America | 200+ | 16 | alumina, calcined kaolin, magnesite, refractory, lithium carbonate, limestone | - | - | ⚠️ 草稿（旧字段） |
| 2026-05-21 | Lime Rotary Kiln | Zhongyi | Africa + Europe + North America + Middle East | 380+ | 18 | steel, sugar refining, magnesium smelting, construction lime, chemical processing, aggregate | - | - | ⚠️ 草稿（旧字段） |
| 2026-05-22 | Rubber Tyre Mobile Screening Station | Zhongyi | S.Asia + SEA + Africa + S.America | 320+ | 15 | limestone, granite, river pebble, coal, iron ore, construction demolition waste | 筛网维护便利性 + 备件供应 / 轮胎式 vs 履带式选型决策 | - | ⚠️ 草稿待审 |
| 2026-05-22 | Rubber Tyre Mobile Screening Station (v2) | Zhongyi | ME + Africa + S.America + Europe + SEA | 380+ | 14 | limestone, granite, coal, iron ore, C&D waste, river pebble | 高湿/粘料筛分适应性 + 快速转场运营成本 | FTM Machinery / Henan Vest / ZhongCheng Machinery (mode C) | ⚠️ 草稿待审 |
| 2026-05-23 | Diesel Jaw Crusher | Zhongyi | Africa + SEA + S.America + N.America | 450+ | 17 | gold ore, iron ore, limestone, granite, coal, C&D waste | 柴油机品牌选型（Cummins/Perkins/Weichai/Kubota）+ 油耗经济性 / 排放合规（Tier 4 Final / Stage V） | sinolingheng.com, zjzgmachine.com (mode A WebFetch ✅) + McCloskey J40 / Sinomada / Upsen / CAEL (SERP refs) | ⚠️ 草稿待审 |
| 2026-05-23 | Calcination Kiln (v2 重写，上一版作废) | Zhongyi | ME + S.America + Europe + N.America | 280+ | 16 | cement, lime, alumina, petroleum coke, DRI, refractory minerals, lithium concentrate | 5物料×6维度工艺参数横向矩阵 + 产能档位决策树(<300/300-800/800-2000/>2000 t/d) | AGICO / Zoomjo / CEMENTL / Shalimar / Nabertherm / Tianli / YIBU / Elan (mode A SERP ✅) / cement-plants.com / Kintek | ⚠️ 草稿待审（测试稿，已作废） |
| 2026-05-23 | Calcination Kiln (正式) | Zhongyi | SEA + S.Asia + Europe + N.America | 350+ | 15 | cement, lime, alumina, refractory, steel, chemical processing, lithium | 燃料灵活性与能耗经济性 + 耐火材料配置与密封方案 | Hongke (hkrotarykiln), Zoomline, CITICHL, FEECO, AGICO (mode A SERP+WebFetch) | ⚠️ 草稿待审 |
| 2026-05-23 | Vertical Preheater | Zhongyi | SEA + S.Asia + ME + S.America | 350+ | 16 | limestone, dolomite, magnesite, bauxite, lithium concentrate, petcoke, cement raw meal | 热交换效率与燃料节省的量化链路 + 推杆系统选型与维护成本 | ZK Corp, CHAENG, Jiangsu Pengfei, Zhengzhou Hengyang, ANDE Metallurgical (mode A SERP) | ⚠️ 草稿待审 |
| 2026-05-23 | Secondary Combustion Chamber | Zhongyi | Africa + ME + S.America + Europe | 320+ | 17 | gold ore, alumina, lime, cement, copper/lead smelting, petroleum coke, hazardous waste | 矿业专属耐火材料与粉尘处理 + SCC 独立 retrofit 组件 | CIC Heavy Machinery (millkiln.com), FEECO (feeco.com), ZK Corp (zkcomp.com) (mode A WebFetch+search) | ⚠️ 草稿待审 |
