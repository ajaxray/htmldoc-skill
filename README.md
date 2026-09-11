# htmldoc skill

A [skills.sh](https://skills.sh) skill for Claude, Codex, Pi, or
[any AI agent that supports skills](https://www.skills.sh/agent). It lets you say "share this doc", "share this plan
online", or "publish this with htmldoc" and get back an unlisted share link
that lives 30 days and can be updated in place. It works by driving the
[`htmldoc-cli`](https://www.npmjs.com/package/htmldoc-cli) command-line tool —
the skill never talks to the API directly and never sees or handles your API
key.

![Claude Code answering "share the report.html" with a link](https://raw.githubusercontent.com/ajaxray/htmldoc-cli/main/docs/agent.gif)

## Install

```sh
npx skills add ajaxray/htmldoc-skill
```

Source: [ajaxray/htmldoc-skill](https://github.com/ajaxray/htmldoc-skill). The
CLI it drives: [ajaxray/htmldoc-cli](https://github.com/ajaxray/htmldoc-cli),
published on npm as [`htmldoc-cli`](https://www.npmjs.com/package/htmldoc-cli).

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

The skill needs the `htmldoc-cli` npm package: either installed globally
(`htmldoc` on PATH) or resolvable via `npx -y htmldoc-cli`. To try a skill
change before pushing, copy this directory into a project's
`.claude/skills/htmldoc/`. To test against an unpublished CLI, clone
[ajaxray/htmldoc-cli](https://github.com/ajaxray/htmldoc-cli) and run
`npm link` inside it.

## Learn more

[htmldoc.space](https://htmldoc.space)
