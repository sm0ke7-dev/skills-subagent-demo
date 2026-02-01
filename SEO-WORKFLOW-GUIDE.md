# SEO Content Creation Workflow
**6-Agent System for Mojo Media**

---

## Overview

You now have 6 specialized subagents that work together to create SEO-optimized content. When you request SEO content, I'll automatically delegate tasks to these agents following the **Hybrid Workflow** below.

---

## The 6 Agents

### 1. **SERP Analyzer** (`serp-analyzer`)
- **What it does:** Analyzes top-ranking pages for your target keyword
- **Output:** SERP Analysis Report (search intent, topics, structure, format elements)
- **Tools:** WebSearch, WebFetch, Read, Grep, Glob, Bash
- **Model:** Haiku (fast, efficient)

### 2. **SEO Optimizer** (`seo-optimizer`)
- **What it does:** Identifies keyword variations, LSI terms, entities, schema recommendations
- **Output:** SEO Optimization Guide (keywords, LSI terms, entities, schema)
- **Tools:** WebSearch, WebFetch, Read
- **Model:** Haiku (fast, efficient)

### 3. **Content Strategist** (`content-strategist`)
- **What it does:** Creates detailed content outline based on SERP + SEO analysis
- **Output:** Content Outline (H-tag hierarchy, topic coverage, LSI placement)
- **Tools:** Read
- **Model:** Sonnet (strategic thinking)

### 4. **Content Writer** (`content-writer`)
- **What it does:** Writes complete content following outline and voice guidelines
- **Output:** Full content draft with LSI integrated, strong intro/conclusion
- **Tools:** Read
- **Model:** Sonnet (quality writing)

### 5. **Internal Linker** (`internal-linker`)
- **What it does:** Finds internal linking opportunities on your website
- **Output:** Internal linking recommendations (where, anchor text, URLs)
- **Tools:** WebFetch, Read, Grep, Glob
- **Model:** Haiku (fast, efficient)

### 6. **SEO Editor** (`seo-editor`)
- **What it does:** Final quality control - validates SEO, tone, grammar, formatting
- **Output:** SEO Validation Report + Final Polished Content (ready to publish)
- **Tools:** Read
- **Model:** Sonnet (thorough review)

---

## Hybrid Workflow (How It Works)

When you say: **"Create SEO blog post for [keyword]"** or similar request, here's what happens:

### **Phase 1: Parallel Research** (Runs simultaneously)
```
SERP Analyzer → Analyzes top-ranking pages
SEO Optimizer → Identifies LSI terms, keywords, entities
```
**Time:** ~3-5 minutes

---

### **Phase 2: Strategy** (Sequential)
```
Content Strategist → Creates detailed outline
  (Uses results from Phase 1)
```
**Checkpoint:** You can review/approve outline here if needed

**Time:** ~2-3 minutes

---

### **Phase 3: Execution** (Parallel)
```
Content Writer → Writes full draft
Internal Linker → Finds internal link opportunities
  (Both run simultaneously)
```
**Time:** ~5-10 minutes (depending on length)

---

### **Phase 4: Quality Control** (Final step)
```
SEO Editor → Validates SEO checklist + polishes content
```
**Deliverables:**
1. SEO Validation Report (checklist status)
2. Final Polished Content (ready to publish with implementation notes)

**Time:** ~2-3 minutes

---

**Total Time:** ~15-20 minutes for complete SEO-optimized content

---

## How to Use the System

### **Option 1: Automatic Delegation (Recommended)**
Just ask me naturally:

```
"Create an SEO blog post for 'Toronto web design pricing'"
```

```
"Write SEO content for 'how to choose a web design agency'"
```

```
"Generate service page content for 'e-commerce website development'"
```

I'll automatically:
1. Recognize it's an SEO content request
2. Kick off the 6-agent workflow
3. Show you progress as each phase completes
4. Deliver final polished content

---

### **Option 2: Manual Control (If You Want to Review Between Phases)**

```
You: "Create SEO content for [keyword] - pause after outline"
```

I'll:
1. Run Phase 1 (research)
2. Run Phase 2 (outline)
3. Pause and show you the outline
4. Wait for your approval
5. Continue with Phase 3 + 4 after you approve

---

### **Option 3: Invoke Specific Agents**

If you only need part of the workflow:

```
"Use the SERP Analyzer to analyze 'Toronto web design'"
```

```
"Have the Content Writer write from this outline: [paste outline]"
```

```
"Run the SEO Editor on this draft: [paste content]"
```

---

## What You'll Receive

### After Phase 1 (Research):
- SERP Analysis Report
- SEO Optimization Guide

### After Phase 2 (Strategy):
- Detailed Content Outline with H-tags and LSI placement

### After Phase 3 (Execution):
- Complete content draft
- Internal linking recommendations

### After Phase 4 (Final):
- **SEO Validation Report** (checklist confirming everything is optimized)
- **Final Polished Content** (clean, formatted, ready to paste into WordPress)
  - Title tag
  - Meta description
  - URL slug
  - Complete content with H-tags marked
  - Internal links inserted
  - Schema markup (JSON-LD code)
  - Implementation notes for uploader

---

## Content Types Supported

### **Blog Posts**
- Voice: Conversational, knowledgeable guide
- Tone: Specific examples, contrarian takes, bucket brigades
- Output: Engaging, SEO-optimized articles

### **Service Pages**
- Voice: Formal, direct, benefit-driven
- Tone: Short paragraphs, scannable, outcome-focused
- Output: Conversion-optimized service descriptions

---

## SEO Checklist (What Gets Validated)

Every piece of content goes through this checklist:

✓ **3-Kings Rule:** Primary keyword in Title, H1, URL
✓ **H-Tag Hierarchy:** Only ONE H1, logical H2 → H3 flow
✓ **LSI Integration:** Geographic, service, industry terms naturally placed
✓ **Content Quality:** Strong intro (hook + context), strong conclusion (CTA)
✓ **Format Elements:** Tables, lists, FAQs as needed
✓ **Internal Links:** 3-5 per 1000 words with descriptive anchors
✓ **Schema Markup:** Appropriate structured data (Article, FAQ, etc.)
✓ **Tone Consistency:** Matches blog/service page voice guidelines
✓ **Grammar & Clarity:** Clean, professional, scannable

---

## Example Usage

### Example 1: Blog Post Request
```
You: "Create an SEO blog post for 'how to choose a web design agency in Toronto'"

[Phase 1 runs - research]
Me: "SERP analysis complete. Search intent is informational. Top pages cover:
     portfolio review, pricing, communication, expertise, etc."

[Phase 2 runs - strategy]
Me: "Content outline created. 2,000 word guide with 5 major sections covering
     portfolio evaluation, pricing transparency, technical expertise, etc."

[Phase 3 runs - writing + links]
Me: "Content draft complete. Internal linking found 4 relevant pages."

[Phase 4 runs - editor]
Me: "Final content ready! SEO checklist validated. Here's your deliverable:"

[Provides final polished content + validation report]
```

---

### Example 2: Service Page Request
```
You: "Write service page content for 'Shopify e-commerce development Toronto'"

[6-agent workflow runs automatically]

Me: "Here's your final service page content:
     - 800 words, formal tone
     - LSI terms: e-commerce, WooCommerce, online store, mobile shopping
     - Local Business + Service schemas included
     - 3 internal links to portfolio/blog
     - Ready to paste into WordPress"
```

---

## Tips for Best Results

1. **Be specific with keywords:** "Toronto web design" is better than "web design"
2. **Specify content type if unclear:** "Blog post about..." or "Service page for..."
3. **Provide context if needed:** "Target audience is small businesses" or "Formal tone"
4. **Review outline before writing:** Ask to "pause after outline" if you want approval first
5. **Trust the process:** The agents follow your SEO checklist and voice guidelines automatically

---

## Agents Location

All 6 agents are stored at:
```
C:\Users\CaloyDadoy\OneDrive\Documents\dan-dev\Mojo Media\.claude\agents\
```

- `serp-analyzer/AGENT.md`
- `seo-optimizer/AGENT.md`
- `content-strategist/AGENT.md`
- `content-writer/AGENT.md`
- `internal-linker/AGENT.md`
- `seo-editor/AGENT.md`

They're project-level, so they only load when working in the Mojo Media project.

---

## Ready to Test!

You mentioned you have a blog post to test this on. Just tell me:

**"Create an SEO blog post for [your target keyword]"**

And the 6-agent system will kick off automatically!

---

**Questions?** Ask anytime. The system is designed to run on autopilot, but you can step in at any phase if needed.
