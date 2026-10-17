# Lapyn Plugins

The Lapyn plugin for Claude Code and Codex: the Lapyn Code Mode skill and its MCP connection, so an agent can
inspect and author your Lapyn designs. Both hosts install the same `plugins/lapyn` directory.

Claude Code:

```bash
claude plugin marketplace add uselapyn/lapyn-plugins
claude plugin install lapyn@lapyn
```

Codex:

```bash
codex plugin marketplace add uselapyn/lapyn-plugins
codex plugin add lapyn@lapyn
```

The first use opens your browser to sign in to Lapyn and choose which projects the agent may use.

This repository is published automatically; pull requests are not merged here. Questions and feedback go to
hello@lapyn.com.
