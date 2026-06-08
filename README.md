# AI Agent Security

AI Agent Security is a static training site and slide deck about defense-in-depth security for agentic AI systems. The repository contains a Marp-powered workshop deck, supporting visual assets, and local build scripts.

The current deck focuses on a 14-layer security model for enterprise AI agents, covering topics such as human oversight, agent identity and access management, prompt injection defense, tool authorization, action sandboxing, memory security, secrets protection, auditability, data governance, RAG poisoning defense, supply chain security, red teaming, multi-agent trust, and governance guardrails.

## Contents

- [Learning Topics](#learning-topics)
- [Repository Structure](#repository-structure)
- [Prerequisites](#prerequisites)
- [Quick Start](#quick-start)
- [Available Commands](#available-commands)
- [Troubleshooting](#troubleshooting)
- [Security Notes](#security-notes)
- [Attribution](#attribution)

## Learning Topics

The deck currently presents the following security layers:

1. Human Approval and Oversight
2. Agent IAM, or Identity and Access Management
3. Prompt Injection Defense
4. Tool, API, and MCP Authorization
5. Action Sandboxing
6. Memory Security
7. Secrets Protection
8. Audit and Traceability
9. Data Privacy and Governance
10. RAG and Knowledge Poisoning Defense
11. Supply Chain Security
12. Continuous Red Teaming
13. Delegation and Multi-Agent Trust
14. Agent Governance and Guardrails

These layers map naturally to common AI and LLM security concerns, including unauthorized tool use, prompt injection, data leakage, secret exposure, poisoned retrieval content, unsafe autonomous actions, weak audit trails, and unclear governance boundaries.

## Repository Structure

```text
AI-Agent-Security/
├── .github/
│   └── workflows/
│       └── pages.yml
├── decks/
│   └── owasp-top10-llm/
│       ├── deck.yml
│       └── slides.md
├── Resources/
│   ├── AI Agents Security.png
│   ├── AI_Agent_01.png
│   ├── AI_Agent_02.png
│   ├── ...
│   ├── AI_Agent_14.png
│   └── AI_Agents_Prompts_Explanation.txt
├── scripts/
│   ├── build-deck.js
│   └── build-site.js
├── site/
│   └── generated static site output
├── package.json
├── package-lock.json
└── README.md
```

### Important paths

| Path | Purpose |
| --- | --- |
| `decks/owasp-top10-llm/slides.md` | Main Marp slide source. Edit this file when changing slide content. |
| `decks/owasp-top10-llm/deck.yml` | Deck metadata used by the generated landing page. |
| `Resources/` | Source images and supporting text used by the deck. |
| `scripts/build-deck.js` | Compiles the Marp deck into `site/owasp-top10-llm/index.html`. |
| `scripts/build-site.js` | Builds the full static website, copies resources, compiles the deck, and writes `site/index.html`. |
| `site/` | Generated output. This directory is ignored by Git and can be rebuilt. |

## Prerequisites

Install the following before working with the project locally:

- Node.js 20 or newer is recommended.
- npm, which is included with Node.js.
- Git, if you plan to version and publish changes.

The project uses these development dependencies:

- `@marp-team/marp-cli` to convert Markdown slides into a browser-ready HTML deck.
- `http-server` to preview the generated static site locally.

## Quick Start

From the repository root:

```bash
npm install
npm run build
npm run preview
```

Then open the preview URL printed by `http-server`. By default, the preview command serves the generated `site/` directory from `127.0.0.1`.

The generated landing page is:

```text
site/index.html
```

The generated slide deck is:

```text
site/owasp-top10-llm/index.html
```

## Available Commands

| Command | What it does |
| --- | --- |
| `npm install` | Installs local Node dependencies from `package-lock.json`. |
| `npm run build` | Builds the complete static site into `site/`. |
| `npm run site` | Same as `npm run build`; runs `scripts/build-site.js`. |
| `npm run build:deck` | Builds only the Marp slide deck into `site/owasp-top10-llm/`. |
| `npm run preview` | Serves `site/` locally with caching disabled. |

## Troubleshooting

### `Marp CLI is not installed. Run npm install first.`

Run:

```bash
npm install
```

Then rebuild:

```bash
npm run build
```

### Images are missing in the generated deck

Check the following:

- The image exists in `Resources/`.
- The path in `slides.md` starts with `../../Resources/`.
- Spaces in image filenames are encoded as `%20`.
- You rebuilt the site after changing image files.

### The preview server shows old content

Stop the preview server, rebuild, and start it again:

```bash
npm run build
npm run preview
```

The preview command disables HTTP caching, but a full rebuild is still required after changing source slides or resources.

### `site/` disappeared or changed unexpectedly

This is expected. `site/` is generated output. The build script deletes and recreates it each time `npm run build` or `npm run site` runs.

## Security Notes

This repository is about security education, but the repository itself should still be handled carefully.

- Do not commit real secrets, API keys, access tokens, credentials, or private certificates.
- Do not include sensitive internal system details in screenshots or generated images.
- Review training examples before using them in customer, regulated, or public environments.
- Treat AI-generated images and text as training material that should be reviewed by a human before publication.
- Keep dependencies updated and review changes to `package-lock.json`.
- If this material is adapted for healthcare, finance, or other regulated contexts, validate examples against the applicable policy and compliance requirements.

## Attribution

The OWASP Top 10 for LLM Applications 2025 training material in this repository was designed and developed by CN Madhu. The workshop combines industry-relevant AI security concepts and practical learning material to explain real-world AI security risks, vulnerabilities, and defense strategies in enterprise and healthcare-oriented environments.

## License

No explicit license file is currently included in this repository. Before redistributing, publishing, or reusing the material outside its intended environment, confirm the appropriate usage permissions with the repository owner or content author.
