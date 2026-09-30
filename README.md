# How I work with AI agents

**See it live:** https://ralphalejandrino.github.io/agents/

Most of my engineering work goes through a Claude Code agent that I've set up and refined over
time. I call it Cici. The model is only part of it. What makes it reliable enough to use on real
client systems is the structure I've built around it.

## What that structure looks like

- **It keeps its memory in files.** Project state, the task board and a log of every session
  live in a Markdown knowledge base under git. Each session starts by reading where things
  stand, and a hook commits the changes after every reply, so an interruption costs almost
  nothing.
- **It follows written procedures.** Deploying, building the desktop app, changing client data
  and running the Android test bench each have a step-by-step protocol that the agent loads by
  name instead of working from memory.
- **It reaches my tools through an MCP server I wrote.** It's in Python, with 21 Gmail, Calendar
  and Drive tools, and each one is marked read-only, write or destructive so the risky ones are
  obvious.
- **A second agent checks its work.** A lighter model handles searches, and a stronger one acts
  as the auditor: it re-runs the tests and confirms a fix's test actually fails when the fix is
  removed. The auditor never reviews its own code.
- **It learns from its mistakes.** When something goes wrong, the lesson is saved along with
  what caused it, and every later session loads it.
- **It only has the access it needs.** On a client's register it can run exactly one privileged
  command, the deploy script. Nothing gets sent, deployed or deleted until I say yes.

## What's on the page

Four real sessions you can step through: starting the day, deploying to a point-of-sale
system, testing a text-message order end to end, and diagnosing a bug from a video. It also
covers the idea the whole setup rests on (the tools make the decisions, and the model reports
them), a sample of the saved lessons, and the failures that shaped it.

## About this repo

`index.html` is the entire page: one file, no build step. Open it in a browser, or use the live
link above.

The code the agent works on isn't public because it holds client data, and the session replays
have client names, hostnames and addresses removed.

## Also by me

- [Engineering case notes](https://ralphalejandrino.github.io/): five production incidents where
  the tooling said everything was fine and it wasn't.
- [CV](https://ralphalejandrino.github.io/cv/)

Ralph Alejandrino · Baguio, Philippines · ralphmiguelalejandrino@gmail.com
