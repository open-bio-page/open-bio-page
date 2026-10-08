# Contributing

Open Bio Page is a Vue site plus a small admin API. Source changes are welcome. Bios, photos, and brand files in a published instance are not part of the MIT grant. See [LICENSE.md](LICENSE.md).

## Run locally

Requirements: [Bun](https://bun.sh/) 1.3.14 (`packageManager` in `package.json`).

```sh
bun install
cp .env.example .env.local
cp worker/.dev.vars.example worker/.dev.vars
cp secrets.local.example secrets.local
bun dev
```

`bun dev` serves the site on port 5173 and the admin API on port 8787.

Docs:

```sh
bun run docs:dev
```

VitePress is at `http://127.0.0.1:5174/`. That command builds the example sites first.

Checks that CI runs (`.github/workflows/ci.yml`):

```sh
bun run type-check
bun lint
bun run build
bun run docs:build
```

`bun run format` runs oxfmt on `src/`. It is not part of CI.

Do not commit `.env.local`, `worker/.dev.vars`, `secrets.local`, or `node_modules`.

## Propose a change

1. Fork the repository and branch from an up-to-date `master`.
2. Keep the change to one topic.
3. Open a pull request against `master` with a short description of what changed.

There is no issue template. A pull request can stand on its own for a small fix. For a larger change, open an issue first so the approach is agreed.

## Code style

The app is Vue single-file components, TypeScript, Pug templates, and SCSS, styled with Tailwind CSS 4.

- `bun run type-check` runs `vue-tsc --build`.
- `bun lint` runs oxlint, then ESLint. oxlint uses `.oxlintrc.json` (correctness as error, plus the eslint, typescript, unicorn, oxc, and vue plugins). ESLint uses `eslint.config.ts`: Vue `flat/essential`, `@vue/eslint-config-typescript` recommended, the Pug template tokenizer, oxlint's overlapping rules turned off, and Prettier-style formatting skipped so oxfmt owns formatting.
- `bun run format` formats `src/` with oxfmt.

Match the surrounding file. Do not reformat unrelated code.

## Report an issue

Use [GitHub issues](https://github.com/open-bio-page/open-bio-page/issues).

Include:

- what you expected and what happened
- the page or command
- the Bun version (`bun --version`)

Do not paste secrets, admin password hashes, or the contents of `.env.local`, `worker/.dev.vars`, or `secrets.local`.
