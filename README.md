# Lapyn for Claude Code and Codex

Design in Lapyn by asking your coding agent. With this plugin, Claude Code or Codex can build new screens in your
Lapyn project, restyle existing ones, translate your designs into other languages, and explain how a design is put
together. When it changes a screen, the agent renders it and checks the result before it reports back.

You don't need Lapyn open. Ask from your terminal, your editor or wherever you run your agent, and the changes are
saved to your Lapyn project, ready the next time you open it.

## Install

**Claude Code**

```bash
claude plugin marketplace add uselapyn/lapyn-plugins
claude plugin install lapyn@lapyn
```

**Codex**

```bash
codex plugin marketplace add uselapyn/lapyn-plugins
codex plugin add lapyn@lapyn
```

## Sign in

You need a Lapyn account. The first time the agent uses Lapyn, your browser asks you to sign in and choose which
projects the agent may use, and whether it may only view them or also edit them. You can disconnect it at any time in
your Lapyn account.

## Try it

- "Create a sign-up screen for my app in Lapyn."
- "Translate the onboarding screens into German and Spanish."
- "Give the settings screen a darker, calmer look."
- "Explain how the home screen is laid out."

## Updates

When a new version is out, the agent tells you. In Claude Code, run `claude plugin update lapyn@lapyn`, or turn on
**Enable auto-update** for the `lapyn` marketplace under `/plugin` › **Marketplaces** to get new versions on their own.

## Privacy

The agent's requests run on Lapyn's servers; the plugin runs nothing on your computer. What the agent reads from your
projects becomes part of your conversation with it.

## Questions

Write to hello@lapyn.com. This repository is a published copy of the plugin, so pull requests aren't accepted here.

The plugin is licensed under the [Apache License 2.0](plugins/lapyn/LICENSE).
