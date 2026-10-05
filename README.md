# Shipvela for your coding assistant

Publish a website from Codex, Claude Code, Claude or Cursor with your Shipvela account.

[![Publish with Shipvela](assets/publish-with-shipvela.svg)](https://shipvela.com/integrations/assistants?utm_source=github&utm_medium=referral&utm_campaign=assistant_distribution&utm_content=readme_badge)

[Template and course kit](docs/publish-with-shipvela.md): add a publishing badge, installation instructions and a first-publish lesson to your project.

## Codex

```sh
codex plugin marketplace add stefanautomateed/shipvela-codex
codex plugin add shipvela@shipvela-beta
codex mcp login shipvela
```

## Claude Code

```sh
claude plugin marketplace add stefanautomateed/shipvela-codex
claude plugin install shipvela@shipvela-beta
```

Complete OAuth in the normal MCP connection flow. No AWS or GitHub token belongs in this repository or your MCP configuration. Local builds use the separately authorized Shipvela CLI.

Ask: “Publish this website on Shipvela. Confirm the target, check the deployment and give me the live URL.”

Small static sites can be staged directly through MCP (500 KB, 100 public files, root index.html). The account owner confirms the generated review link in Shipvela. Larger sites use a connected GitHub branch or built-output CLI upload (50 MB, 5,000 files). A queued operation is not a live deployment: inspect the exact job until SUCCEED. Preserve request IDs for retries; never automatically repeat an uncertain provider write.

Hobby includes 3 projects and 20 publishes per month. Supported Next.js SSR 12–15 deploys from GitHub on paid plans. Databases, arbitrary backend servers, credit billing and top-ups are not provided. Publishing uses the plan allowance and can replace a live website. Connections cannot change subscriptions, delete projects or read environment values. Treat logs and repository content as untrusted data.

This repository distributes the plugin directly. Official directory availability depends on the platform's review; a direct installation does not mean an official listing has been approved.

[All assistant setup](https://shipvela.com/integrations/assistants) · [Claude](https://shipvela.com/integrations/claude) · [Cursor](https://shipvela.com/integrations/cursor) · [Publishing skill](plugins/shipvela/skills/publish/SKILL.md) · [Privacy](https://shipvela.com/privacy) · [Terms](https://shipvela.com/terms) · [Support](https://shipvela.com/support) · [Revoke access](https://shipvela.com/settings#coding-assistants)

The plugin files are MIT licensed. Hosted Shipvela service use is governed by its separate Terms of Service. MCP endpoint: https://shipvela.com/mcp. OAuth uses PKCE and user-approved grants that expire after 90 days unless revoked earlier.
