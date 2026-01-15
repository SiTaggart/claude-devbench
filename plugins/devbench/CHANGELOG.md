# Changelog

All notable changes to the devbench plugin will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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


