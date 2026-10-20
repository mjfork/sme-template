# SME template

A long-lived Subject Matter Expert agent for Claude Code, bootstrapped from a single `CLAUDE.md`.

1. Create a repo from this template (or copy the folder) for one domain, e.g. `sme-cicd`.
2. Fill in the `<NAME>`, `<DOMAIN>` and charter placeholders in `CLAUDE.md`.
3. Start it: `claude --name <name>` (e.g. in a herdr pane). Other agents reach it with `@<name>`.
4. Tell it to sweep, so it seeds `STATE.md` and `knowledge/` from the real sources of truth.

Memory lives in this folder: `STATE.md` (loaded every session via `@STATE.md`, so it survives
compaction), `knowledge/` (one file per topic, with last-verified date and evidence), and
`journal.md` (append-only log).

## License

Released under the MIT License.
See [LICENSE](LICENSE) for details.
