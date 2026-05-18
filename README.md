# claude.md
My personal CLAUDE.md for Claude Code that combines the best of Andrej Karpathy's LLM coding guidelines with targeted integration of the Superpowers skill plugin, tuned for solo developers working on existing codebases like me :D

What it does
Loads automatically into every Claude Code session and shapes how Claude behaves across five rules:

## Section	Rule	What it prevents
0. Phase Awareness
   Exploration mode vs implementation mode, Claude discusses and analyzes only until you explicitly say to act. It prevents Claude making code changes during what you intended as a brainstorming conversation
1. Think Before Coding
   Surface assumptions, present tradeoffs, ask when unclear. It prevents silent wrong assumptions that require rewrites
2. Simplicity First
   Minimum code that solves the problem, nothing speculative. It prevents overengineered abstractions, features you didn't ask for
3. Surgical Changes
   Touch only what the request requires, match existing style. It prevents driveby refactoring, formatting changes, unrelated "improvements" in diffs
4. Goal-Driven Execution
   Define verifiable success criteria before implementing. It prevents vague "make it work" goals that require constant clarification
5. Skill Integration
    Autofires two Superpowers skills at the right moments. It prevents guessed fixes without root cause, completion claims without evidence
   
Section 5 automatically invokes:
superpowers:systematic-debugging — triggered on any bug, test failure, or unexpected behavior. No fix is proposed until root cause is established.
superpowers:verification-before-completion — triggered before any claim of "done", "fixed", or "passing". Requires running the actual verification command and showing output.

## Who it's for
Solo developers or small teams who:
- Work on existing codebases (not greenfield)
- Want Claude to discuss first and act second
- Have been burned by Claude touching code it shouldn't have
- Want rigorous bug investigation and honest completion claims without installing the full Superpowers ceremony

## Installation
Copy CLAUDE.md to ~/.claude/CLAUDE.md to apply globally across all projects, or copy into a specific project directory only. If you use the Superpowers plugin, Section 5 will autotrigger the two relevant skills. If you don't have Superpowers installed, Section 5 has no effect, the rest of the guidelines still apply independently.

## Works with
Claude Code (CLI and desktop)
Superpowers plugin (optional, enhances Section 5)
andrej-karpathy-skills (this file supersedes it, no need to install both)

## Design decisions
Why not invoke /karpathy-guidelines at session start? The plugin's CLAUDE.md auto-loads every session, so manual invocation is redundant. This file is the permanent version of that content, it survives plugin updates which would otherwise overwrite the plugin's own copy.

Why not use /using-superpowers? The full Superpowers protocol (9-step brainstorming, design docs, TDD cycles, git worktrees) is built for team workflows. For solo development on existing codebases it adds ceremony without benefit. This file takes only the two skills with universal value and wires them in directly.

Why Sections 2 and 3 specifically? These are the only rules in Karpathy's guidelines that Superpowers does not cover at all. Every other concern, explore before implement, planning and verification has a Superpowers skill. Simplicity and surgical changes are uniquely Karpathy territory.

See, if you made it this far in reading this readme, kudos to you! Basically I just love being efficient and want a backup for my framework lmao
