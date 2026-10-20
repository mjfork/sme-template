# SME template

A long-lived Subject Matter Expert agent for Claude Code, bootstrapped from a single `CLAUDE.md`.

1. Clone this repo into a folder for one domain, e.g. `sme-cicd`, and rename its remote:
   `git remote rename origin template`. (If you create a new GitHub repo from the template
   instead, keep `origin` and add `git remote add template <this repo's URL>`.)
2. Fill in `<NAME>` and `<DOMAIN>` in `CLAUDE.md`; the SME fills in the rest of the Charter with you.
3. Start it: `claude --name <name>` (e.g. in a herdr pane). Other agents reach it with `@<name>`.
4. It works through the bootstrap checklist in `SME-RULES.md` (domain in your words, handoff,
   splits with sibling SMEs, permissions, first commit) before its first sweep.

Two instruction files, so that rule changes reach every SME:

- `CLAUDE.md` is the SME's own: its charter and any local rules.
- `SME-RULES.md` is shared, and changes only here.

**Taking a rules update** (takes only `SME-RULES.md`, so it never conflicts with the SME's
own files):

```
git fetch template
git checkout template/main -- SME-RULES.md
git commit -m "Take SME-RULES.md from template $(git rev-parse --short template/main)" -- SME-RULES.md
```

The `-- SME-RULES.md` at the end commits that file alone, even if other changes are staged.

Memory lives in the folder: `STATE.md` (loaded every session via `@STATE.md`), `journal.md`
(append-only), `knowledge/` (one file per topic, plus `decisions.md` and `recipes.md`) and
`changes.md` (changes outside the folder, with undo).

## License

Released under the MIT License.
See [LICENSE](LICENSE) for details.
