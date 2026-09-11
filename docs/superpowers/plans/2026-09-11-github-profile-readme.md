# GitHub Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the generic profile README with a concise, recruiter-oriented portfolio for AI Application / Agent Engineer roles.

**Architecture:** A single Markdown document is the deliverable. It uses standard Markdown/HTML layout and the component patterns popularized by `rahuldkjain/github-profile-readme-generator`, but limits them to a professional introduction, verified skills and project links, contact details, and two GitHub image cards.

**Tech Stack:** GitHub Flavored Markdown, HTML image/link tags, Simple Icons CDN, GitHub Readme Stats image endpoints.

**Spec:** `docs/superpowers/specs/2026-09-11-github-profile-design.md`

## Global Constraints

- Use concise English for the README's primary copy.
- Do not claim seniority, ownership, metrics, or outcomes not supported by public information.
- Describe `folio` as an open-source project and do not imply original authorship because it is a fork.
- Retain the current LinkedIn URL and University of Melbourne email address.
- Include no visitor counter, trophies, typing banner, snake graph, animated assets, or extensive badge wall.
- Use only AI/agent, backend, and engineering technologies currently stated in the README or supported by the public project description.

---

### Task 1: Write the recruiter-oriented profile README

**Files:**
- Modify: `README.md`
- Test: `README.md` structural and link validation via PowerShell

**Interfaces:**
- Consumes: GitHub profile `Rapeter`, public repository `Rapeter/folio`, current contact details, and the approved design spec.
- Produces: A standalone GitHub Profile README rendered by `Rapeter/Rapeter`.

- [ ] **Step 1: Write the failing structural test**

Create a PowerShell check that reads `README.md`, asserts the markers `AI Application & Agent Engineer`, `About Me`, `AI & Agent Systems`, `Featured Project`, `Rapeter/folio`, `github-readme-stats`, the current LinkedIn path, and the current email address, and rejects `visitor`, `trophy`, `typing-svg`, or `snake`.

- [ ] **Step 2: Run the test against the current README**

Run the Step 1 script in PowerShell. Expected: it reports missing role, project, and GitHub stats markers.

- [ ] **Step 3: Implement the approved README content**

Replace the existing generic content with a centered `Hi, I'm Kaizhong 👋` heading, the role `AI Application & Agent Engineer`, and the positioning statement: `Building reliable agentic workflows and LLM-powered products, grounded in backend engineering.` Add `About Me`, `AI & Agent Systems`, `Backend & Engineering`, `Featured Project`, `GitHub at a Glance`, and `Let's Connect` in that order. Use compact Simple Icons image links with alt text for: AI Agents, LLM Applications, RAG, Tool Calling, Multi-Agent Systems, Python, JavaScript, Node.js, Express, MongoDB, Docker, and Git. Link `folio` to `https://github.com/Rapeter/folio` and describe it as an open-source, local-first AI investment research workbench with deep research, evidence-backed theses, portfolio-risk analysis, watchlists, and a Pi Agent copilot. Include only these two stats endpoints: `https://github-readme-stats.vercel.app/api?username=Rapeter` and `https://github-readme-stats.vercel.app/api/top-langs/?username=Rapeter`. Link the existing LinkedIn profile and use `mailto:kaizhongw@student.unimelb.edu.au`.

- [ ] **Step 4: Re-run the structural test**

Run the Step 1 script. Expected: success with no missing markers and no prohibited widgets.

- [ ] **Step 5: Validate Markdown whitespace and required outgoing URLs**

Run `git diff --check`, then verify that `https://github.com/Rapeter/folio`, both GitHub Readme Stats URLs, `https://www.linkedin.com/in/kaizhong-wang-9410b0288`, and `mailto:kaizhongw@student.unimelb.edu.au` occur in `README.md`. Expected: no whitespace errors and all URLs present.

- [ ] **Step 6: Commit the completed profile update**

Run `git add README.md` followed by `git commit -m "docs: optimize GitHub profile for AI agent roles"`.
