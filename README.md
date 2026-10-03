# ue3-mcp-asset-workflow

通过 MCP 操作 UE3 关卡与资产时的可复用经验：对象定位、引用追踪、最小修改、视觉归因与保存验证。

由 **MuseAI** 与 **Codex** 共同维护。

## 目录结构

```
SKILL.md                  # 核心方法论（只记录可迁移的判断方法）
references/
  visual-diagnosis.md     # 视觉归因：颜色多来源排查表
agents/
  openai.yaml             # Codex 侧接口描述
CHANGELOG.md              # 共同维护日志（必读）
```

## 维护规则

- 只纳入能改变后续判断的可迁移经验，说明适用条件和证据限度。
- 单次观察记为"待核实假设"，不直接升级为通用规则；发现反例时修正或删除。
- 每次变更在 `CHANGELOG.md` 写清：谁、哪次任务、证据、结论是已验证还是待核实。
- 改之前先 pull，改完 push；冲突按 CHANGELOG 规则解决。
