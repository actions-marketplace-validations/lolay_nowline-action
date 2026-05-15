# lolay/nowline-action

[![Marketplace](https://img.shields.io/badge/marketplace-coming%20soon-lightgrey)](https://github.com/marketplace)

> **This repository is a publish-target mirror.** It exists so the
> [GitHub Actions Marketplace](https://github.com/marketplace) can find
> an `action.yml` at the repo root. Source code, issues, and pull
> requests all live in the [`lolay/nowline`](https://github.com/lolay/nowline)
> monorepo.

## What this action does

`@nowline/action` renders [Nowline](https://github.com/lolay/nowline)
roadmap diagrams in CI. Two modes:

- **File mode** — render a single `.nowline` file to SVG or PNG.
- **Markdown mode** — scan markdown files for ` ```nowline ` fenced
  code blocks, render each one, and insert / refresh an image
  reference adjacent to the block.

The action is the answer for hosts that strip `<script>` tags
(GitHub READMEs, GitHub issues, GitHub PRs, email, Slack, Discord,
Confluence rich text). For pages that *can* run scripts, see the
[browser embed](https://github.com/lolay/nowline/tree/main/packages/embed)
instead.

## Status

This action is **bootstrapping**. The first release will populate
`action.yml`, `dist/index.js`, and the full README + license from
the monorepo on every tag push. Until then, this repo only carries
the placeholder files you see here.

For the latest documentation and source code, see
[`packages/nowline-action/` in the monorepo](https://github.com/lolay/nowline/tree/main/packages/nowline-action).

## Where to file things

| What | Where |
|---|---|
| Bug reports, feature requests | [`lolay/nowline` issues](https://github.com/lolay/nowline/issues) |
| Pull requests | [`lolay/nowline` pulls](https://github.com/lolay/nowline/pulls) — change `packages/nowline-action/` |
| Security disclosures | `security@nowline.io` (see [`SECURITY.md`](https://github.com/lolay/nowline/blob/main/SECURITY.md)) |
| Marketplace listing | This repo's tagged releases |

## How the mirror works

On each release in the monorepo, `lolay/nowline`'s
`.github/workflows/release.yml` runs a mirror cell that pushes the
compiled action artifacts here:

- `action.yml` — copied from `packages/nowline-action/action.yml`
- `dist/index.js` — esbuild-bundled action entry
- `README.md` — replaced with the user-facing README from
  `packages/nowline-action/README.md`
- `LICENSE` — replaced with the monorepo's Apache-2.0 LICENSE
- Tags `vX.Y.Z` (immutable) and `vX` (moving major-tag pointer)

Same pattern as the [`lolay/homebrew-tap`](https://github.com/lolay/homebrew-tap)
publish-target mirror.

## License

Apache-2.0. See [`LICENSE`](./LICENSE).
