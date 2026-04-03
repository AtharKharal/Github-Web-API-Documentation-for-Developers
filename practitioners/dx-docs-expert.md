---
name: dx-documentation-orchestrator
description: Systematic framework for transforming 288+ GitHub Web API endpoints into a high-impact Developer Experience (DX) ecosystem within MkDocs. Use this when the agent needs to structure guides, tutorials, or onboarding for the deployed API reference.
---

# Goal
To transition the "Antigravity-deployed" MkDocs API reference from a dictionary of endpoints into a systematic, rule-based documentation ecosystem that prioritizes "First Success" and functional discovery.

# Instructions

## 1. Apply the Diátaxis Mapping
When generating or restructuring documentation for the 288+ endpoints, categorize all content into the following four quadrants:

* **Tutorials (Learning-Oriented):** Create a 10-minute "Hello World" path using the Postman collection. Explain the mental model of Resource Interlinking (e.g., Repos -> Issues -> Actions).
* **How-to Guides (Problem-Oriented):** Provide recipe-style entries for specific workflows (e.g., "Bulk-updating labels across an Org").
* **Technical Reference (Information-Oriented):** Ensure every endpoint includes request/response schemas ($query$, $path$, $header$) and specific mapping for status codes ($404$, $422$, $500$).
* **Explanations (Understanding-Oriented):** Document the "Why"—specifically how the Antigravity system maintains the Postman-to-MkDocs "Source of Truth" synchronization.

## 2. Enforce Systematic DX Standards
Every documentation artifact must meet the following structural requirements:
* **Searchability:** Enable fuzzy-search capabilities across the entire endpoint list.
* **Code Multi-tenancy:** Provide snippets in cURL, Python, and JavaScript for every endpoint.
* **Traceability:** Every parameter and error code must have a unique deep-link URI.
* **Logical Grouping:** Organize the sidebar by functional resources (e.g., `/repos`, `/users`) rather than alphabetical lists.

# Constraints
* **No Surface-Level Descriptions:** Avoid redundant phrases like "This endpoint gets the user." Explain the logic of the response instead.
* **Strict Formatting:** Use standard Markdown. Avoid decorative symbols or emojis.
* **Mathematical Accuracy:** Represent all rate-limiting logic and header variables (e.g., `X-RateLimit-Remaining`) using LaTeX-style notation where appropriate.

# Examples

## User Request: "Help me write the onboarding guide for the repo endpoints."
**Agent Action:**
1. Reference the `/repos` section of the 288+ endpoint list.
2. Structure a "Tutorial" quadrant focusing on creating a repository.
3. Include a "How-to" quadrant for setting branch protection rules.
4. Link the "Reference" layer to the pre-deployed MkDocs URI for `/repos/{owner}/{repo}`.

## User Request: "Document the rate limit errors."
**Agent Action:**
1. Create an "Explanation" page detailing the primary and secondary limits.
2. Define the $X-RateLimit-Reset$ timestamp conversion logic.
3. Map the $403$ Forbidden response to the specific rate-limit exhaustion message in the Postman collection.