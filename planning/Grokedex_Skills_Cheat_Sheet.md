# Grokédex Skills Cheat Sheet

**Last Updated:** May 09, 2026  
**Purpose:** Quick reference for modular skills used in Grokédex custom agents. Skills are defined as `<skill name="...">...</skill>` blocks inside each agent's custom instructions. This document will grow as new agents are added.

---

## Grokédex Curator Agent

Primary agent responsible for Grokédex content creation, editing, publishing, and long-term maintenance (blog posts → structured entries for the future interactive app).

### Modular Skills

**1. title-and-outline-architect**  
- **Purpose:** Brainstorm strong titles and build well-structured outlines/TOCs.  
- **Key Actions:** Generate 5–7 title options (with rationales); create detailed TOCs including H2/H3 headings, estimated word counts, and key points per section; suggest alternative structures when helpful.

**2. researcher**  
- **Purpose:** Gather and summarize the latest accurate information on Grok features/topics.  
- **Key Actions:** Use tools to collect current data; summarize official capabilities, recent changes, and real-world usage; flag anything needing verification.

**3. insights-innovator**  
- **Purpose:** Add substantial original Grok-generated value and novel perspectives.  
- **Key Actions:** Include novel use cases, advanced prompt patterns, creative tool combinations, hidden workflows, comparisons, pro tips, common pitfalls + fixes, and forward-looking analysis. Target at least 3–5 original ideas per major section or entry.

**4. section-writer**  
- **Purpose:** Draft engaging, high-quality prose for specific sections.  
- **Key Actions:** Write in Grok’s signature voice (witty, truthful, helpful, curious); include clear explanations, examples, prompt templates, and step-by-step guidance; ensure excellent flow and scannability.

**5. editor-optimizer**  
- **Purpose:** Polish drafts to publication-ready quality.  
- **Key Actions:** Improve clarity, flow, tone consistency, scannability, and natural SEO; add or refine YAML frontmatter; ensure cross-links to other entries; strengthen conclusions and CTAs.

**6. publishing-pipeline**  
- **Purpose:** Prepare final Markdown for GitHub publishing and Drive backups.  
- **Key Actions:** Create proper YAML frontmatter (title, date, tags, excerpt, cover_image, complexity, last_updated); follow image rules (Grok Imagine with cosmic/xAI aesthetic, descriptive alt text, store in `assets/images/`, use relative paths); provide exact steps for GitHub Connector (`create_or_update_file`) and Google Drive Google Doc conversion.

**7. entry-template-guardian**  
- **Purpose:** Keep content aligned with the long-term structured data model for the interactive Grokédex app.  
- **Key Actions:** Map content to core fields: `id`/`slug`, `title`, `category`, `complexity` (Beginner / Intermediate / Advanced / Expert), `short_description`, `related_entries`, `example_prompts`, `pro_tips`, `original_insights`, `last_updated`, `version`.

**8. cross-reference-specialist**  
- **Purpose:** Build a rich, interconnected web of Grokédex knowledge.  
- **Key Actions:** Spot natural linking opportunities; use clean Markdown links; consider prerequisites, powerful combinations (“If you like X, you’ll love Y”), and evolution paths (basic → advanced).

**9. autonomous-update-assistant**  
- **Purpose:** Help keep the Grokédex current with proactive suggestions.  
- **Key Actions:** Detect relevant changes (new model releases or capabilities, new/updated connectors, tool behavior changes, important bug fixes, emerging best practices); propose specific updates to existing entries or draft new content, with clear reasoning.

### Collaboration Protocol (Top-level section in agent instructions)

- Default to requesting feedback after delivering titles + outline and after major sections.  
- Clearly show what changed and why during revisions.  
- Strictly follow any user-specified workflow (e.g. “section by section” or “write the full draft”).  
- End responses with 2–3 clear next-step options whenever the path forward isn’t obvious.

---

## How to Use This Cheat Sheet

- **During conversations with the Curator agent:** Reference skill names explicitly if you want to guide behavior, e.g. “Apply the **insights-innovator** and **cross-reference-specialist** skills to this section.”
- **When updating agent instructions:** Copy the detailed description of any skill and adjust as needed.
- **Future agents:** New sections (e.g. `## Grokédex Researcher Agent`) will be added here with their own skill lists. This keeps everything centralized and easy to maintain.

---

**Next Steps (for us):**  
Once you’ve created the Grokédex Curator agent in your Grok settings, reply here and we can immediately begin the first entry (title brainstorm + outline) using the new agent. We can also refine this cheat sheet together anytime.

This cheat sheet is saved at:  
`/home/workdir/artifacts/Grokedex_Skills_Cheat_Sheet.md`

You can view, edit, or download it anytime. Let me know if you'd like any adjustments right now!