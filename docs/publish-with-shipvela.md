# Publish with Shipvela: template and course kit

Give someone who has finished a website a clear next step: connect their assistant, confirm publishing, and open the live URL.

This is a first-party Shipvela kit. Adding it does not imply a partnership with OpenAI, Anthropic, Cursor or the template author. No payment, commission or exclusivity is part of this kit.

## Add a publishing badge to your README

[![Publish with Shipvela](../assets/publish-with-shipvela.svg)](https://shipvela.com/integrations/assistants?utm_source=github_template&utm_medium=referral&utm_campaign=publish_with_shipvela&utm_content=readme_badge)

Copy this into your template README:

```md
[![Publish with Shipvela](https://raw.githubusercontent.com/stefanautomateed/shipvela-codex/main/assets/publish-with-shipvela.svg)](https://shipvela.com/integrations/assistants?utm_source=github_template&utm_medium=referral&utm_campaign=publish_with_shipvela&utm_content=readme_badge)
```

The badge opens setup instructions. Clicking it does not upload code, grant access, create a project or deploy a website. Use a stable non-personal template identifier in utm_content if you need to distinguish your template. Never put emails, tokens or other private data in referral links.

## Install for Codex

```sh
codex plugin marketplace add stefanautomateed/shipvela-codex
codex plugin add shipvela@shipvela-beta
codex mcp login shipvela
```

[Full setup](https://shipvela.com/integrations/codex). This is direct beta distribution; official catalog publication is a separate review.

## Install for Claude Code

```sh
claude plugin marketplace add stefanautomateed/shipvela-codex
claude plugin install shipvela@shipvela-beta
```

Connect the Shipvela MCP server through Claude Code's normal OAuth flow. [Claude and Claude Code setup](https://shipvela.com/integrations/claude).

## Connect Cursor or Claude

Use [Cursor setup](https://shipvela.com/integrations/cursor) or [Claude setup](https://shipvela.com/integrations/claude). The remote endpoint is `https://shipvela.com/mcp`. Each user connects their own verified Shipvela account. Keep credentials out of the template.

## A short first-publish lesson

1. Download the [static starter](https://shipvela.com/downloads/shipvela-static-starter.zip), unzip it and customize the public files. The root must include index.html.
2. Create a Shipvela account, verify your email and connect your preferred assistant.
3. Ask the assistant to inspect the intended public files and identify whether this is a static upload or a GitHub build.
4. Use the prompt below after reviewing its proposed target.
5. For a small chat upload, open the returned review link and personally confirm the file manifest in Shipvela. For a GitHub deployment, follow the exact returned job.
6. Wait for a successful deployment, open the returned HTTPS URL, then make a small change and repeat the reviewed update.

Prompt:

> Publish this website on Shipvela. Identify the connected account, intended project and public files or GitHub branch first. Ask me to confirm the target before publishing. Follow the exact deployment job and return its status and live URL. If anything fails, explain the error and the next step. Do not change billing, domains or unrelated projects.

The public starter is a plain HTML/CSS example. React/Vite projects need a successful build and the generated output directory; unbuilt source is not a static website. [React/Vite walkthrough](https://shipvela.com/guides/deploy-react-vite-production).

## Supported publishing paths

| Input | Path |
| --- | --- |
| Small public HTML/CSS/JS website | MCP staging: up to 500 KB and 100 files, root index.html, owner confirmation required |
| Larger built static site | Separately authorized CLI upload: up to 50 MB and 5,000 files |
| Connected GitHub repository | Build configured remote production branch; local edits must first be pushed |
| Supported Next.js SSR 12–15 | GitHub deployment on a paid plan |

Hobby includes 3 projects and 20 publishes per month. Publishing uses that allowance and can replace a live website. Databases and general backend processes are not provisioned. A submitted or running job is not yet a live website. Check current [pricing](https://shipvela.com/#pricing), [CLI docs](https://shipvela.com/docs) and [publishing permissions](https://shipvela.com/integrations/assistants).

## Suggested template description

> Build your website in your preferred editor. Publish its static output or connected GitHub branch through Shipvela, then share the live HTTPS URL. You keep your code and connect your own hosting account.

For a dedicated partner link or a joint tutorial: [hello@shipvela.com](mailto:hello@shipvela.com). [Partner page](https://shipvela.com/partners).
