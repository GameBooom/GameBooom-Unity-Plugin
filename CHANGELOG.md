# Changelog

## 0.0.9
- Initial commercial DLL distribution package template.


## 0.1.0
- Release prepared in editor.


## 0.1.1
- Release prepared in editor.


## 0.1.2
- Release prepared in editor.


## 0.1.3
- Release prepared in editor.


## 0.1.4

### Added
- Added MCP resources, resource templates, and prompts so Codex and other MCP clients can discover more useful Unity context.
- Added cached attachment snapshots for image and text files to keep chat/session recovery independent from the original file paths.
- Added higher-level Unity workflow helpers, including smarter reference auto-wiring and built-in runtime validation templates for common prototype checks.

### Improved
- Improved custom API compatibility for OpenAI Responses-based providers such as PackyAPI while preserving tool calling in compatible flows.
- Improved AI workflow quality for Unity prototyping, including stronger orchestration around scene setup, validation, and repeated write-action handling.
- Improved release packaging consistency with unified package versioning and versioned commercial DLL output naming.

### Fixed
- Fixed repeated write-operation loops from some models by blocking duplicate write actions and surfacing follow-up inspection suggestions.
- Fixed scene safety gaps by saving the current scene before creating new scenes and before entering Play Mode.
- Fixed MCP main-thread access issues by moving Unity state sampling to cached main-thread snapshots and enabling keep-alive only while requests are active.
