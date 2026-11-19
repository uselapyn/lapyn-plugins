# Lapyn MCP server and plugins

Design in Lapyn with your AI agent. The Lapyn MCP server lets Claude, Codex, and other MCP clients create screens,
restyle existing designs, translate content, and explore how your designs are structured. After making changes, the
agent renders the result and checks it before reporting back.

You don't need to keep Lapyn open. Work from your terminal, editor, or wherever you use your agent. Changes are saved
directly to your Lapyn projects, ready whenever you return.

## Install the plugin

The plugin sets up the MCP connection and includes a skill that helps your agent understand when and how to use Lapyn.
It's the easiest way to get started with Claude Code or Codex.

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

## Use with any MCP client

Lapyn works with any MCP client that supports Streamable HTTP and OAuth.

- **Server URL:** `https://lapyn.com/api/flow/v2/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth with your Lapyn account. No API key required.

**Claude** (web, desktop, and mobile): Find Lapyn in the connector directory and connect your account.

**Claude Code** without the plugin:

```bash
claude mcp add --transport http lapyn https://lapyn.com/api/flow/v2/mcp
```

**Codex** without the plugin:

```bash
codex mcp add lapyn --url https://lapyn.com/api/flow/v2/mcp
codex mcp login lapyn
```

## Connect your account

You'll need a Lapyn account to get started. The first time your agent connects, your browser opens the sign-in flow.

You choose which projects the agent can access and whether it has read-only or editing permissions. You can change or
revoke access at any time from your Lapyn account.

## Try it

Once connected, try asking your agent:

- "Create a sign-up screen for my app in Lapyn."
- "Translate my Lapyn onboarding screens into German and Spanish."
- "Give the settings screen in Lapyn a darker, calmer look."
- "Explain how the home screen in Lapyn is structured."

## Update the plugin

**Claude Code:** run `claude plugin update lapyn@lapyn`, or turn on **Enable auto-update** for the `lapyn` marketplace
under `/plugin` › **Marketplaces**.

**Codex:** run `codex plugin marketplace upgrade lapyn`, then `codex plugin add lapyn@lapyn`.

## Privacy

Your agent interacts with Lapyn through its MCP server. Requests are processed on Lapyn's servers, with no additional
local service required.

Information the agent retrieves from your projects becomes part of your conversation with your AI provider.

## Questions

Questions or feedback? Reach out at hello@lapyn.com.

This repository is a published copy of the Lapyn plugin and doesn't accept pull requests.

Licensed under the [Apache License 2.0](LICENSE).
