# Vibecoding

Speed, no strict guidelines, technical debt -> AI goes crazy.

A master prompt - write everything about what the project does. It is like background info.

Write the spec before prompting. Give AI context. Test before implementing.
Review code changes. Build tools that enforce good habits, linters.

IDE copilot:
- Autocomplete
- Generate snippets

Chat agents

Repo/task agents (agentic coding tools)

# Copilot AI:

nice, free for students, works good, multiple providers

# Claude Code

can use CLI

# Lovable

Good for web page building, everything is preinstalled, batteries included, just ask AI what you want and it builds and deploys.

# OpenClaw

it can configure, trigger workloads, do things, most popular on GitHub.

Security is issue, prompt injections.

# For companies

Suggest for customer easily how things can be done.

# Agent comparison

# Vibecoding is like steering

Inputs -> Process -> Output
/\                     \/
** <------------------ **

# 10 habits to improve AI coding
1. Give AI context before your prompt
`AGENTS.md` - read by codex
`CLAUDE.md` - read by claude

2. Always plan first
Small steps work the best.
Skeleton first, sketching how things flow, connect

3. Tests are important, edge cases, test driven development

4. Build gradually
Start at core add complexity later

Thin vertical sclices

5. Identify -> Understand -> Document -> Fix

Sometimes ai tries to fix stuff without understanding the problem.

Document how to fix these bugs later.

When you find a bug, you not only fix it but also create a test.

6. Security critical code

Misses ownership cases
Accidental leakage 

7. When to stop asking the AI
Three failed attempts -> Restart, you have missing context, or the task is outside AI reliability zone.

8. Tooling matters
Reusable prompts, bash scripts, skills, repeatable workflows.
Its worth to build a skill and then write in `AGENTS.md` how to use it, its easier.

9. Pick the right model for your job

Not all models are created equal, some are for planning, some for code.
Use different model from one that wrote the code to review code.

10. Iterate
AI without feedback drifts. Target one minute cycles, not one hour

# Future trends of vibecoding

Using ai created training data
AI orchestration
