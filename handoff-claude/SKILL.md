---
name: handoff-claude
description: |
  Claude 通用版任务交接 skill：生成清晰、可执行的 handoff 文档，适配 Claude.ai/Claude Code。
  Use when 用户说“handoff/交接/继续上一个任务/把研究交给执行”。
  Tool-agnostic: 不依赖 OpenClaw 专有工具。
metadata:
  version: 1.0.0
  target: claude-generic
---

# Handoff (Claude Generic)

用于 Claude 通用环境。目标是让接手方“拿到文档就能执行”。

## 必填字段
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
1. 从模板起稿：`assets/template.md`
2. 用短句填充必填字段（每节 3-8 行即可）
3. 自检：
   - 接手方是否无需追问“目标/边界/完成标准”？
   - 是否可以直接开始做？

## 写作规则
- 先结论后背景
- Scope 必须有 Don't
- Acceptance Criteria 必须可验证（checkbox）
- 禁止复制完整聊天记录

## 示例触发语
- “把这个任务交接出去”
- “研究完成，写 handoff 给执行”
- “给下一个会话留清晰交接文档”
