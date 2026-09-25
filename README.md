# atelier

A personal library of [Agent Skills](https://agentskills.io/specification): one folder per skill, each with a `SKILL.md`, working in Claude Code, GitHub Copilot CLI and the other agents the `skills` installer supports.

The repository is private for now. Installing from it works wherever `git clone` of it works (a signed-in `gh` or an SSH key).

## Catalogue

### hot-seat

The [grill-me](https://www.aihero.dev/skills-grill-me) interview with a UI. Every round of questions is a [Lavish](https://github.com/kunchenguid/lavish-axi) page with a recommended answer on each card, a live design tree and a decisions ledger. Started inside a codebase it also does the [grill-with-docs](https://www.aihero.dev/skills-grill-with-docs) paper trail (`CONTEXT.md`, ADRs).

```sh
npx skills add GTiberi/atelier --skill=hot-seat
```

| | |
|---|---|
| Use | `/hot-seat <what to grill>` |
| Needs | Node 18+ and `lavish-axi` on PATH (`npm i -g lavish-axi`). Without Lavish the skill says so and runs the same interview in chat. |
| Upstream | `grilling` and `domain-modeling` from [mattpocock/skills](https://github.com/mattpocock/skills) are the source of its rules. hot-seat carries them inline and does not load them, so installing them is optional: `npx skills add mattpocock/skills --skill grilling domain-modeling` |
| Docs | [hot-seat/README.md](hot-seat/README.md) (install scopes, what is in the folder) and [hot-seat/SKILL.md](hot-seat/SKILL.md) (the contract and run-book) |

## Adding a skill

1. Create `<name>/SKILL.md` at the repository root. The folder name is the skill name (lowercase, hyphens) and must equal `name` in the frontmatter; `description` is required and at most 1024 characters. Put helpers in `scripts/`, `references/` and `assets/` inside the folder.
2. Validate from the repository root: `gh skill publish --dry-run` checks names and frontmatter, and `npx skills add . --list` must show the skill. Then install it into a scratch project with `npx skills add /path/to/atelier --skill=<name>` and try it there.
3. Add a catalogue entry above: purpose, install line, what it needs. Link to the skill's own docs instead of repeating them.
4. Keep the repository to skills only: no secrets, no absolute paths, nothing derived from client or employer work, nothing personal.
5. Open a pull request against `master`.

## Licence

[MIT](LICENSE). hot-seat derives from mattpocock/skills (also MIT); its notice is in [hot-seat/references/NOTICE.md](hot-seat/references/NOTICE.md).
