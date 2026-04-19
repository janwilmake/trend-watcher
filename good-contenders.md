# Good Contenders
*Trends with low competition, specific enough to rank for, high informational intent.*
*Last updated: 2026-04-19*

---

## 1. Multi-Agent Swarm Orchestration with Claude Code — Practical Patterns

**Why it's trending:** Claude Code's leaked 512k-line source revealed advanced "swarm" orchestration features. Steve Yegge's "Gas Town" platform orchestrates Claude Code swarms. n8n's April 2026 blog calls multi-agent orchestration the defining question of 2026. Microsoft's Copilot Studio just shipped multi-agent GA. Cursor 3 launched its Agents Window on April 2 with parallel agents at its core. The concept of "orchestrator + worker" agent patterns is heating up fast.

**Suggested blog angle:** *"Claude Code swarm patterns: how to orchestrate multiple AI agents without losing your mind"* or *"Practical multi-agent patterns for solo developers in 2026."* Focus on concrete patterns (orchestrator-worker, sequential agents, parallel agents) with code examples — not the enterprise governance angle.

**Competition notes:**
- "Multi-agent orchestration" broadly: HIGH competition (Microsoft, n8n, GetStream.io, Domo, Elementum.ai — all April 2026 posts).
- "Claude Code swarm" / "Claude Code multi-agent": extremely fresh. Steve Yegge's Medium piece, one substack newsletter, no dedicated tutorial ranking.
- "Multi-agent patterns for solo developers": very low competition. Enterprise content dominates, indie developer content is sparse.
- Intent: strongly informational/how-to. Developer audience.
- Narrow enough to rank. A 2,000-word tutorial with diagrams and code snippets from a developer blog could hit page 1 within 2–3 weeks on the specific phrase.

---

## 2. Running Local LLMs with Ollama + MLX on Apple Silicon — A Developer's Setup Guide

**Why it's trending:** Ollama 0.19 (released March 30, 2026) switched to Apple's MLX backend on Apple Silicon, delivering ~1.6× faster prefill and ~2× faster generation on M-series chips. Covered by MacRumors, 9to5Mac, AppleInsider. Product Hunt ranked Ollama v0.19 #8 in April. The update specifically benefits users running Claude Code, OpenClaw, and coding agents locally. Apple Silicon Mac owners who were using local LLMs for coding agents suddenly have a meaningfully different experience.

**Suggested blog angle:** *"Setting up Claude Code with a local Ollama MLX backend on Apple Silicon (M2/M3/M4 guide)"* or *"How fast is Ollama 0.19 with MLX for coding agents? My M3 Max benchmarks."* Focus on the practical setup: which models work, what settings to use, how to connect coding agents (Claude Code, OpenClaw) to the local endpoint, what the real-world latency feels like for day-to-day coding.

**Competition notes:**
- News articles (MacRumors, 9to5Mac, AppleInsider): high-level, no hands-on setup guide.
- DEV Community (Apr 7): discusses local AI stack broadly, Ollama MLX mentioned but not a dedicated guide.
- Medium (Ollama 0.19 post): tech news summary, not a setup guide.
- No hands-on developer guide connecting Ollama 0.19 MLX specifically to Claude Code or OpenClaw exists yet.
- Search intent: strongly how-to / informational. Mac developer audience.
- Low competition on the specific "Ollama MLX Claude Code setup" angle. Good shot at page 1 for long-tail phrases within 2–3 weeks.
- **Note:** Preview is limited to Qwen3.5-35B-A3B for now (32GB+ RAM required). Scope the post to users who meet this requirement.

---

## 3. Reviewing AI-Generated Pull Requests — A Senior Engineer's Checklist

**Why it's trending:** An April 2026 survey shows 84% of developers use AI coding tools daily, but only 29% trust what they ship in production. A viral Medium post (April 6, 2026, 19 claps) from a staff engineer details the exact checks he runs on every AI-generated PR before it touches production. Reddit r/vibecoding is full of devs asking how to manage AI output quality. This "trust gap" is the defining pain point for engineering teams in 2026: agents are fast, but no one has a standardized way to validate their output.

**Suggested blog angle:** *"The AI-generated PR review checklist: 7 things senior engineers check before merging agent code"* — a practical, developer-oriented guide with specific checklist items (cache invalidation, database query plans, resource assumptions, failure coverage, blast radius). Real examples, opinionated, written from a production engineering perspective. Alternative angle: *"How to review code when 80% of it wasn't written by a human."*

**Competition notes:**
- Medium post (Clean Code Journal, Apr 6): covers "5 patterns" in a personal narrative format — good but short (5 min read), no dedicated SEO, paywalled on Stackademic.
- Vibe coding security checklist (good-contenders #3 above): focuses on *security vulnerabilities*; this entry focuses on *production reliability and operational correctness* — different, complementary angle.
- No dedicated standalone checklist post exists on "how to review AI-generated PRs" from a senior/staff engineer perspective.
- Checkmarx and Faros.ai cover AI PR review from a *tooling* angle (buy our product). No developer-first checklist post.
- Search intent: informational + task-oriented. Strong developer audience.
- Low competition on the specific senior-engineer / operational-correctness angle. High shareability on LinkedIn and Hacker News.
- Ranking potential: good within 2–3 weeks on long-tail phrases like "how to review AI generated code pull request" or "AI agent PR review checklist."

---

---

## 4. Vercel Workflows GA — Building Durable AI Agents with `"use workflow"` + `"use step"`

**Why it's trending:** Vercel launched **Workflows** as generally available on April 16–17, 2026. Workflows is a durable execution framework built into the Vercel platform: developers add `"use workflow"` and `"use step"` TypeScript directives to turn ordinary async functions into durable, resumable, observable workflows — no separate queue infrastructure, state databases, or orchestration services required. AI SDK v7 ships alongside it with a `WorkflowAgent` class that deeply integrates durable execution with tool calling. Since the October 2025 beta, Workflows has processed 100M+ runs and 500M+ steps across 1,500+ customers, with 200K+ npm downloads/week. The Python SDK just entered public beta. For AI agent developers, the value proposition is concrete: agents that need to pause for human approval, survive server restarts, stream output across reconnects, or pass 2GB of image/video data between steps can now do so with two directive annotations. Vercel Day (April 17) spotlighted Workflows prominently. The open-source Workflow SDK supports self-hosted deployments via community "Worlds" adapters (MongoDB, Redis, Cloudflare).

**Suggested blog angle:** *"I rewrote my flaky AI agent with Vercel Workflows in 30 lines — here's what changed"* — a practical developer tutorial covering: the "serverless mayfly" problem (why LLM agents keep timing out or losing state mid-task), how `"use workflow"` and `"use step"` work mechanically (event log replay, deterministic step isolation), a real before/after (an agent that calls 3 external APIs + waits for user approval → from broken to production-ready), how `DurableAgent` from `@workflow/ai` differs from a raw AI SDK `generateText()` loop, how to use `sleep()` to pause for days without burning compute, and current limitations (TypeScript only for now; Python SDK in beta). Alternative angle: *"Vercel Workflows vs Temporal for AI agents: when does each one make sense?"*

**Competition notes:**
- Vercel official blog (vercel.com/blog/a-new-programming-model-for-durable-execution, Apr 16): launch post — authoritative but overview-level, not a step-by-step tutorial.
- Vercel Knowledge Base (vercel.com/kb/guide/building-a-slack-agent-with-durable-workflows): Vercel's own Slack agent guide — specific to Slack, written by Vercel engineers (not independent). Detailed but official.
- useworkflow.dev/docs/ai: official SDK docs, not a narrative tutorial.
- Vercel Academy (vercel.com/academy): official structured course — authoritative, but formal course format.
- KuCoin Flash (Apr 17): crypto news brief summarizing the launch — not a developer guide.
- Temporal blog (Jan 2026): "Building durable agents with Temporal and AI SDK by Vercel" — covers Temporal as an alternative, predates GA.
- YouTube (Jan 2026, AI Engineer channel, Peter Wielander): Workflow DevKit intro video — 7.3K views, covers beta version from 3 months ago, not GA.
- Callstack blog (May 2025): "Building AI Agent Workflows With Vercel's AI SDK" — covers older AI SDK patterns without Workflow DevKit.
- **No independent developer tutorial for Vercel Workflows GA** (the `"use workflow"` + `"use step"` directive model) exists outside Vercel's own docs and KB articles.
- Search intent: informational + how-to. Developer audience (Next.js/TypeScript developers building AI agents, indie hackers who have hit the serverless timeout wall, teams moving agents from prototype to production).
- **Very low competition** on "Vercel Workflows tutorial," "use workflow use step guide," "durable AI agents Vercel," or "Vercel Workflow SDK getting started." The only competition is Vercel's own authoritative content.
- Ranking potential: strong on specific phrases. Against Vercel's own content, an independent developer's "I tried it and here's what I ran into" post differentiates on trust (third-party perspective) and specificity (real project pain points, gotchas, vs. official happy-path documentation).
- **Window: 3–5 days.** This is a GA launch of a product in beta since October 2025 — the community of early adopters is already large, which means independent tutorials and comparison posts will appear faster than for a completely new product. The specific "AI agent durability" angle — connecting `"use workflow"` directly to the LLM timeout / state-loss problem — is currently unclaimed by any independent blogger.

---

## 5. Claude Opus 4.7 Task Budgets API — Controlling Token Spend in Production Agent Loops

**Why it's trending:** Claude Opus 4.7 (launched April 16, 2026) ships with two developer-facing features that are genuinely new and underexplored: (1) **Task budgets** (public beta on the API) — a `task_budget: { type: "tokens", total: N }` parameter that shows Claude a running countdown of available tokens so it can prioritize work and finish tasks gracefully as the budget is consumed, rather than truncating mid-thought; and (2) the **`xhigh` effort level** — a new setting between `high` and `max` that gives more granular control over the reasoning/latency tradeoff (Claude Code now defaults to `xhigh`). Combined with the new `/ultrareview` slash command (a dedicated code review session that reads changes and flags bugs/design issues a senior reviewer would catch), these three features compose a practical "production agent quality control" toolkit that hasn't been documented from a real-world developer perspective. The key context: Opus 4.7's new tokenizer means the same prompts use up to 35% more output tokens — meaning production teams need to immediately audit and recalibrate their existing cost models and agent loops.

**Suggested blog angle:** *"Claude Opus 4.7 in production: how to use task budgets, xhigh effort, and /ultrareview without going broke"* — a practical developer guide covering: what the 35% tokenizer change actually means for your monthly bill (show the math), how to set a `task_budget` via the API and what Claude actually does differently when it sees the countdown, when to use `xhigh` vs `high` effort (the BrowseComp regression means research-heavy agents should stay on `high`), what `/ultrareview` actually surfaces compared to `/review` (design-level issues vs. syntax), the `/claude-api migrate` skill for upgrading existing code to Opus 4.7, and a cost optimization checklist for teams migrating from 4.6.

**Competition notes:**
- Anthropic official blog (anthropic.com/news/claude-opus-4-7, Apr 16): launch announcement — covers features at overview level, links to docs.
- platform.claude.com/docs/en/about-claude/models/whats-new-claude-4-7: official docs — comprehensive technical reference but not a developer narrative.
- platform.claude.com/docs/en/build-with-claude/task-budgets: official task budgets doc — complete API reference but no real-world cost analysis.
- Vellum AI (vellum.ai/blog/claude-opus-4-7-benchmarks-explained, Apr 16): covers benchmarks, mentions `xhigh` in FAQ but no hands-on task budget example.
- Mashable (Apr 16): general model launch coverage, consumer audience.
- AWS Blog (Apr 16): Bedrock-specific, enterprise focus.
- tosea.ai (Apr 16): brief "complete guide" — high-level overview, mentions task budgets in one sentence.
- Karo Zieminski Substack (Apr 17): "role-mapped" overview (best non-Anthropic review found) — covers `/ultrareview` and effort level in context, but no hands-on API task budget code walkthrough or cost analysis.
- YouTube (DIY Smart Code, Apr 16): "Opus 4.7 + /ultrareview Full Breakdown" — video format only, 3.5 min.
- **No independent written developer guide** covers task budgets with real code examples and production cost analysis.
- Search intent: informational + how-to. Developer/architect audience (teams migrating production Claude agents from 4.6 → 4.7, indie developers who run agent loops at scale and care about token cost).
- **Low-to-moderate competition** on "Claude Opus 4.7 task budgets guide," "xhigh effort level claude," or "claude opus 4.7 production migration." The general "Opus 4.7 review" space is crowded but the production API / cost control angle is not.
- Ranking potential: moderate-strong on long-tail phrases like "claude opus 4.7 task budget example" or "claude 4.7 xhigh effort when to use." The specific cost-impact analysis framing (35% tokenizer change → your bill) is a hook that drives shares among CTOs and senior developers.
- **Window: 5–7 days.** The launch is fresh. DataCamp-style comprehensive guides will cover Opus 4.7 broadly within the week but are unlikely to go deep on API-level task budget configuration and cost modeling. The production-engineer angle has a longer window than product launch coverage.

---

## 6. Figma for Agents — Writing Your Team's First Design System Skill

**Why it's trending:** Figma opened the canvas to AI agents on April 10, 2026 via the new `use_figma` MCP tool — and relaunched as "Figma for Agents" on Product Hunt on April 14 (#1 Product of the Day, 528 upvotes). The core problem it solves is the "design system blindness" of AI agents: Claude Code, Codex, and Cursor generate UI that looks technically correct but ignores the actual component library, variables, and spacing tokens a team has spent months building. The `use_figma` tool reads your live Figma file; **Skills** (markdown files encoding your team's design conventions) guide how agents behave in that canvas — which components to reach for, how to handle variants, what naming conventions to follow. Skills are cross-agent (Claude Code, Cursor, Copilot, Codex all read the same SKILL.md). Community members from Uber, Edenspiekermann, and others published 9 example skills at launch. Free in open beta. The Figma blog published "Agents, Meet the Figma Canvas" on April 10, and Figma's own YouTube tutorial (6.6K views, 2 days old) covers the setup — but neither addresses the specific workflow of *authoring* a custom skill for an existing design system.

**Suggested blog angle:** *"I wrote a Figma skill for our design system — here's what 30 minutes of effort actually bought us"* — a real-team walkthrough covering: what a skill file looks like (SKILL.md structure: name, description, instructions with concrete examples), the three things every design team should encode first (which component to reach for vs. create from scratch, how to apply color tokens vs. hardcoding, spacing grid rules), a before/after screenshot comparison (agent output with vs. without the skill active), how to test the skill against a real use case in Claude Code (connect Figma MCP, point at your file, prompt the agent), and the 2–3 gotchas Figma's own docs underplay (the `figma-use` base skill must load before `use_figma` calls; agents still can't handle FigJam files; custom fonts require a workaround). Alternative angle: *"Figma Skills vs. Claude Code CLAUDE.md: two ways to teach your agent your design system."*

**Competition notes:**
- Figma official blog (figma.com/blog/the-figma-canvas-is-now-open-to-agents, Apr 10): launch post — explains the concept well but no practical skill-authoring guide.
- Figma YouTube tutorial (Apr 7/16): 6.6K views — covers MCP setup (Claude Code, Cursor, Codex) but not skill authoring.
- Muzli Blog (March 24): overview of what changed, mentions Skills — no workflow guide.
- UX Collective / Christine Vallaure (Apr 6): "Agentic AI, design systems & Figma: a practical guide" — philosophical, designer-audience, no skill-authoring tutorial.
- Medium / Mohit Aggarwal (Apr 9): "10 Figma Claude Skills for PMs" — covers pre-built skills to use, not how to write your own from scratch.
- Medium / Nurkhon (Apr 16): "Your Figma Library Is Invisible to AI Agents" — frames the problem well, no solution walkthrough.
- vectosolve.com (Apr 14): Figma Weave + MCP pipeline tutorial — niche (image-to-SVG), mentions skills briefly.
- Reddit r/FigmaDesign (Apr 10): community thread announcing the feature, no tutorials.
- **No independent written tutorial for authoring a custom Figma skill from scratch** (the SKILL.md authoring workflow, connecting it to your team's actual component library, testing it via Claude Code MCP) exists on any blog as of April 18.
- Search intent: informational + how-to. Audience: design engineers, frontend developers who own the design system connection in their team, PMs who manage Figma workflows, and designers curious about whether agent-generated designs can finally respect their work.
- **Very low competition** on "how to write a Figma skill," "Figma skill SKILL.md tutorial," "Figma for Agents design system setup," or "use_figma skill authoring guide."
- Ranking potential: strong on product-specific phrases. Figma's own blog ranks for "Figma for agents" but not for authoring-level tutorials. The "before/after screenshot with vs. without skill" angle is highly shareable in design/developer Twitter and r/FigmaDesign.
- **Window: 3–5 days.** The April 14 Product Hunt launch is 4 days old; the concept is spreading through design newsletters (Sidebar, Dense Discovery, Designer News). YouTube tutorial makers (TD Sunshine channel, DesignWithArash) are publishing adjacent Figma AI content but haven't yet covered skill authoring. The "write your first skill" tutorial window is open but will close once Figma publishes an official tutorial or a high-authority design YouTuber covers it.

---

## 7. JetBrains Air — Practical Comparison: Air vs. Cursor 3 vs. Windsurf 2.0 for Multi-Agent Workflows

**Why it's trending:** JetBrains entered the Agentic Development Environment (ADE) category in March 2026 with Air (public preview, free for macOS). Air is a standalone desktop app — not a plugin or IDE extension — that runs Codex, Claude Agent, Gemini CLI, and Junie concurrently in Git worktrees or Docker containers, with a task-card UI for managing concurrent agent work and a code-aware diff review panel. It sits in direct comparison with Cursor 3's Agents Window (launched April 2) and Windsurf 2.0's Agent Command Center (launched April 16). All three shipped parallel-agent management within six weeks of each other, creating a natural "which one should I use?" search query that is not yet authoritatively answered. The category name "Agentic Development Environment" is gaining traction (Thoughtworks April 2026 macro trends post, JetBrains survey showing 85% AI tool adoption). Air has 74 HN upvotes (4 months ago for the alpha) and the March 24 public preview announcement.

**Suggested blog angle:** *"Air vs. Cursor 3 vs. Windsurf 2.0: I ran the same three tasks in each parallel-agent system — here's what actually worked"* — a practical developer comparison covering: the core architecture difference (Air: standalone ADE for agent orchestration, your IDE stays separate; Cursor 3: multi-agent inside your existing editor; Windsurf 2.0: IDE + cloud Devin delegation), how each handles task isolation (Air: Git worktrees or Docker; Cursor 3: background worktrees; Windsurf 2.0: local Cascade + cloud Devin), the review workflow in each (Air: code-aware diff panel with line-commenting; Cursor 3: diff in editor; Windsurf 2.0: PR review in Spaces), real gotchas for each (Air: macOS only, no Claude Agent without JetBrains AI subscription; Cursor 3: agents hang when window loses focus; Windsurf 2.0: Devin credits cost extra), and a clear recommendation matrix (solo dev vs. team, macOS vs. cross-platform, local-first vs. cloud delegation preference). Alternative angle: *"The rise of the Agentic Development Environment: why your coding agent needs a control plane, not a chat window."*

**Competition notes:**
- Medium / Saeed Zarinfam (Mar 30): "JetBrains Air: The Future of Multi-Agent Coding, or Just More AI Noise?" — paywalled, 7 claps, covers Air at overview level but no hands-on comparison vs. Cursor or Windsurf.
- JetBrains blog (Apr 9): "My Journey to Agent-First Development With Air" — testimonial-style from a JetBrains engineer. Official, but not an independent comparison.
- JetBrains blog (Mar 24): Air launch post — authoritative but marketing-tone overview, not hands-on workflow.
- Augment Code (Apr 12): "JetBrains Central vs Intent" — compares two enterprise products, mentions Air, not a hands-on Air workflow guide.
- Reddit r/Jetbrains: "Thoughts on JetBrains' new agentic IDE, Air" — critical user thread ("feels half-baked"), no tutorial.
- HN thread (74 points, 4 months ago): developer reactions, no dedicated tutorial.
- YouTube: JetBrains official promo video + a few shorts — no independent hands-on comparison with Cursor or Windsurf.
- **No independent developer-authored comparison of Air vs. Cursor 3 vs. Windsurf 2.0** exists yet. The category comparison search — "JetBrains Air vs Cursor" or "ADE comparison 2026" — returns no authoritative results.
- Search intent: informational + decision-support. Developer audience (devs who've heard of all three products from separate launch announcements and want one comparison to inform which they adopt).
- **Low competition** on "JetBrains Air review," "JetBrains Air vs Cursor," "agentic development environment comparison 2026," or "Air IDE review." The only substantive content is Figma's own blog, official JetBrains posts, and a paywalled Medium article.
- Ranking potential: good on long-tail comparison phrases. The "I actually ran the same task in all three" framing differentiates from official launch posts. Developer Twitter and HN love head-to-head tool comparisons with real benchmark tasks.
- **Window: 7–14 days.** Air has been in public preview since March 24 (25 days old) but is still macOS-only and underexposed. Windsurf 2.0 launched April 16 (2 days ago) and adds fresh search demand for the comparison angle. DataCamp and similar high-authority blogs have not yet published a three-way comparison. The window is wider than most product-launch opportunities because Air's preview phase has been slow to attract English-language independent coverage.

---

## 8. Fathom 3.0 + Official MCP Server — The "Meeting Memory" Workflow for Developer Teams

**Why it's trending:** Fathom launched version 3.0 on April 15, 2026 (#1 Product Hunt of the Day, 581 upvotes, 177 comments, 5.0 rating from 298 reviews) — the biggest update since Fathom 2.0. The headline feature is bot-free capture (record meetings without a bot joining, with full speaker diarization), but the under-covered developer story is the simultaneous launch of Fathom's **official MCP server** (April 17, registered on PulseMCP). This MCP server connects Claude, Claude Code, ChatGPT, and Cursor directly to your Fathom meeting history — enabling queries like "What did the client say about the database migration last week?" without leaving your IDE, or "Summarize all customer objections across this month's sales calls." Fathom 3.0 also ships account-wide Ask Fathom (previously single-meeting only), Claude and ChatGPT integrations via the public API, and a live summary scratchpad during meetings. For developer teams who use Fathom to record standups, architecture calls, and customer interviews, the combination of bot-free capture + the official MCP server creates a "meeting memory" layer that feeds directly into coding agents — but the workflow is completely undocumented from a practitioner standpoint.

**Suggested blog angle:** *"I connected Fathom 3.0 to Claude Code — my meetings are now part of my development context"* — a developer-focused workflow guide covering: why meeting knowledge is usually lost for engineering decisions (the "we discussed this six weeks ago" problem), how to connect the official Fathom MCP server to Claude Desktop (`claude mcp add fathom -- npx mcp-remote@latest https://api.fathom.ai/mcp`) and Claude Code in one command, three concrete use cases for developer teams (1: query last week's architecture call before writing a spec; 2: ask Claude to extract all open action items from standup transcripts and create a task list; 3: pull client feedback from sales calls into a feature brief), the bot-free capture workflow (which mode to use: transcript-only vs. audio capture vs. video bot), the speaker diarization quality difference in practice, and what the new account-wide Ask Fathom means for engineering team leads. Alternative angle: *"Fathom 3.0 review: the meeting notetaker that finally speaks developer."*

**Competition notes:**
- Fathom official MCP docs (developers.fathom.ai/mcp-docs/claude): step-by-step connection reference — not a workflow narrative or use-case tutorial.
- Truto blog (Mar 10, 2026): "Best MCP Server for Fathom" — covers building an MCP with Truto's managed infrastructure, pre-dates the official MCP server, focused on multi-user enterprise routing (different audience and angle).
- agencyenterprise/fathom-mcp-server (GitHub): community-built MCP repo — code only, no tutorial post.
- PulseMCP (Apr 17): listing entry — index only, no tutorial.
- TechCrunch (Apr 15): "Fathom adds a bot-less meeting mode" — covers the launch, no developer workflow guide.
- BusinessWire (Apr 15): launch press release — product marketing only.
- Progressive Robot (Apr 14): "What Is Fathom AI? 7 Critical Facts" — general product explainer, no MCP or developer workflow content.
- YouTube (Mar 30): Fathom AI Tutorial 2026 (The Business Dive) — covers general Fathom setup, predates 3.0 and the official MCP.
- composio.dev (Mar 9): Fathom MCP with OpenClaw via Composio layer — different architecture (managed connector), not the direct official MCP.
- **No independent developer workflow post** covers connecting the official Fathom MCP to Claude Code or using meeting context in an engineering workflow as of April 19, 2026.
- Search intent: informational + how-to. Audience: individual developers and engineering team leads who use Fathom for meeting notes and also use Claude/Claude Code for development work.
- **Low competition** on "Fathom MCP server tutorial," "Fathom 3.0 Claude Code integration," "connect Fathom to Claude," or "meeting intelligence developer workflow." The official docs cover the setup steps but no one has written the "here's the real workflow and why it matters" post.
- Ranking potential: moderate-strong on long-tail phrases. The Fathom product has 500K+ users; a meaningful fraction are developers who also use Claude. Strong shareability on developer Twitter/HN as an "obvious in hindsight" workflow post.
- **Window: 4–7 days.** The official MCP server launched April 17 (2 days ago). The Fathom 3.0 launch momentum is still active (product newsletter cycle). Independent developers who use both Fathom and Claude will start publishing "I tried this" posts as they discover the connection. The window is wider than a pure product launch because the integration angle is non-obvious — most Fathom users don't think of their meetings as developer context, and most Claude Code users don't know Fathom has a native MCP. The first person to write the "this is the workflow" narrative owns the search slot for this specific combination.
EOF; echo "
__CWD_TRACK__$(pwd)"