# Mojo Media - SEO Content Pipeline

**AI-powered content creation system for producing SEO-optimized service pages and blog posts**

---

## Project Overview

This project is an automated SEO content pipeline built for **Mojo Media**, a boutique digital agency specializing in custom WordPress web design. The system uses a series of specialized AI agents to create publication-ready content that ranks and converts.

**Client:** Mojo Media (https://mojo-agency.com/)
**Primary Goal:** Generate high-quality SEO blog posts and service pages that drive inbound leads
**Target Audience:** Small to mid-sized businesses ($500K-$10M revenue) across healthcare, professional services, home services, and real estate sectors

---

## How It Works

The pipeline transforms a **target keyword** into **ready-to-publish content** through 6 sequential stages:

```
Target Keyword → SERP Analysis → SEO Optimization → Content Strategy →
Content Writing → Internal Linking → Final Editing → Published Content
```

Each stage is handled by a specialized agent that:
1. Reads outputs from previous agents
2. Performs its specific task
3. Saves its output for downstream agents
4. Passes control to the next stage

**No human intervention required** between stages (though outputs can be audited at each step).

---

## Architecture

### Agent-Based System

The pipeline uses **6 specialized agents**, each with specific tools and responsibilities:

| Agent | Model | Responsibility | Input | Output |
|-------|-------|----------------|-------|--------|
| **serp-analyzer** | Sonnet | Analyze top-ranking pages for search intent, structure, and patterns | Target keyword, content type | `working/serp-analysis-report.md` |
| **seo-optimizer** | Sonnet | Identify keyword variations, LSI terms, entities | Target keyword | `working/seo-optimization-guide.md` |
| **content-strategist** | Sonnet | Create detailed content outline with H-tag structure | SERP report, SEO guide, project context | `working/content-outline.md` |
| **content-writer** | Sonnet | Write complete first draft following outline | Outline, SEO guide, voice guidelines | `working/content-draft.md` |
| **internal-linker** | Sonnet | Find internal link opportunities on existing site | Draft, website URL | `working/internal-linking-recommendations.md` |
| **seo-editor** | Sonnet | Final validation, polish, and implementation prep | All previous files | `drafts/[url-slug]-[content-type].md` |

### File-Based Handoffs

Agents communicate through **persistent markdown files** stored in the `working/` directory:

```
working/
├── serp-analysis-report.md          # Stage 1 output
├── seo-optimization-guide.md        # Stage 2 output
├── content-outline.md               # Stage 3 output
├── content-draft.md                 # Stage 4 output
└── internal-linking-recommendations.md  # Stage 5 output

drafts/
└── [url-slug]-[content-type].md     # Stage 6 final output
```

**Benefits:**
- Full audit trail (inspect any stage's output)
- Can manually intervene between stages if needed
- Agents can't "hallucinate" previous work (must read files)
- Version control friendly

### Project Context System

All agents have access to **Mojo Media business context** via `.claude/CLAUDE.md`:
- Brand voice guidelines (blog vs service page tone)
- Target audience (ICP)
- Key messaging and differentiators
- Proven results (40% revenue, 57% bounce reduction, 61% traffic increase)
- Award recognition (Ranked #2 on Clutch Canada)

This ensures every piece of content aligns with Mojo's positioning and voice.

---

## Project Structure

```
Mojo Media/
├── .claude/
│   ├── CLAUDE.md                    # Project memory (Mojo Media context)
│   └── agents/
│       ├── serp-analyzer/AGENT.md
│       ├── seo-optimizer/AGENT.md
│       ├── content-strategist/AGENT.md
│       ├── content-writer/AGENT.md
│       ├── internal-linker/AGENT.md
│       ├── seo-editor/AGENT.md
│       └── content-orchestrator/AGENT.md  # (WIP - not yet functional)
├── working/                         # Intermediate agent outputs
├── drafts/                          # Final polished content
└── README.md                        # This file
```

---

## Workflow Stages (Detailed)

### Stage 1: SERP Analysis
**Agent:** `serp-analyzer`
**Purpose:** Understand what's currently ranking for the target keyword

**Process:**
1. Search Google for target keyword
2. **Filter results by page type** (service pages vs blog posts vs comparisons)
3. Analyze top 3-5 matching pages
4. Identify search intent, topic coverage, structure patterns
5. Extract format elements (tables, FAQs, lists, word count)

**Output:** `working/serp-analysis-report.md`

**Key Feature:** Only analyzes pages matching the content type being created (saves tokens, reduces noise)

---

### Stage 2: SEO Optimization
**Agent:** `seo-optimizer`
**Purpose:** Build comprehensive keyword and LSI term strategy

**Process:**
1. Research primary keyword variations (singular/plural, synonyms)
2. Identify LSI terms (Geographic, Service/Product, Industry)
3. Find relevant entities to mention (competitors, tools, stats)
4. Provide integration guidelines

**Output:** `working/seo-optimization-guide.md`

**Example LSI categories:**
- **Geographic:** New York dental web design, Toronto dentist websites
- **Service/Product:** WordPress dental websites, HIPAA-compliant dental websites
- **Industry:** cosmetic dentistry website, patient acquisition for dentists

---

### Stage 3: Content Strategy
**Agent:** `content-strategist`
**Purpose:** Create detailed outline with logical flow and LSI integration

**Process:**
1. Review SERP patterns and SEO requirements
2. Load Mojo Media brand voice from CLAUDE.md
3. Build H1/H2/H3 structure
4. Map LSI terms to specific sections
5. Specify format elements (tables, lists, FAQs)
6. Set tone (blog vs service page)

**Output:** `working/content-outline.md`

**Special handling:**
- Service pages: Formal, direct, benefit-driven (no bucket brigades)
- Blog posts: Conversational, knowledgeable guide (strategic bucket brigades)
- Comparison articles: Client positioned at #1, competitors described neutrally

---

### Stage 4: Content Writing
**Agent:** `content-writer`
**Purpose:** Write complete first draft following outline exactly

**Process:**
1. Follow outline structure precisely
2. Match Mojo Media voice/tone for content type
3. Integrate LSI terms naturally (not forced)
4. Craft strong intro (hook + context + preview)
5. Craft strong conclusion (recap + clear CTA)

**Output:** `working/content-draft.md`

**Format:**
```markdown
URL: suggested-url-slug
TITLE TAG: Optimized title with keyword (under 60 chars)
META DESCRIPTION: SEO-optimized description (155-160 chars)

H1: Main Title

[Intro paragraph]

H2: First Major Section
[Content...]

H3: Subsection
[Content...]

...
```

**Voice guidelines:**
- **Blog posts:** Contractions, short paragraphs, specific examples, bucket brigades (3-4 per 500 words)
- **Service pages:** No bucket brigades, very short paragraphs, action-oriented, stats only if verifiable

---

### Stage 5: Internal Linking
**Agent:** `internal-linker`
**Purpose:** Identify opportunities to link to existing Mojo Media pages

**Process:**
1. Analyze content draft for linkable topics
2. Search Mojo Media website for relevant pages
3. Recommend 3-5 internal links per 1000 words
4. Suggest descriptive anchor text (no "click here")
5. Explain relevance of each link

**Output:** `working/internal-linking-recommendations.md`

**Link quality rules:**
- Contextually relevant to surrounding text
- Descriptive anchor text with keywords
- Deep links (not just homepage)
- Natural placement in sentence flow

---

### Stage 6: Final Editing
**Agent:** `seo-editor`
**Purpose:** Validate SEO checklist, polish content, prepare for publication

**Process:**
1. **SEO Validation:**
   - ✓ 3-Kings Rule (keyword in Title, H1, URL)
   - ✓ Only ONE H1
   - ✓ H2 → H3 logical hierarchy
   - ✓ LSI terms integrated naturally
2. **Tone Consistency:** Match expected voice
3. **Grammar & Clarity:** Fix errors, improve readability
4. **Internal Links:** Insert recommended links
5. **Implementation Notes:** Add uploader instructions

**Output:** `drafts/[url-slug]-[content-type].md` (ready to publish)

**Deliverables:**
1. SEO Validation Report (checklist results)
2. Final Polished Content (copy-paste ready)

---

## Usage

### Manual Orchestration (Current Method)

Run each agent sequentially using the Task tool:

```bash
# Stage 1: SERP Analysis
Task(
  subagent_type: "serp-analyzer",
  prompt: "Analyze SERP for keyword: 'dental web design', content type: service page"
)

# Stage 2: SEO Optimization
Task(
  subagent_type: "seo-optimizer",
  prompt: "Create SEO guide for keyword: 'dental web design'"
)

# Stage 3: Content Strategy
Task(
  subagent_type: "content-strategist",
  prompt: "Create outline for 'dental web design' service page using working/serp-analysis-report.md and working/seo-optimization-guide.md"
)

# ... continue with stages 4-6
```

### Automatic Orchestration (Planned)

The `content-orchestrator` agent will handle the full pipeline:

```bash
Task(
  subagent_type: "content-orchestrator",
  prompt: "Create service page for keyword: 'dental web design'"
)
```

**Status:** Orchestrator exists but not yet recognized by system (requires CLI reload/registration)

---

## Recently Updated ("Previously on...")

### Session: February 1, 2026

**Objective:** Build and test the complete SEO content pipeline for Mojo Media

#### What We Built

1. **Created 6 Specialized Agents**
   - serp-analyzer: SERP research and pattern analysis
   - seo-optimizer: Keyword variations and LSI terms
   - content-strategist: Detailed content outlines
   - content-writer: Complete draft writing
   - internal-linker: Internal link opportunities
   - seo-editor: Final validation and polish

2. **Implemented File-Based Handoff System**
   - All agents save outputs to `working/` directory
   - Downstream agents read previous outputs (no hallucination)
   - Full audit trail for quality control

3. **Built Project Context System**
   - `.claude/CLAUDE.md` contains Mojo Media business context
   - Agents receive brand voice, messaging, target audience
   - Ensures content aligns with client positioning

4. **Created content-orchestrator Agent**
   - Designed to run full 6-stage pipeline automatically
   - Currently not recognized by system (needs CLI reload)
   - Fallback: Manual orchestration works perfectly

#### Issues Discovered

**Problem 1: Agents Not Saving Files**
- **Issue:** seo-optimizer and content-strategist generated content but didn't save to files
- **Root cause:** Agents with Write tool not executing it when invoked as subagents
- **Fix applied:**
  - Changed all agents from haiku → sonnet (better instruction-following)
  - Added explicit "CRITICAL FILE SAVING INSTRUCTIONS" sections
  - Mandatory language: "If you complete without saving, you have failed"

**Problem 2: Orchestrator Not Loading**
- **Issue:** content-orchestrator agent not in available agents list
- **Root cause:** Agent registry needs reload or orchestrator type not supported
- **Workaround:** Manual orchestration (invoke each agent sequentially)

**Problem 3: SERP Analyzer Checking Wrong Page Types**
- **Issue:** Analyzing blog posts when creating service pages (token waste, context pollution)
- **Fix applied:** Added page type filtering to serp-analyzer
  - Now identifies page type from SERP metadata (title, URL, dates)
  - Only analyzes pages matching content type being created
  - Service page → skip blog posts, Blog post → skip service pages

#### Test Case: Dental Web Design Service Page

**Target Keyword:** "dental web design"
**Content Type:** Service page
**Pipeline Status:** 50% complete (3 of 6 stages)

**Completed Stages:**
- ✓ Stage 1: SERP Analysis (saved successfully)
- ✓ Stage 2: SEO Optimization (manually saved after agent failed)
- ✓ Stage 3: Content Strategy (agent reported saving but file not created)

**Pending Stages:**
- ⏳ Stage 4: Content Writing
- ⏳ Stage 5: Internal Linking
- ⏳ Stage 6: Final Editing

**Next Session:** Complete remaining stages 4-6 and verify file auto-save fixes work

#### Key Decisions Made

1. **All agents now use Sonnet** (previously 3 used haiku)
   - More reliable instruction-following
   - Better tool usage
   - Worth the cost for quality and reliability

2. **File-based handoffs are mandatory**
   - Agents must save to files (not just generate content)
   - Enables audit trail and quality control
   - User can inspect/modify between stages if needed

3. **Page type filtering in SERP analysis**
   - Saves tokens (only analyze relevant pages)
   - Improves quality (patterns from matching page types)
   - Reduces context pollution

4. **Service page tone != Blog tone**
   - Service pages: Formal, direct, benefit-driven, no bucket brigades
   - Blog posts: Conversational, contractions, strategic bucket brigades
   - Agents trained on both voices

---

## Configuration

### Agent Models

All agents use **Sonnet (claude-sonnet-4-5)** for reliability and quality.

### Permission Mode

All agents use `permissionMode: default`

### Tools by Agent

| Agent | Tools |
|-------|-------|
| serp-analyzer | Read, Grep, Glob, Bash, WebSearch, WebFetch, Write |
| seo-optimizer | Read, WebSearch, WebFetch, Write |
| content-strategist | Read, Write |
| content-writer | Read, Write |
| internal-linker | Read, Grep, Glob, WebFetch, Write |
| seo-editor | Read, Write |

---

## Troubleshooting

### Agent Doesn't Save Output File

**Symptoms:** Agent generates content but file doesn't appear in `working/` directory

**Fix:**
1. Check agent's output for the generated content
2. Manually save using Write tool
3. Verify agent's AGENT.md has "CRITICAL FILE SAVING INSTRUCTIONS" section
4. Ensure agent is using Sonnet (not haiku)

### Orchestrator Not Found

**Symptoms:** `content-orchestrator` not in available agents list

**Workaround:** Use manual orchestration (invoke each agent sequentially)

**Potential fix:** Restart Claude Code CLI to reload agent registry

### SERP Analyzer Checking Wrong Page Types

**Symptoms:** Analyzing blog posts when creating service pages (or vice versa)

**Fix:** Update serp-analyzer AGENT.md with page type filtering instructions (already applied as of Feb 1, 2026)

### Content Voice Doesn't Match

**Symptoms:** Service page sounds like blog post (or vice versa)

**Check:**
1. Content type specified correctly in agent prompt?
2. content-strategist outline includes tone guidance?
3. content-writer has access to voice guidelines from CLAUDE.md?

---

## Roadmap

### Immediate (Next Session)
- [ ] Complete dental web design service page (stages 4-6)
- [ ] Verify file auto-save fixes work
- [ ] Test full pipeline end-to-end

### Short Term
- [ ] Get content-orchestrator recognized by system
- [ ] Create wrapper script for pipeline verification
- [ ] Add automated output file checking

### Long Term
- [ ] Build skill for quick internal link lookups (mojo-internal-links)
- [ ] Add schema markup generation to seo-editor
- [ ] Create service-page-best-practices and blog-post-best-practices skills
- [ ] Implement automated quality scoring

---

## Content Voice Reference

### Service Page Voice
**Tone:** Formal, direct, benefit-driven
**Structure:** Very short paragraphs (1-2 sentences), bulleted lists
**NO:** Bucket brigades, contractions, conversational hooks
**YES:** Action-oriented language, stats (if verifiable), outcomes focus

**Example:**
```
Custom dental websites that convert visitors into patients.

Mojo Media builds HIPAA-compliant sites with online booking, patient portals,
and mobile-first design. Our dental clients report 40% of revenue attributed
to their websites.
```

### Blog Post Voice
**Tone:** Conversational, knowledgeable guide
**Structure:** Short paragraphs (2-4 sentences), varied sentence length
**YES:** Contractions, bucket brigades (3-4 per 500 words), specific examples
**NO:** Generic openings ("In today's world..."), sales pitches in conclusion

**Example:**
```
Most dental practices pick a web designer based on portfolios. That's usually wrong.

Here's what actually matters: Can they prove results? Do their clients actually
generate leads from their websites? Because a pretty site that doesn't convert
is just expensive decoration.

But here's what you should ask instead...
```

---

## Technical Notes

### H-Tag Format
Content uses **explicit labels** (H1:, H2:, H3:), NOT markdown syntax (##, ###)

**Correct:**
```
H1: Custom Dental Web Design That Converts

H2: Why Choose Custom Over Templates

H3: Template Limitations
```

**Incorrect:**
```
# Custom Dental Web Design That Converts

## Why Choose Custom Over Templates

### Template Limitations
```

### File Naming Convention
Final content files: `drafts/[url-slug]-[content-type].md`

**Examples:**
- `drafts/dental-web-design-service-page.md`
- `drafts/best-web-design-agencies-blog.md`
- `drafts/toronto-web-design-location-page.md`

---

## License

Proprietary - Mojo Media internal use only

---

## Contact

**Client:** Mojo Media
**Website:** https://mojo-agency.com/
**Project Type:** SEO Content Strategy & Blog Content

**Content Strategy Focus:**
- Drive inbound leads for custom web design services
- Target: SMBs ($500K-$10M revenue)
- Industries: Healthcare, professional services, home services, real estate
- Geographic: North America (US & Canada)

---

**Last Updated:** February 1, 2026
