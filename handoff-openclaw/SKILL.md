---
name: handoff-openclaw
description: |
  OpenClaw 专用的任务交接 skill：生成标准化 handoff 文档并交给 sub-agent 或发送到指定 topic。
  Use when 用户说“handoff/交接/传给 codex/让 sonnet 做/拆分任务/spawn 执行”。
  Includes OpenClaw actions: sessions_spawn, message(send), topic 发送。
metadata:
  version: 1.0.0
  target: openclaw
---

# Handoff (OpenClaw)

用于 OpenClaw 场景：主 agent 明确方向后，产出 handoff 文档并派发执行。

## 必填字段（文档内）
- Task
- Context
- Scope (Do / Don't)
- Acceptance Criteria
- Resources

## 按需字段
- Research Summary
- Plan
- Constraints
- Priority / Deadline
- Notes

## 步骤
1. 复制模板：`assets/template.md`
2. 保存到：`~/clawd/handoffs/handoff-<task>-<YYYYMMDD-HHMM>.md`
3. 派发（二选一）：
   - 给 sub-agent：`sessions_spawn(..., attachments=[handoff.md])`
   - 发到 topic：`message(action="send", target="<topic_id>", filePath="<handoff_path>")`

## OpenClaw 派发模板

### A) Spawn 执行
```json
{
  "task": "按附件 handoff.md 执行",
  "runtime": "subagent",
  "mode": "run",
  "attachments": [{"name":"handoff.md","content":"..."}]
}
```

### B) 发到 Telegram topic
```json
{
  "action": "send",
  "channel": "telegram",
  "target": "<topic_id>",
  "filePath": "<handoff_path>",
  "message": "handoff attached"
}
```

## 质量门槛
- 不写长对话历史
- 不写模糊词（尽量/应该/可以考虑）
- Acceptance Criteria 必须可验收（checkbox）
