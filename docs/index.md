---
title: GitHub REST API Documentation
description: Authoritative, developer-focused documentation for the GitHub REST API with 607 endpoints, tutorials, how-to guides, and conceptual explanations.
meta:
  - name: description
    content: Complete developer documentation for GitHub REST API v3 with all 607 endpoints documented. Covers authentication, rate limiting, repositories, issues, PRs, actions, and more.
  - name: keywords
    content: GitHub API, REST API, GitHub REST v3, API documentation, GitHub developer, GitHub Actions, GitHub CLI
  - name: author
    content: Documentation Authority System
  - property: og:title
    content: GitHub REST API Documentation
  - property: og:description
    content: Authoritative developer documentation for the GitHub REST API - 607 endpoints documented
  - property: og:type
    content: website
tags:
  - GitHub API
  - REST API
  - Developer Documentation
  - Authentication
  - API Reference
related:
  - quickstart.md
  - explanations/authentication.md
  - explanations/rate-limiting.md
---

<div class="badges-row" style="display: flex; gap: 16px; justify-content: center; margin: 24px 0 16px 0; flex-wrap: wrap;">

<span style="background: #238636; color: white; padding: 10px 20px; border-radius: 8px; font-weight: 700; font-size: 15px; display: inline-flex; align-items: center; gap: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.15);">
  <svg height="18" viewBox="0 0 16 16" width="18" fill="white"><path d="M8 0c4.42 0 8 3.58 8 8a8.013 8.013 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38 0-.27.01-1.13.01-2.2 0-.75-.25-1.23-.54-1.48 1.78-.2 3.65-.88 3.65-3.95 0-.88-.31-1.59-.82-2.15.08-.2.36-1.02-.08-2.12 0 0-.67-.22-2.2.82-.64-.18-1.32-.27-2-.27-.68 0-1.36.09-2 .27-1.53-1.03-2.2-.82-2.2-.82-.44 1.1-.16 1.92-.08 2.12-.51.56-.82 1.28-.82 2.15 0 3.06 1.86 3.75 3.64 3.95-.23.2-.44.55-.51 1.07-.46.21-1.61.55-2.33-.66-.15-.24-.6-.83-1.23-.82-.67.01-.27.38.01.53.34.19.73.9.82 1.13.16.45.68 1.31 2.69.94 0 .67.01 1.3.01 1.49 0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8Z"></path></svg>
  Auto-Synced via GitHub Actions
</span>

<span style="background: #1f6feb; color: white; padding: 10px 20px; border-radius: 8px; font-weight: 700; font-size: 15px; box-shadow: 0 2px 8px rgba(0,0,0,0.15);">
  607 Endpoints Documented
</span>

<span style="background: #8250df; color: white; padding: 10px 20px; border-radius: 8px; font-weight: 700; font-size: 15px; box-shadow: 0 2px 8px rgba(0,0,0,0.15);">
  MkDocs Powered
</span>

</div>

All content is generated directly from the Postman collection and repository source — nothing is speculated or invented. Auto-synced on every commit.

## Documentation Structure

This site follows the [Diátaxis](https://diataxis.fr/) framework. Content is divided into four distinct categories, each serving a different purpose:

| Section | Purpose | Start Here If... |
| --- | --- | --- |
| [Quick Start](quickstart.md) | First API call in under 10 minutes | You are new to the GitHub API |
| [Tutorials](tutorials/index.md) | Learning through doing | You want to understand how the API works |
| [How-to Guides](how-to/index.md) | Recipes for specific tasks | You know what you want to accomplish |
| [Explanations](explanations/index.md) | Conceptual understanding | You want to know why, not just how |
| [API Reference](api-reference/repos.md) | Complete endpoint catalogue | You need exact parameter and schema details |

---

## Core Design Principles

**Traceable**
: Every statement is verifiable against a source artifact — the Postman collection, the repository, or a live API response. No speculated functionality is documented.

**Deterministic**
: Documentation is generated through defined, repeatable processes via the Automation Tier. The same inputs always produce the same outputs.

**Developer-Focused**
: Optimized for operational clarity. Endpoints include cURL, Python, and JavaScript examples. Parameters link to specific schema definitions. Error codes map to verified API responses.

---

## System Components

**Expert Modules** (`expert-modules/`)
: Logical capability manifests. Define what content to generate and how to structure it. The `dx-docs-expert` module implements the Diátaxis framework for this site.

**Automation Processors** (`automation-tier/`)
: Deterministic Python scripts. Execute file generation, schema extraction, auditing, and deployment. No semantic decisions are made here.

**MkDocs Material**
: High-fidelity documentation theme. Provides tabbed code examples, admonitions, full-text search, and dark mode support.

---

> [!NOTE]
> This documentation is automatically synchronized with the Postman collection source of truth. When the collection changes, the processors regenerate affected pages and validate navigation integrity before deployment.
