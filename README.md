# htmldoc skill

A [skills.sh](https://skills.sh) skill for Claude Code and other agents that
publish files to disk. It lets you say "share this doc", "share this plan
online", or "publish this with htmldoc" and get back an unlisted share link
that lives 30 days and can be updated in place. It works by driving the
[`htmldoc-cli`](https://www.npmjs.com/package/htmldoc-cli) command-line tool —
the skill never talks to the API directly and never sees or handles your API
key.

## Install

```sh
npx skills add ajaxray/htmldoc-cli
```

(Replace `ajaxray/htmldoc-cli` with this skill's published repository.)

## One-time setup

Before the skill can upload anything, you need an API key:

1. Visit [htmldoc.space](https://htmldoc.space) and sign in with GitHub.
2. Copy the API key shown on your dashboard.
3. In a terminal, run:

   ```sh
   npm i -g htmldoc-cli
   htmldoc login
   ```

   and paste the key when prompted. (Skipping the global install also works:
   the agent falls back to `npx -y htmldoc-cli`, which is slower on first run.) This step must be run by you, in your own
   terminal — the agent will never ask for or handle the key.

After that, just ask your agent to share a file.

## Local development

Outside this monorepo, the skill needs the published `htmldoc-cli` npm
package: either installed globally (`htmldoc` on PATH) or resolvable via
`npx -y htmldoc-cli`. While developing against
an unpublished CLI, link it locally instead:

```sh
cd cli && npm link
npm link htmldoc-cli   # from the repo root, or wherever npx will resolve from
```

## Learn more

[htmldoc.space](https://htmldoc.space)
