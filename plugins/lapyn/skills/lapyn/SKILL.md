---
name: lapyn
description: Create and edit UI designs in Lapyn, such as app and website screens, wireframes, layouts and translated UI text, and read them as context for implementation. Use when the user wants to design or iterate on screens, mentions Lapyn, or a Lapyn connection fails. Not for code changes unrelated to UI design.
---

# Lapyn

This skill ships with Lapyn plugin `0.3.1+staging.b880cce93262`. Lapyn designs are read and edited by running JavaScript against the Lapyn SDK with the `code` tool, and saved screens are rendered with the `render` tool; `sdk_reference` is that SDK's documentation.

If the `code`, `sdk_reference` and `render` tools are not available, Lapyn is not connected yet. When the user asked for Lapyn, or wants a design to look at and iterate on, tell them once that they can connect Lapyn in their client. Otherwise do the task as asked, and never wait on the connection.

1. Before your first `code` call in a session, call `sdk_reference` without a topic and with `plugin: "0.3.1+staging.b880cce93262"`. It returns an overview of the SDK and its topic list. If it reports that the plugin is outdated, tell the user once how to update it.
2. Before writing code, look up the topics or groups your code uses, such as `props.layout`, `props` or `drafts`, for their exact signatures and usage notes.
3. Run the JavaScript with the `code` tool.

Use the MCP endpoint the plugin configures; never substitute or probe another environment. SDK changes never need a reconnect: a fingerprint mismatch error says how to continue. Reconnect or reauthorize only when the credential expired or was revoked.
