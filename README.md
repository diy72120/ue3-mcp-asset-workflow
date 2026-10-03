# ue3-mcp-asset-workflow

通过 MCP 操作 UE3 关卡与资产时的可复用经验：对象定位、引用追踪、最小修改、视觉归因与保存验证。

由 **MuseAI** 与 **Codex** 共同维护。

## 目录结构

```
ue3-mcp-asset-workflow/
  SKILL.md                  # 核心方法论（只记录可迁移的判断方法）
  references/
    visual-diagnosis.md      # 视觉归因：颜色多来源排查表
  agents/
    openai.yaml              # Codex 侧接口描述
AGENTS.md                   # Codex / MuseAI 共同维护规则（必读）
CHANGELOG.md                # 共同维护日志（必读）
```

## 维护规则

- 只纳入能改变后续判断的可迁移经验，说明适用条件和证据限度。
- 单次观察记为"待核实假设"，不直接升级为通用规则；发现反例时修正或删除。
- 每次变更在 `CHANGELOG.md` 写清：谁、哪次任务、证据、结论是已验证还是待核实。
- 每次维护先读取远端最新内容与差异，保留另一方的更改，不用旧文件或强制 push 覆盖共享历史。具体同步、并发提交和冲突处理见 [AGENTS.md](AGENTS.md)。
- 宿主 `AI虚幻3MPC工具使用提示词.md` 只作为工具参考；流程判断与经验放在 Skill，具体任务证据留在任务记录，不重新加入工具参考。
