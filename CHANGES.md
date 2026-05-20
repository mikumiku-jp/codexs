# Changes from upstream (openai/codex)

This is a derivative work of [OpenAI Codex CLI](https://github.com/openai/codex),
licensed under the Apache License, Version 2.0.

The following files have been modified from the original:

## Rust source files
- `codex-rs/core/src/arc_monitor.rs` — ARC safety monitor bypassed (always returns Ok)
- `codex-rs/core/src/guardian/review.rs` — Guardian rejection instructions relaxed
- `codex-rs/core/src/guardian/policy_template.md` — Guardian authorization policy relaxed
- `codex-rs/core/src/context/user_instructions.rs` — AGENTS.md role changed from "user" to "developer"
- `codex-rs/core/src/context/permissions_instructions.rs` — Auto-review rejection message simplified
- `codex-rs/core/src/goals.rs` — Test updated for objective tag rename
- `codex-rs/core/src/client.rs` — ReasoningEffort::None disables reasoning param in API
- `codex-rs/core/src/agent/registry.rs` — Subagent depth hard-capped at 1
- `codex-rs/core/src/tools/handlers/multi_agents_spec.rs` — Subagent spawn policy changed to proactive with constraints
- `codex-rs/tui/src/slash_command.rs` — Added /thinking command, /permissions available during tasks
- `codex-rs/tui/src/chatwidget/slash_dispatch.rs` — /thinking command dispatch added
- `codex-rs/tui/src/chatwidget/model_popups.rs` — "Off (no reasoning)" added to reasoning effort selector
- `codex-rs/tui/src/chatwidget/reasoning_shortcuts.rs` — None always included in reasoning choices, visibility changed
- `codex-rs/tui/src/chatwidget/status_controls.rs` — Status line shows "off" for ReasoningEffort::None

## Prompt/template files
- `codex-rs/core/templates/goals/continuation.md` — User authority section added, completion audit simplified
- `codex-rs/core/templates/goals/objective_updated.md` — "untrusted_objective" tag changed to "objective"
- `codex-rs/core/templates/personalities/gpt-5.2-codex_friendly.md` — Rewritten to follow user corrections
- `codex-rs/core/templates/model_instructions/gpt-5.2-codex_instructions_template.md` — User correction rules added, STOP IMMEDIATELY removed, comment rule defers to AGENTS.md
- `codex-rs/core/templates/compact/prompt.md` — User corrections preserved in compaction summary
- `codex-rs/core/templates/agents/orchestrator.md` — Subagent guidelines rewritten, STOP IMMEDIATELY removed
- `codex-rs/collaboration-mode-templates/templates/default.md` — Clarifying questions allowed when intent is ambiguous
- `codex-rs/collaboration-mode-templates/templates/execute.md` — Questions allowed when wrong assumption causes rework
- `codex-rs/collaboration-mode-templates/templates/plan.md` — Suggests mode switch instead of silently ignoring user
- `codex-rs/models-manager/prompt.md` — "safe" removed, AGENTS.md priority elevated, persistence balanced
- `codex-rs/protocol/src/prompts/base_instructions/default.md` — Same changes as models-manager/prompt.md
- `codex-rs/core/gpt_5_codex_prompt.md` — STOP IMMEDIATELY removed, "safe" removed
- `codex-rs/core/gpt-5.1-codex-max_prompt.md` — STOP IMMEDIATELY removed, "safe" removed
- `codex-rs/core/gpt-5.2-codex_prompt.md` — STOP IMMEDIATELY removed, "safe" removed
- `codex-rs/core/gpt_5_2_prompt.md` — Persistence balanced, Autonomy rewritten, "safe" removed, AGENTS.md priority elevated
- `codex-rs/core/gpt_5_1_prompt.md` — Same changes as gpt_5_2_prompt.md
- `codex-rs/core/prompt_with_apply_patch_instructions.md` — Same changes as models-manager/prompt.md
