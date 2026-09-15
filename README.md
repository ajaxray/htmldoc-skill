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

Then ask your agent in plain words: **"share this report"**, **"publish process.html with htmldoc"**, or **"make this plan shareable"** (after the one-time setup below). It replies with the link and the expiry date.

Source: [ajaxray/htmldoc-skill](https://github.com/ajaxray/htmldoc-skill). The
CLI it drives: [ajaxray/htmldoc-cli](https://github.com/ajaxray/htmldoc-cli),
published on npm as [`htmldoc-cli`](https://www.npmjs.com/package/htmldoc-cli).

## First run

Nothing to set up. The first time you ask your agent to share a file, the
CLI has no API key yet, so the agent runs `htmldoc login`, which prints an
approval link (and opens it in your browser), then waits with
`htmldoc login --wait`. Sign in with GitHub, check that the code on the page
matches the one the agent showed you, and click Approve. The CLI stores your
key and the agent finishes the share. The agent announces each of those steps
before it happens and never sees the key.

If you prefer the old way, `htmldoc login --paste` accepts the key from your
dashboard in an interactive terminal.

## Local development

The skill needs the `htmldoc-cli` npm package: either installed globally
(`htmldoc` on PATH) or resolvable via `npx -y htmldoc-cli`. To try a skill
change before pushing, copy this directory into a project's
`.claude/skills/htmldoc/`. To test against an unpublished CLI, clone
[ajaxray/htmldoc-cli](https://github.com/ajaxray/htmldoc-cli) and run
`npm link` inside it.

## Feedback

Skill misbehaving: [issues here](https://github.com/ajaxray/htmldoc-skill/issues). Feature requests, roadmap votes, and anything about the site: [ajaxray/htmldoc.space](https://github.com/ajaxray/htmldoc.space/issues).

## Learn more

[htmldoc.space](https://htmldoc.space)
