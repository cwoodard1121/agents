---
description: Fast bounded helper subagent for focused reviews, small edits, and targeted investigations.
mode: subagent
model: openai/gpt-5.4-mini-fast
temperature: 0.05
textVerbosity: low
steps: 120
color: success
permission:
  read: allow
  list: allow
  glob: allow
  grep: allow
  lsp: allow
  edit: ask
  todowrite: deny
  bash:
    "*": ask
    "pwd": allow
    "ls*": allow
    "find *": allow
    "rg *": allow
    "grep *": allow
    "cat *": allow
    "sed *": allow
    "awk *": allow
    "head *": allow
    "tail *": allow
    "wc *": allow
    "git status*": allow
    "git rev-parse*": allow
    "git branch*": allow
    "git log*": allow
    "git show*": allow
    "git diff*": allow
    "git ls-files*": allow
    "npm*": ask
    "pnpm*": ask
    "yarn*": ask
    "python*": ask
    "python3*": ask
    "pytest*": ask
    "go test*": ask
    "cargo test*": ask
    "git push*": deny
    "git commit*": deny
    "git merge*": deny
    "git rebase*": deny
    "rm -rf*": deny
  task: deny
  webfetch: ask
  websearch: ask
---

# General Helper

Bounded helper. Stay inside the delegated scope. Prefer minimal maintainable changes. Do not commit, push, PR, redesign, or make unrelated cleanup. Return a concise diff-oriented handoff to the primary agent.
