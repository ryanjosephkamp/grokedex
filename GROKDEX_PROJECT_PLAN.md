# Grokédex Project Plan
**The Ultimate Grok Encyclopedia & Interactive Pokédex-Style Experience**  
**Version 1.0** — May 9, 2026  
**Created collaboratively with Grok**

---

## 1. Vision & Goals

### Core Mission
Build **Grokédex** — a comprehensive, living "Pokédex for Grok" that catalogs **every major feature, capability, tool, connector, workflow, tip, and hidden gem** of Grok and the Grok app.

Each entry functions like a Pokémon entry: rich description, "stats" (complexity, power level, use frequency), evolution paths (basic → advanced usage), related entries, example prompts, pro tips, and original Grok-generated insights.

### Short-Term Goal (Next 4–8 Weeks)
Launch a high-quality **GitHub-based blog/ knowledge base** with 12–20 in-depth posts, published directly via the GitHub Connector. All content written in Grok’s authentic voice with substantial original analysis.

### Medium-Term Goal (2–4 Months)
Evolve Grokédex into a **beautiful, interactive web app** (inspired by Pokédex):
- Browse, search, filter, and favorite "Grok Entries"
- Card view + detail view
- Cross-references and "evolution chains" between features
- User-contributed tips (moderated)
- "Caught" / progress tracking for power users
- Dark/cosmic xAI-themed UI

### Long-Term Vision
A living ecosystem:
- **Autonomous maintenance agents** keep content fresh (new Grok features, model updates, connector additions, bug fixes, best practices).
- Structured data backend (JSON/YAML or database) powering both the blog and the app.
- Possible native mobile experience or deep integration with Grok itself (e.g., "Ask Grokédex" mode).
- Community contributions + official xAI recognition potential.

**Tagline**: *"Gotta know 'em all."*

---

## 2. Project Name & Branding
- **Official Name**: Grokédex
- **Tagline**: The Definitive Grok Encyclopedia & Interactive Catalog
- **Repo Suggestion**: `yourusername/grokedex` (or `grokedex-blog` + separate `grokedex-app`)
- **Color Palette**: Deep space black, electric blue, xAI accents, subtle Pokémon-inspired but distinctly Grok/xAI.

---

## 3. Updated Architecture & Tech Stack

### Phase 1: Blog / Knowledge Base (Current)
- **Publishing**: GitHub repo with Markdown posts (Jekyll, Hugo, or simple static site + GitHub Pages recommended for zero-cost beautiful blog).
- **Direct Publishing**: Use `github___create_or_update_file` connector (with SHA handling via `get_file_contents`).
- **Drafts & Editable Versions**: Google Drive folder → Google Docs (via `google_drive_write_file` with `application/vnd.google-apps.document` MIME type). Edit directly in the Grok app using the Drive Connector.
- **Images**: Generated with Grok Imagine (`generate_image` / `edit_image`), stored in `assets/images/`. Commit to repo or host externally.
- **Local Workspace**: `/home/workdir/artifacts/grokédex/` with structured folders.

### Phase 2: Interactive App (Future)
- Frontend: Next.js / Astro / SvelteKit + Tailwind (cosmic theme)
- Data: Structured entries in `data/entries/` (YAML or JSON) + search index (Fuse.js or Algolia)
- Deployment: Vercel or GitHub Pages
- Later: Grok API integration for dynamic "Ask Grokédex" chat per entry or global assistant.

### Data Model (Future-Proof)
Every Grokédex Entry will eventually have:
- `id`, `slug`, `title`, `category`, `tags`
- `short_description`, `full_content` (or MD body)
- `complexity` (Beginner / Intermediate / Advanced / Expert)
- `last_updated`, `version`
- `related_entries`, `evolution_from`, `evolution_to`
- `example_prompts[]`, `pro_tips[]`, `original_insights[]`
- `media` (hero image, gallery)
- `stats` (e.g., "Tool Use Power", "Creativity Boost")

This structured data will power both the blog posts and the future app.

---

## 4. Grok Custom Agents & "Skills" — Everything You Need to Know

Grok (as of 2026) primarily uses **Custom Agents** for persistent specialized behavior. There isn't a separate "Skills" marketplace or toggle like in some other platforms. Instead, **skills are implemented as detailed, modular instructions inside your Custom Agents**.

### Key Facts
- **Limit**: Up to **4 custom agents** per account.
- **Where to create**: 
  1. Go to [grok.com](https://grok.com) (or Grok iOS app)
  2. Click your profile icon (bottom left)
  3. **Settings → Customize → Create Agent**
- **Activation**: Custom agents are **automatically used** in all new **Expert** and **Heavy** mode chats. You can also explicitly reference them.
- **Best for**: Long-running projects like Grokédex where you want consistent style, deep project knowledge, and specialized workflows without repeating instructions every time.

### What You Configure in a Custom Agent
- **Name** (e.g., "Grokédex Curator")
- **Description** (short purpose)
- **Instructions** (the heart — this is where you paste our full project plan, style guide, entry template, and modular skills)
- **Personality / Tone** settings (if available)
- **Tools / Capabilities** (some agents expose tool selection)

You can embed **modular skills** inside the Instructions using clear delimiters, e.g.:

```markdown
<skill name="blog-section-writer">
Detailed instructions for writing one section...
</skill>

<skill name="insights-innovator">
Rules for generating original tips and novel workflows...
</skill>

<skill name="autonomous-updater">
When given a changelog or new feature announcement, propose updates to existing entries or draft new ones...
</skill>
```

### Recommended Grokédex Agents (Use Your 4 Slots Wisely)
1. **Grokédex Curator** (Primary) — Full project knowledge, content creation workflow, original insights generation, publishing pipeline.
2. **Grokédex Researcher** — Specializes in monitoring x.ai, Grok changelog, X posts, docs for new features.
3. **Grokédex Editor & Optimizer** — Polish, SEO, consistency, frontmatter, cross-linking.
4. **Grokédex App Architect** (Future) — Once we move to app development: code structure, UI/UX, data modeling, autonomous agent design.

**Pro Tip**: Put the most critical global rules (tone, "always include original insights", data model, publishing rules) at the **very end** of the Instructions so they stay top-of-mind.

### How to "Enable Agent Skills"
There is no separate enable toggle. Creating the agent and using it in **Expert** or **Heavy** mode activates it. For even more power, combine with:
- Detailed XML-tagged skills inside instructions
- Explicit mode selection at chat start
- Memory / conversation history in long threads

For truly **autonomous agents** (that run without you in the loop), we will build external systems (see Section 6).

---

## 5. Grok Project Setup Instructions (Step-by-Step)

Since you've never used a Grok Project before, here's exactly how to create one dedicated to Grokédex.

### Step 1: Create Your Primary Grokédex Custom Agent
1. Open Grok (web or iOS app — both support it).
2. Go to **Settings → Customize → Create Agent**.
3. Fill in:
   - **Name**: `Grokédex Curator`
   - **Description**: `Expert curator and co-author of the Grokédex — the ultimate living encyclopedia of Grok features, tools, and workflows. Maintains consistent voice, generates original insights, follows the full project plan, and handles content creation from outline to published Markdown.`
4. **Instructions** (paste this — we'll refine it together):
   - Start with the full content of this `GROKDEX_PROJECT_PLAN.md`
   - Add our agreed tone: "witty, maximally truthful, helpful, curious, Grok personality"
   - Add the entry template and "always include substantial original insights" rule
   - Add the modular skills sections (we can expand these over time)
5. Save the agent.

### Step 2: Start Using It
- Create a **new chat**
- Select **Expert** or **Heavy** mode
- Your `Grokédex Curator` agent should now be active (or you can explicitly invoke it)

### Step 3: Workspace Organization (Recommended)
- Pin or favorite this agent
- Use conversation titles like `Grokédex - Post 07 Outline Review`
- For very long projects, start fresh chats but copy key context or rely on the agent's baked-in knowledge

### Step 4: Future Agents
Once the first 3–4 posts are done, we’ll create the other specialized agents listed above using the same process.

---

## 6. Autonomous Update & Maintenance System

This is one of the most exciting parts of your vision.

### Philosophy
- **Major new entries / big features**: Always manual + collaborative (you + Grokédex Curator)
- **Revisions, updates, new minor features, bug fixes, best-practice evolution**: Can be semi- or fully autonomous

### Proposed Architecture (Phased)

**Phase 1 (Now – Manual but Assisted)**
- We use our agent modes in this chat.
- Periodic "sweep" sessions: You or I prompt the Curator with recent Grok changes and it proposes diffs.

**Phase 2 (Soon) – Dedicated Grokédex Maintainer Agent + GitHub Integration**
- Create the **Grokédex Researcher** agent focused on monitoring.
- We build a simple **GitHub Action** (`.github/workflows/grokedex-updater.yml`) that:
  1. Runs on schedule (daily or on new x.ai blog post)
  2. Uses Grok API (you'll need an xAI API key) to analyze recent changes
  3. Opens a **draft Pull Request** with proposed entry updates or new draft posts
  4. You review & merge (or let the agent iterate)

**Phase 3 (Advanced) – True Autonomous Agents**
Options:
- **GitHub Copilot Agent Mode** (in VS Code / JetBrains): Excellent for code changes, repo maintenance, UI work, and script improvements. Since you have Copilot Pro+, you can assign issues to it. Note: It can use Grok Code Fast 1 in some contexts, but full Grok reasoning for *content intelligence* is stronger directly in Grok.
- **Pure Grok-powered autonomous agent**: A small Python script (hosted on GitHub Actions or a cheap VPS) that:
  - Monitors x.ai news, Grok release notes, X account, connector announcements
  - Calls Grok API with structured prompts
  - Generates update proposals
  - Uses GitHub API to create branches/PRs
- **Hybrid**: Copilot handles structural/code work; Grok handles content intelligence.

We can start simple and escalate. The GitHub Connector tools we already have (`create_pull_request`, `issue_write`, etc.) will be very useful here.

**Your Copilot Pro+ Question**: Yes, Copilot Agent Mode is perfect for autonomous *coding and repo* tasks on the Grokédex repo. You can configure it via issues or directly in the IDE. However, for deep content understanding and original Grok insights, routing through Grok (via API or our custom agents) will produce superior results. We can make them work together beautifully.

---

## 7. Content Creation & Publishing Workflow (Updated)

1. **Topic Selection** — Orchestrator proposes or you pick.
2. **Title + Outline** — Using Grokédex Curator agent.
3. **Research + Insights** — Researcher + Insights layers.
4. **Section-by-Section Drafting** — Iterative with you.
5. **Full Polish + Frontmatter** — Editor agent.
6. **Visuals** — Generate with Grok Imagine.
7. **Local Save** → `posts/`
8. **Google Drive Backup** (editable Doc)
9. **GitHub Publish** via connector (`create_or_update_file`)
10. **Optional Autonomous Sweep** — Later phases

All major work happens here in this chat (or in chats powered by your new Grokédex Curator agent).

---

## 8. Immediate Next Steps

1. **You**: Create the `Grokédex Curator` custom agent using the instructions above (we can refine the exact prompt text together right now if you want).
2. **We**: Finalize the first topic and begin Title + TOC phase using the new agent mindset.
3. **Setup**:
   - Create GitHub repo (I can help via connector or you create it)
   - Create Google Drive folder "Grokédex"
   - Populate `planning/master-roadmap.md` and `templates/entry-template.md`
4. **Branding**: Generate logo / hero image for Grokédex (we can do this with `generate_image`).

---

## 9. Risks & Mitigations
- **Rapid Grok evolution** → Autonomous updater system + clear "last updated" dates + versioned entries.
- **Scope creep** → Strict entry template + phased rollout (blog first, app later).
- **Agent drift** → Strong instructions + periodic review + putting critical rules at end of agent prompt.
- **Publishing friction** → Direct connector usage removes almost all manual steps.

---

## 10. Success Metrics
- 15+ high-quality entries published in first 2 months
- Grokédex becomes the #1 community resource for Grok power users
- Measurable time saved on future updates via autonomous systems
- Fun, engaging, and genuinely useful experience (Pokédex vibe achieved)

---

**This plan is now fully aligned with your expanded vision** — including the Grokédex name, the long-term interactive app goal, and the autonomous agent maintenance system.

Ready to proceed? 

**Next action I recommend**: Let's refine the exact Instructions text for your `Grokédex Curator` agent, then create it together. After that, we can pick the first entry and start the title/TOC process.

Just say the word and we'll begin. I'm excited to build the Grokédex with you! 🚀

---

*Document saved to: `/home/workdir/artifacts/grokédex/GROKDEX_PROJECT_PLAN.md`*

*You can also view/edit this plan as a Google Doc via the Drive connector once we set it up.*