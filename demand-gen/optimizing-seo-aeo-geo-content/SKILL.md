---
name: optimizing-seo-aeo-geo-content
description: "Runs the full Russian SEO/AEO/GEO content workflow from research to publication-readiness audit: research brief, article architecture, drafting, SEO/AEO/GEO editing, and final quality review. Use when the user asks for a complete content production process, an end-to-end article workflow, or mentions \"SEO/AEO/GEO контент\", \"полный цикл статьи\", \"ресерч, структура, текст, оптимизация и аудит\"."
status: active
domain: demand-gen
type: workflow
tags: [demand-gen, #workflow, #process, #playbook, #p1]
version: 1.0.0
updated: 2026-06-30
author: GxG
allowed-tools: Read, WebSearch
---

# Optimizing SEO AEO GEO Content

Coordinates the complete Russian SEO/AEO/GEO article workflow. This is a composite skill: use the nested skills for specific steps, or run them in sequence when the task requires the full content pipeline.

## When to Use This Skill

Activate when:
- The user wants a complete SEO/AEO/GEO content workflow, not just one editing step
- A topic needs to become a researched, structured, drafted, optimized, and audited Russian article
- The request spans multiple stages such as research, outline, writing, metadata, FAQ, schema candidates, and publication readiness
- The user asks to fix or manage the full article process

Do NOT use when the user clearly asks for only one step. In that case, use the relevant nested skill directly.

---

## Nested Skills

| Step | Skill | Purpose |
|------|-------|---------|
| 1 | [researching-content](researching-content/SKILL.md) | Build the research brief, intent map, facts, source notes, and risky-claim list |
| 2 | [architecting-articles](architecting-articles/SKILL.md) | Turn the brief into a GxG-style article outline |
| 3 | [writing-articles](writing-articles/SKILL.md) | Draft the Russian long-form article from the approved outline |
| 4 | [editing-seo-aeo-geo-content](editing-seo-aeo-geo-content/SKILL.md) | Edit the draft for SEO, AEO, GEO, metadata, FAQ, internal links, and extractable structure |
| 5 | [auditing-content-quality](auditing-content-quality/SKILL.md) | Run the final publication-readiness audit |

---

## Workflow

### Full Content Pipeline

1. Use `researching-content` to define reader job, search intent, verified facts, source-backed examples, SEO/AEO/GEO opportunities, and risky claims.
2. Use `architecting-articles` to create the article structure, `Коротко` block, tables, checklist, FAQ, and writer notes.
3. Use `writing-articles` to produce the draft in Russian with practical examples, natural GxG voice, and cautious claims.
4. Use `editing-seo-aeo-geo-content` to improve headings, answer-first sections, metadata, FAQ schema candidates, internal links, and extractability.
5. Use `auditing-content-quality` to decide whether the article is ready to publish and list remaining fixes.

### Partial Pipeline

If the user already has an artifact from an earlier stage, start from the next relevant nested skill:
- Verified brief exists -> start with `architecting-articles`
- Approved outline exists -> start with `writing-articles`
- Draft exists -> start with `editing-seo-aeo-geo-content`
- Near-final article exists -> start with `auditing-content-quality`

---

## Output Format

For a full pipeline, produce staged outputs rather than merging all decisions into one block:

```markdown
# Research Brief

# Article Outline

# Draft Article

# SEO/AEO/GEO Edit Notes

# Content Audit
```

---

## Out of Scope

This composite skill does NOT:
- Replace the nested skills' detailed instructions
- Invent facts, metrics, sources, rankings, salaries, or search performance claims
- Force the full workflow when the user only needs one stage
- Guarantee traffic, citations, rankings, conversion, or AI answer inclusion

---

## Changelog

| Version | Date | Change |
|---------|------|--------|
| 1.0.0 | 2026-06-30 | Converted from single editor skill into composite SEO/AEO/GEO content workflow |
