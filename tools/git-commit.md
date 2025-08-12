---
description: Create well-formatted git commits with conventional commit messages and emoji
category: version-control-git
allowed-tools: Bash, Read, Glob
---

# Claude Command: Commit

This command helps you create well-formatted commits with conventional commit messages and emojis.

## Usage

To create a commit, simply enter:
```
/tools:git-commit
```

## Command Features

1. Use `git status` to check staged files
2. If 0 files are staged, stop execution, ask whether to stage all unstaged files, and proceed based on the response
4. View changes in the staging area
5. Analyze diffs to determine if there are multiple distinct logical changes
6. If multiple distinct changes are detected, suggest splitting the commit into smaller commits
7. Create commit messages using conventional commit format for each commit (or a single commit if not split)
8. Ask the user for the `JIRA-ID` to fill in, directly inserting it based on user feedback $ARGUMENTS

## Commit Best Practices

- **Atomic Commits**: Each commit should contain related changes serving a single purpose
- **Split Large Changes**: If changes involve multiple concerns, split them into separate commits
- **Conventional Commit Format**: Use the format `<type>(<module>): <summary>`, where the type is one of the following:
  - `feat`: New feature
  - `fix`: Bug fix
  - `docs`: Documentation changes
  - `style`: Code style changes (formatting, etc.)
  - `refactor`: Code changes that neither fix bugs nor add features
  - `perf`: Performance improvements
  - `test`: Adding or fixing tests
  - `chore`: Changes to build processes, tools, etc.
- **Present Tense, Imperative Mood**: Write commit messages as commands (e.g., "Add feature" instead of "Added feature")

## Format Specifications

1. **First Line**: Type(module) + summary
   - **Strictly follow conventional commit format**: `<type>(<module>): <summary>`
   - `module` is set based on diff
   - **Concise summary**: Strictly limit each line to < 50 characters, allowing line breaks
   - Example: `fix(bl616): correct irq vector index calculation`

2. **Second Line**: Empty line

3. **Third Line**: JIRA-ID
   - Format: `PROJECTKEY-XXX` (all uppercase)
   - If not provided by the user, replace with an empty line

4. **Fourth Line**: Empty line

3. **Fifth Line**: Technical details description
   - Description must include:
     - Root cause
     - Solution
     - Impact
   - Multiple pieces of information can be listed as 1, 2, 3...
   - Strictly limit each line to < 50 characters, allowing line breaks
