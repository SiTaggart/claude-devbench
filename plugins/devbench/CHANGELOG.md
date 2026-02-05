# Changelog

All notable changes to the devbench plugin will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.0] - 2026-02-05

### Added

- **`orchestrating-swarms` skill** - Comprehensive guide to multi-agent swarm orchestration using Claude Code's TeammateTool and Task system. Covers primitives, 13 TeammateTool operations, 6 orchestration patterns (Parallel Specialists, Pipeline, Self-Organizing Swarm, Research + Implementation, Plan Approval, Coordinated Multi-File Refactoring), spawn backends (in-process, tmux, iterm2), error handling, and complete workflow examples. Ported from compound-engineering plugin v2.30.0.

### Changed

- **`/workflows:work` command** - Cherry-picked improvements from compound-engineering:
  - Smart branch detection: detects current branch vs default branch, offers appropriate choices
  - Incremental commits: commit after each logical unit with heuristic table for when to commit
  - Plan checkbox tracking: marks `[ ]` -> `[x]` in plan file as tasks complete
  - Generic test commands: replaced hardcoded `bin/rails test` with project-agnostic examples
  - Phase 4 (Ship It): added PR creation workflow with `gh` CLI
  - Swarm Mode section: optional parallel execution with TeammateTool for complex plans

---

## [1.1.4] - 2026-01-26

### Added

- **Main branch protection hook** - PreToolUse hook that prevents Claude from committing directly to `main` or `master` branches. Blocks `git commit`, `git merge`, `git rebase`, and `git cherry-pick` operations with guidance to create a feature branch first.

## [1.1.3] - 2026-01-22

### Fixed

- **Plan file paths** - Updated `/plan` and `/deepen-plan` commands to use `.ai` directory consistently for storing plan output files.

## [1.1.2] - 2026-01-21

### Added

- **skills-sh-marketplace skill** - Search, discover, and install skills from [skills.sh](https://skills.sh) (Vercel's open agent skills ecosystem). Supports browsing the leaderboard, filtering by name/author, listing repository contents, and installing skills to Claude Code and other agents using `bunx skills` commands.

## [1.1.1] - 2026-01-15

### Changed

- **Human-in-the-loop for agent output** - Commands no longer auto-commit or push changes, letting you review agent work before committing:
  - `resolve_parallel` - Removed "Commit & Resolve" section
  - `resolve_pr_parallel` - Removed commit, push, and thread resolution steps
  - `resolve_todo_parallel` - Removed commit and push steps
  - `review` - Removed git commit instruction from track progress section
  - `triage` - Removed "commit the todos" option from completion menu
  - `file-todos` skill - Removed auto-commit step from completion workflow
  - `create-agent-skills` iteration guide - Removed "Commit change" from fast iteration workflow

### Removed

- iOS/Xcode testing paths from `/review` command - Simplified to focus on web/Playwright tests only

## [1.1.0] - 2026-01-15

### Added

- **RepoPrompt Integration Commands** - 4 new CLI commands for RepoPrompt workflows:
  - `/rp-build-cli` - Build workflow with context builder
  - `/rp-investigate-cli` - Deep bug investigation
  - `/rp-oracle-export-cli` - Export to oracle format
  - `/rp-reminder-cli` - Context reminders
- **Agent Browser Skill** - New skill for browser automation in agent workflows

### Removed

- `dhh-rails-reviewer` agent - Rails-specific tooling removed for framework-agnostic focus
- `dhh-rails-style` skill - Rails-specific tooling removed
- `dhh-ruby-style` skill - Ruby-specific tooling removed

### Changed

- Streamlined `compound-docs`, `review`, and `plan_review` commands
- Plugin is now more framework-agnostic (removed 3,669 lines of Rails/Ruby-specific code)

## [1.0.2] - 2026-01-09

### Changed

- Rewrote `create-agent-skills` skill to follow Anthropic's official spec
- Use standard markdown headings instead of XML tags
- Renamed skill to gerund form (`creating-agent-skills`)
- Added `official-spec.md` and `best-practices.md` reference docs
- Removed deprecated `use-xml-tags.md` reference

## [1.0.0] - 2026-01-01

### Added

- Initial release of Devbench plugin, forked from compound-engineering v2.19.0
- React/TypeScript focused development tools
- 27 specialized agents for code review, research, design, and documentation
- 20 commands for workflow automation
- 13 skills for development assistance
- 2 MCP servers (Playwright, Context7)

### Changed

- Rebranded from "compound-engineering" to "devbench"
- Updated keywords to focus on React/TypeScript (removed Rails/Ruby specific tags)
- Updated repository URLs to SiTaggart/claude-devbench

---

**Note:** This plugin was forked from [compound-engineering v2.19.0](https://github.com/EveryInc/compound-engineering-plugin) which had 2+ years of active development and 27+ releases.


