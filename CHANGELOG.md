# 变更日志（MuseAI 与 Codex 共同维护）

规则：每条记录写明**谁**在**哪次任务**中发现、**证据**是什么、结论是"已验证"还是"待核实假设"。单次观察不直接升级为通用规则，发现反例时修正适用范围或删除。

---

## 2026-10-03 — 初始版本（Codex 创建）

- 来源：2026-10-02 石门（Login_n）蓝火/红门改色任务的成功经验。
- 内容：SKILL.md（对象定位、引用追踪、最小修改、视觉归因、保存验证的方法论）+ references/visual-diagnosis.md（颜色多来源归因表）+ agents/openai.yaml。
- 原则：只记录可迁移的判断方法，不记录某张地图的操作脚本、对象编号、颜色配方或坐标。

## 2026-10-03 — MuseAI 审阅

- 审阅了 SKILL.md、visual-diagnosis.md、openai.yaml 全文。
- 评价（已验证）：方法论与"四种完成证据"（请求/数据/表现/持久化）、"现象/下一步/不足以证明"三列表格可直接采用；"单次观察不升级为规则"的维护规范正确。
- 保留意见（待讨论）：Skill 刻意不记具体数值；但绑定特定部署的工具提示词（如 `AI虚幻3MPC工具使用提示词.md`）中记录经核实的案例参考值是有用的，前提是明确标注案例来源与校正状态，不写成通用定律。两者分层共存，不冲突。

## 2026-10-03 — 同步修正 `.md` 提示词（MuseAI）

起因：Codex 审阅发现 MuseAI 在 `AI虚幻3MPC工具使用提示词.md` 新增经验段落中有四处会把后续 AI 带偏的错误，已按 Codex 纠正重写：
1. 粒子资源认错：`fx_lg`/`fx_lg02` 不是目标；实际是两侧火焰 `P_Ex_01_Small`（Emitter_13/10，5 处 ColorOverLife 曲线）与中央光柱 `P_Gatefx`（Emitter_6，`DistributionVectorConstant.Constant=(X=3,Y=0,Z=0)`）。
2. 归因方法武断："关灯还亮=材质问题"不成立，改为"关灯只排除该灯"。
3. `set_material` 结论降级：Codex 成功调蓝柱子未调用 set_material；M_liubian 观察标为 MuseAI 单方待核实。
4. `Brightness=0.01` 不通用化；补充"只筛 PointLight 会漏动态灯/自定义子类（如 MMOTorchLight）"陷阱。
- 保留的有用部分：参数名纠正（`component_path`、`source_path`/`target_package`/`target_name`）、复制材质可能触发 Bridge 断连（先 `ue3.health`）、粒子与照明分开修改。
