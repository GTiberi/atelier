# Project agent memory

This file is the project's committed home for project-intrinsic agent knowledge: build, test, release, architecture, and sharp-edge notes that should travel with the code.

- atelier is a private, personal Agent Skills library: one `<name>/SKILL.md` folder per skill at the repository root, catalogued in `README.md` (which also says how a skill is added and validated).
- Skills only. Nothing derived from employer or client work, nothing personal, no secrets, no absolute or home-directory paths. Scan the tree before committing (gitleaks, or grep for token prefixes such as `gho_`, `ghp_`, `AKIA`, and for absolute paths).
- There is no test suite. Validate with `gh skill publish --dry-run` (frontmatter, name equals folder) and a scratch-directory `npx skills add <path-to-repo> --skill=<name>`.
- Installer sharp edge (skills CLI 1.7.0): repeating `--skill=a --skill=b` installs the whole repository. Document one `--skill=<name>`, or the space-separated `--skill a b`.
- `hot-seat/references/NOTICE.md` carries the upstream MIT notice (mattpocock/skills) and must stay with the skill.

## Maintaining this file

Keep this file for knowledge useful to almost every future agent session in this project.
Do not repeat what the codebase already shows; point to the authoritative file or command instead.
Prefer rewriting or pruning existing entries over appending new ones.
When updating this file, preserve this bar for all agents and keep entries concise.
