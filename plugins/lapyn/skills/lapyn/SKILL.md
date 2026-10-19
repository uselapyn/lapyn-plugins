---
name: lapyn
description: Operate an authorized Lapyn design through Code Mode MCP, or diagnose connection failures. Do not use for ordinary repository work or generic debugging.
---

# Lapyn

This skill ships with Lapyn plugin `0.2.0`. The Lapyn MCP server owns how to work with Lapyn, and its texts are current: its instructions, and the `sdk_reference` answers, which carry the guidance for the topics they cover. Where this skill and the server disagree, follow the server.

1. Before your first `code` call in a session, call `sdk_reference` without a topic and with `plugin: "0.2.0"`. It returns the workflow, the recovery rules and the topic list. If it says the plugin is outdated, tell the user once how to update it.
2. Before authoring, read the topics or groups your code uses, such as `props.layout`, `props` or `drafts`, and follow the guidance they end with.
3. Run JavaScript with the `code` tool as the server instructions describe.

Use the MCP endpoint the plugin configures; never substitute or probe another environment. SDK changes never need a reconnect: a fingerprint mismatch error says how to continue. Reconnect or reauthorize only when the credential expired or was revoked.
