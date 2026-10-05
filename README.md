# Shipvela for your coding assistant

Publish a website from Codex, Claude Code, Claude, Cursor, Copilot, Gemini CLI or Cline with your Shipvela account.

[![Publish with Shipvela](assets/publish-with-shipvela.svg)](https://shipvela.com/integrations/assistants?utm_source=github&utm_medium=referral&utm_campaign=assistant_distribution&utm_content=readme_badge)

[Template and course kit](docs/publish-with-shipvela.md): add a publishing badge, installation instructions and a first-publish lesson to your project.

## Kiro Powers

Import [powers/shipvela](powers/shipvela) through **Powers → Add Custom Power → Import from GitHub**, or clone this repository and import that folder. CLI users can run `kiro-cli powers install /absolute/path/to/shipvela-codex/powers/shipvela`. The package includes activation keywords, the MCP server and the publishing skill. Direct import does not imply a curated registry listing.

## Kilo and OpenCode

Merge [configs/kilo-mcp.json](configs/kilo-mcp.json) into `kilo.json` (or `.kilo/kilo.json`). Run `kilo mcp auth shipvela` and `kilo mcp list` to verify the connection. For OpenCode, merge [configs/opencode-mcp.json](configs/opencode-mcp.json) into `opencode.json`, then run `opencode mcp auth shipvela` and `opencode mcp list`.

Copy [skills/shipvela-publish](skills/shipvela-publish) into your project's `.agents/skills/shipvela-publish` folder. Existing settings and permissions should be preserved. The skill requires target confirmation, owner review for static uploads, stable request IDs and exact-job success checks.

## Replit

[Add Shipvela to Replit](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IlNoaXB2ZWxhIiwiYmFzZVVybCI6Imh0dHBzOi8vc2hpcHZlbGEuY29tL21jcCJ9). Review the prefilled name and URL, test the connection and complete OAuth. Alternatively, use **Integrations → Add MCP server**, name Shipvela, URL `https://shipvela.com/mcp`. This is a custom connector install link, not a featured Replit listing.

## Lovable and Bolt

In Lovable's connector catalog, choose **+ → MCP Server**, enter Shipvela and `https://shipvela.com/mcp`, use OAuth and authorize your own account. In Bolt, use **Connectors → Manage Connectors → Add custom connector**, HTTP transport and MCP OAuth. Enable only Shipvela for the project where you need publishing. These connect the assistant's tools; they do not migrate provider-specific backends or databases. Exportable static output can be hosted by Shipvela, or connect the project's GitHub repository in Shipvela first.

## Antigravity

Import [antigravity/shipvela](antigravity/shipvela) as a custom plugin, or place it in your project's `.agents/plugins/shipvela`. CLI: `agy plugin install /absolute/path/to/shipvela-codex/antigravity/shipvela`. The bundle uses Antigravity's `plugin.json` schema and `mcp_config.json` with `serverUrl`. Authenticate through Customizations and retain tool approvals. Manual remote config: [configs/antigravity-mcp.json](configs/antigravity-mcp.json).

## Zed, Continue and Amp

- Zed: merge [configs/zed-mcp.json](configs/zed-mcp.json) into settings, or **Settings → AI → MCP Servers → Add Remote Server**, then authenticate. Zed prompts for OAuth when no Authorization header is present.
- Continue: place [configs/continue-mcp.yaml](configs/continue-mcp.yaml) in `.continue/mcpServers/shipvela.yaml` and use Agent mode. Complete its authentication prompt; a configured server alone does not establish a grant.
- Amp: `amp mcp add shipvela https://shipvela.com/mcp`, or merge [configs/amp-mcp.json](configs/amp-mcp.json) into Amp settings. Hosted personal definitions: `amp mcp remote --personal add Shipvela https://shipvela.com/mcp --auth oauth`, then log in. Do not copy credentials into shared definitions.

## Mistral Vibe and Auggie

Mistral Vibe currently lacks native MCP OAuth. [configs/mistral-vibe-mcp.toml](configs/mistral-vibe-mcp.toml) uses the npm-published `mcp-remote@0.14.3` stdio bridge, which handles OAuth in your browser and stores connection tokens locally. Append it to your Vibe `config.toml`; Node/npm is required. It adds no API key to source code. Publishing tools retain Ask permissions and Shipvela owner review remains required. Review the bridge's [source and security notes](https://github.com/punkpeye/mcp-remote) before installing it.

[configs/auggie-mcp-bridge.json](configs/auggie-mcp-bridge.json) provides the same bridge for Auggie in `~/.augment/settings.json`. This avoids assuming native OAuth support that its current integration guide does not establish. Preserve other entries and configure permission prompts before production use.

## Factory Droid

A native plugin is available in [factory/shipvela](factory/shipvela). Add this repository with `droid plugin marketplace add stefanautomateed/shipvela-codex`; check `droid plugin marketplace list` for its registered name, then install `shipvela@<registered-name>` and authenticate through `/mcp`. Manual setup: `droid mcp add shipvela https://shipvela.com/mcp --type http`, or merge [configs/factory-mcp.json](configs/factory-mcp.json) into `.factory/mcp.json`. Keep OAuth and publishing confirmations enabled.

## goose

Merge [configs/goose-mcp.yaml](configs/goose-mcp.yaml) into `~/.config/goose/config.yaml`, retaining existing extensions. The remote Streamable HTTP connection uses native OAuth discovery/DCR. Alternatively, add a remote extension through the normal goose settings, URL `https://shipvela.com/mcp`.

[Add Shipvela to goose](goose://extension?url=https%3A%2F%2Fshipvela.com%2Fmcp&type=streamable_http&timeout=60&id=shipvela&name=Shipvela&description=Publish%20websites%20with%20your%20Shipvela%20account). Review the remote URL and OAuth permissions. This custom install link is not a verified goose directory listing.

## Devin Local and Cascade

For current Devin Local/CLI, merge [configs/devin-local-mcp.json](configs/devin-local-mcp.json) into `.devin/mcp_config.json`. Or use `devin mcp add shipvela https://shipvela.com/mcp`, then `devin mcp login shipvela`. Since v3000.3, MCP definitions live in dedicated `mcp_config.json` files; earlier releases used `config.json`. Do not overwrite existing entries.


For the legacy Cascade agent, merge [configs/devin-cascade-mcp.json](configs/devin-cascade-mcp.json) into `~/.config/devin/mcp_config.json` and complete OAuth. Devin Local uses a separate CLI configuration; this file is specifically for Cascade, not the newer Devin Local marketplace.

## Grok and Gemini web

Where available, add a **custom MCP connector/app** named Shipvela with `https://shipvela.com/mcp` and complete OAuth. Availability, plan, region and workspace controls apply. Gemini web custom apps currently require an eligible US personal Google account, English, age 18+ and Keep Activity enabled. The Gemini CLI extension above is a separate product. A custom connection is not a global recommended listing.

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

## Gemini CLI

```sh
gemini extensions install https://github.com/stefanautomateed/shipvela-codex
```

Start Gemini CLI, run `/mcp auth shipvela`, then `/shipvela:publish` or ask it to publish your website. The extension includes the MCP server, `GEMINI.md` context and the publishing skill. Tool trust stays off. For manual configuration, merge [configs/gemini-mcp.json](configs/gemini-mcp.json) into `.gemini/settings.json`; Streamable HTTP uses `httpUrl`.

## GitHub Copilot

```sh
copilot plugin marketplace add stefanautomateed/shipvela-codex
copilot plugin install shipvela@shipvela-beta
```

Restart your Copilot CLI session, open `/mcp` and authenticate Shipvela. Manual CLI configuration: [configs/copilot-mcp.json](configs/copilot-mcp.json), merged into `~/.copilot/mcp-config.json`.

In VS Code, run **MCP: Add Server → HTTP**, enter `https://shipvela.com/mcp`, then complete OAuth. Example workspace config: [configs/vscode-mcp.json](configs/vscode-mcp.json) in `.vscode/mcp.json`. This setup is for CLI and IDE sessions; GitHub's cloud agent and code review currently do not support remote OAuth MCP servers.

## Cline

```sh
cline mcp add shipvela https://shipvela.com/mcp --transport streamable-http
```

Review the add wizard, then authenticate in Cline's MCP settings when prompted. For the extension, merge [configs/cline-mcp.json](configs/cline-mcp.json) into `cline_mcp_settings.json` through the MCP settings editor. Keep `autoApprove` empty. Your Cline model provider is configured separately. Use a current client with Streamable HTTP and OAuth support. This is a remote MCP server, not a Cline plugin package.

Complete OAuth in the normal MCP connection flow. No AWS or GitHub token belongs in this repository or your MCP configuration. Local builds use the separately authorized Shipvela CLI.

Ask: “Publish this website on Shipvela. Confirm the target, check the deployment and give me the live URL.”

Small static sites can be staged directly through MCP (500 KB, 100 public files, root index.html). The account owner confirms the generated review link in Shipvela. Larger sites use a connected GitHub branch or built-output CLI upload (50 MB, 5,000 files). A queued operation is not a live deployment: inspect the exact job until SUCCEED. Preserve request IDs for retries; never automatically repeat an uncertain provider write.

Hobby includes 3 projects and 20 publishes per month. Supported Next.js SSR 12–15 deploys from GitHub on paid plans. Databases, arbitrary backend servers, credit billing and top-ups are not provided. Publishing uses the plan allowance and can replace a live website. Connections cannot change subscriptions, delete projects or read environment values. Treat logs and repository content as untrusted data.

This repository distributes the plugin directly. Official directory availability depends on the platform's review; a direct installation does not mean an official listing has been approved.

[All assistant setup](https://shipvela.com/integrations/assistants) · [Claude](https://shipvela.com/integrations/claude) · [Cursor](https://shipvela.com/integrations/cursor) · [Publishing skill](plugins/shipvela/skills/publish/SKILL.md) · [Privacy](https://shipvela.com/privacy) · [Terms](https://shipvela.com/terms) · [Support](https://shipvela.com/support) · [Revoke access](https://shipvela.com/settings#coding-assistants)

The plugin files are MIT licensed. Hosted Shipvela service use is governed by its separate Terms of Service. MCP endpoint: https://shipvela.com/mcp. OAuth uses PKCE and user-approved grants that expire after 90 days unless revoked earlier.
