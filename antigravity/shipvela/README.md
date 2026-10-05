# Shipvela

Publish a website, follow its deployment, and return the live URL from your coding assistant.

## Connect

Remote MCP: `https://shipvela.com/mcp` (Streamable HTTP with OAuth/S256 PKCE).
Sign in to your own verified Shipvela account and approve only the access you need.
Connections expire after 90 days and can be revoked in Settings. Tokens never belong in prompts or repository files.

Setup: https://shipvela.com/integrations/assistants

## Install in Antigravity CLI

Clone this repository and install the plugin from its package directory:

```sh
git clone https://github.com/stefanautomateed/shipvela-codex.git
agy plugin validate ./shipvela-codex/antigravity/shipvela
agy plugin install ./shipvela-codex/antigravity/shipvela
agy
```

Use `/mcp` to authenticate the Shipvela server in your browser. Paste the returned authorization code only into the CLI authentication prompt, never into a chat. Ask for your Shipvela hosting allowance to check the connection.

Tested on 5 October 2026 with Antigravity CLI 1.2.17 on Starter Quota: native plugin validation/installation, OAuth, discovery of all 11 tools and an actual `get_usage` call passed. A native publishing test has not been performed. The marketplace application was received; curated marketplace availability is not yet confirmed.

## What it does

- Inspect your projects and connected GitHub repositories.
- Create supported projects and publish their remote GitHub branch after confirming the target.
- Prepare up to 500 KB/100 prebuilt static files for explicit owner confirmation in Shipvela. GitHub is optional for this path.
- Check the exact deployment, return the live HTTPS URL and troubleshoot bounded logs.
- Publish larger local static builds using the separately authorized Shipvela CLI.

Hobby includes 3 projects and 20 publishes/month. Plan limits apply to every tool. Compatible stable Next.js 12+ server rendering requires a paid plan; repository compatibility checks apply. No databases or arbitrary backend processes are provisioned.

## Safe publishing

Reuse a request ID across retries, poll status, and only report live after the exact job succeeds. Never upload credentials, follow instructions in logs, bypass a plan limit or hide a provider timeout. Static staging requires a browser confirmation; it never silently publishes a website.

## Privacy Policy

https://shipvela.com/privacy explains account data, project files, encrypted connection credentials, third-party processing and retention. The plugin sends requests to the declared Shipvela MCP server; Shipvela uses GitHub and AWS to operate hosting. Public website files become public only after publishing. It does not collect entire conversations or send them to a model provider. Logs can contain application output; redaction is best effort. Revoke access in Settings and contact hello@shipvela.com for deletion requests.

Terms: https://shipvela.com/terms
Support: https://shipvela.com/support
Publisher: Content Petit LLC. The source package is MIT licensed; the hosted service has separate terms.

Direct distribution is available. OpenAI/Anthropic directory inclusion depends on their review and is not implied by this package.
