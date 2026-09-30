# How I work with AI agents

**Live, interactive version: https://ralphalejandrino.github.io/agents/**

I run my engineering work through one Claude Code agent. I call it Cici. It is Claude plus
everything built around it, so that its work can be trusted on real client systems:

- **State lives in files, not in the chat.** A git-backed Markdown knowledge base holds the live
  checkpoint, the task board and one log per session. A hook commits it after every reply.
- **Protocols are skills.** Deploys, desktop builds, data changes and an Android test bench each
  have a written procedure the agent loads by name.
- **An MCP server in Python.** 21 Gmail, Calendar and Drive tools, each annotated as read-only,
  write or destructive.
- **A second agent checks the first.** A cheap scout model searches; an expensive auditor model
  re-runs tests and proves a fix's test fails without the fix. It never reviews its own work.
- **Lessons, saved with their incident**, loaded in every future session.
- **Least privilege.** The deploy machine can run exactly one privileged command on a client's
  register. Nothing is sent, deployed or deleted without a yes from me in that turn.

The page replays four real sessions step by step (a morning load, a point-of-sale deploy, an
end-to-end test of a text order, and a bug report that arrived as a video), plus the principle
behind the design (*the tools decide, the model reports*), a sample of the saved lessons, and
the failures that shaped it.

## What is and isn't here

`index.html` is the whole page: one self-contained file, no build step. Open it locally or use
the live link above.

The production code the agent works on stays private, because it holds client data. Session
replays are abridged from real logs with client names, hostnames and addresses removed.

## Related

- [Engineering case notes](https://ralphalejandrino.github.io/): five production incidents where
  the tooling reported success and was wrong.
- [CV](https://ralphalejandrino.github.io/cv/)

Ralph Alejandrino · Baguio, Philippines · ralphmiguelalejandrino@gmail.com
