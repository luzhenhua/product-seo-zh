# 用户身份判定与规则调整

本 skill 主要服务两类用户。在阶段 0.5 询问「可选变量 — 用户身份」时识别用户场景，然后按下表调整规则。

---

## 两类用户场景

| 维度 | SEO 服务商代写（默认场景）| 品牌方/厂家自写 |
|------|---|---|
| 用户是谁 | 外贸 SEO 服务商，给客户品牌写英文产品页 | 品牌方自有团队，写自家产品页 |
| 是否有产品手册 | ❌ 无 — 只能用行业 plausible 数据 | ✅ 有 — 可对照真实产品手册 |
| 数据真实性标准 | 行业合理、避免明显造假 | 必须 100% 真实 |
| 引擎/零件/认证品牌 | 行业常见组合可直接写（如 Cummins/Perkins/Weichai/Kubota）| 必须是真实采购的品牌 |
| 经验年数/项目数 | 按 `track_record_log.md` 的 Fabrication Policy 走 plausible 范围 | 必须是真实数字 |
| 认证（ISO9001 / CE / 等） | 出口厂常见默认组合可写 | 必须是真实持有的认证 |

---

## 规则调整对照表

| 模块 / 参考文档 | 默认场景（SEO 服务商）| 厂家自写场景 |
|---|---|---|
| Module 5 Specs 参数 | 行业合理范围，避开 1,000 t/h 小型柴油机这类明显造假 | 必须对照产品手册逐行核对 |
| Module 7 Project Case | 项目地点 + 数据用合理示例 | 必须用真实项目数据 |
| Module 12 Manufacturer 经验年数 | plausible 14–19 年区间 vary | 真实年数 |
| Module 12 认证清单 | ISO9001:2015 + CE 默认（出口厂常见组合）| 真实认证清单 |
| `self-check-report.md` 待核对部分 | "如有手册请核对（可选）"——不强求 | "⚠️ MUST VERIFY against manual"——必须 |
| `final-review-checklist.md` VERIFY 项 | "plausibility check"——查是否明显造假即可 | "must verify"——逐条核对真实 |

---

## 默认行为

- 阶段 0.5 收到「用户身份」变量为空 / 未指定 → **默认按 SEO 服务商场景**（这是本 skill 主要使用群）
- 阶段 0.5 收到「用户身份 = 品牌方」→ 切换厂家自写场景，自检/终审项升级为强 verify
- 阶段 0.5 收到「用户身份 = SEO 服务商」→ 显式确认默认场景
- 自检报告 (`self-check-report.md`) 输出时按场景套用对应文案
- 终审清单 (`final-review-checklist.md`) 同上

---

## Hero UI 容量（独立维度，与用户身份无关）

很多外贸品牌站的 Hero 区是窄列布局，装不下长段落。本 skill 默认按短版本生成，避免内容溢出。

| Hero UI 状态 | Hero 模块 (`modules/01-hero.md`) 行为 |
|---|---|
| 短容量（默认）| H1 + 2 短句（~40–55 字）+ 2–4 bullets + CTA |
| 长容量（用户明确） | H1 + 4 句（~70–105 字，定义→特点→功能→解决方案）+ 4 bullets + CTA |

阶段 0.5 收到「Hero UI 容量」变量为空 → **默认短版本**（多数出口模板站的真实约束）。

---

## 何时应用本规则

- 阶段 0.5 收齐变量后：对照本表确认默认行为
- 生成 Module 5 / Module 12 时：根据用户身份调整数据严谨度
- 生成 `modules/01-hero.md` 时：根据 Hero UI 容量选择短/长版本
- 输出 `self-check-report.md` + `final-review-checklist.md` 时：根据用户身份套用对应文案
