---
name: generating-ugc-ads
description: Produces research-grounded UGC video-ad concepts, first-frame briefs, and generation-ready video prompts for short-form social ads. Use when creating a UGC ad, planning a TikTok/Reel/Shorts campaign, generating ad variations, turning a product page into video concepts, or when user mentions "UGC", "creator ad", "TikTok ad", "Reels ad", "Shorts ad", "video creative", "ad variations".
status: draft
domain: demand-gen
type: encoded-preference
tags: [demand-gen, #analysis, #template, #playbook, #p1]
version: 1.0.0
updated: 2026-07-24
author: GxG
allowed-tools: Read, Write, Edit, Bash, Web
---

# Generating UGC Ads

Builds a traceable pipeline from product information and audience research to human-feeling, generation-ready UGC video ads.

## When to Use This Skill

Activate when:
- A product team needs creator-style TikTok, Reel, or Shorts ad concepts.
- A marketer has a product link, image, or brief and needs UGC creative angles.
- A paid-social team needs a batch of distinct testable ad variations.
- A video-generation tool needs a precise first-frame or video prompt.

Do NOT use when: the request is for a brand campaign without a product and conversion goal, a polished TV commercial, or paid-media buying and optimization.

---

## Workflow

| Workflow | Trigger | Steps |
|----------|---------|-------|
| **Concept pack** | "give me UGC ideas" | Intake → research → concepts → selection |
| **Prompt pack** | "write prompts for this ad" | Confirm concept → first-frame brief → video prompt |
| **Production handoff** | "make the video" | Confirm generation capability → approval gates → generate or hand off |

---

## Instructions

### 1. Intake and scope

Collect or extract:

1. Product name, category, audience, price point, and geography.
2. What it does, its 2–4 defensible benefits, differentiators, and constraints on claims.
3. Product imagery or a product-page URL; do not invent visual details that are not supplied.
4. Desired number of concepts (default: 10; maximum: 20), platform, aspect ratio (default: 9:16), and total duration (default: 15 seconds).
5. The conversion action, such as purchase, free trial, lead form, or app install.

If a missing item would materially change the concept, ask for it. Summarize the accepted product brief in 2–3 lines before research.

### 2. Research the audience before ideation

Read [docs/market-research.md](docs/market-research.md). Run targeted web searches across buyer discussions, reviews, competitor feedback, and credible category sources. Aim for at least 12 independent searches; use public community archives only when their terms and access allow it.

Produce a compact Voice-of-Customer (VoC) brief with:

- Five pains or friction points, with source links and short attributable excerpts where allowed.
- Objections, failed alternatives, desired outcomes, and trigger moments.
- Recurring language that can inform hooks without presenting paraphrase as a verbatim customer quote.
- Competitor praise and complaints.
- A risky-claims list: facts that require proof or must not be used.

Never fabricate evidence. If the research is thin, say so and use fewer, more carefully qualified concepts.

### 3. Create the concept menu

Write up to 20 genuinely distinct concepts. Diversify the hook, creator persona, setting, format, and proof mechanism; do not make small rewrites of one premise.

For each concept, provide:

| Field | Requirement |
|-------|-------------|
| Number and title | Short, memorable working name |
| Hook | First spoken line or on-screen idea, rooted in the VoC brief |
| Format | e.g. skeptic-to-believer, demo, GRWM, comparison, myth-bust |
| Creator and setting | Specific and appropriate to the audience |
| Framework | PAS, BAB, AIDA, Star–Story–Solution, 4Ps, or another named framework |
| Research grounding | The VoC finding or objection it answers |
| Proof and CTA | What makes the claim credible and the desired next step |

End with a selection checkpoint: ask which concepts to build, the duration per concept, and the aspect ratio. Do not generate paid media at this point.

### 4. Plan the chosen ads

For every selected concept, confirm the title, hook, framework, duration, ratio, and product-reference asset. A single generative-video segment should be no more than 15 seconds unless the selected tool explicitly supports more.

For longer ads, define a sequence of short segments:

`hook → problem/proof → benefit/demo → CTA`

Maintain the same creator, wardrobe, product appearance, setting, lighting, and room tone across segments. Use the end frame of a preceding segment as the visual reference for the next one when the video tool supports it.

### 5. Write and approve the first-frame brief

Read [docs/first-frame-prompts.md](docs/first-frame-prompts.md). Create one dense, production-ready first-frame prompt per ad. It must describe camera setup, creator, wardrobe, setting, props, lighting, texture, product placement, and imperfect real-world detail.

Present all prompts together for a batch and obtain explicit approval before calling an image-generation service or incurring credits. A prompt is not approval to spend.

### 6. Generate or hand off the first frame

First determine whether the current environment exposes an authorized image-generation tool. If it does not, deliver the approved prompt, reference-asset list, and a named output path for the production team instead of claiming that an image was generated.

When generating, use the product image as a reference where supported. Return the resulting frame for approval. Revise or regenerate only after the user explicitly directs it.

### 7. Write and approve the video prompt

Read [docs/video-prompts-and-production.md](docs/video-prompts-and-production.md). Write a separate prompt for each segment that contains:

1. Ratio, duration, single-shot behavior, and authentic phone-camera treatment.
2. A time-blocked description of action, hands, facial expression, lighting, background, and product visibility.
3. Natural native dialogue and matching room tone when audio is required.
4. Reference-asset mapping for the creator, approved frame, setting, and product.

Use only supportable product claims. Present the prompt or prompt set and get explicit approval before any paid video generation.

### 8. Produce, stitch, and hand off

Use only a generation service that is available and authorized in the current environment. Poll asynchronous jobs where applicable, retain the generation IDs, and report failures transparently.

For multi-segment ads, inspect the last frame before writing the next prompt. Get approval at each continuation checkpoint. Use `ffmpeg` or the approved editor to concatenate compatible segments; if stream-copy concatenation fails, re-encode deliberately. Verify final duration and aspect ratio.

Return a manifest:

| Ad | Framework | Duration | First frame | Video | Final path/URL | Status |
|----|-----------|----------|-------------|-------|----------------|--------|

### 9. Optional social posting

Posting is a separate, explicit action. Draft a caption, target platform/account, timing, and media URL, then show them to the user. Post or schedule only after a final explicit approval and only through an authorized connected account.

---

## Examples

### Example 1: Batch of ad concepts for a supplement

**Input / Context:**
"Here is our product page and pack shot. Create 10 vertical UGC concepts for a 25–40 US audience; goal is a first subscription."

**Output:**
A product brief, sourced VoC brief, and 10 concepts that each state a hook, creator/setting, copywriting framework, research grounding, proof device, and subscription CTA. The workflow stops for concept selection before writing or generating prompts.

---

### Example 2: 30-second creator ad handoff

**Input / Context:**
"Build concept #4 as a 30-second 9:16 ad. We have a product image but no video generator connected."

**Output:**
Two 15-second segment plans, an approved first-frame prompt, two detailed video prompts with continuity instructions, reference-asset mapping, and a production manifest. No media is represented as generated.

---

## Reference

- Audience-research method: [docs/market-research.md](docs/market-research.md)
- First-frame prompt rules: [docs/first-frame-prompts.md](docs/first-frame-prompts.md)
- Video prompts and production handoff: [docs/video-prompts-and-production.md](docs/video-prompts-and-production.md)
- Source: [sadekxD/ugc-ad-generator-skill](https://github.com/sadekxD/ugc-ad-generator-skill)

## Out of Scope

This skill does NOT:
- Fabricate market research, customer quotes, testimonials, product proof, or regulated claims.
- Make a paid image/video generation call or publish to a social account without explicit approval at that stage.
- Guarantee performance, compliance approval, or access to a specific video-generation provider.
- Replace paid-media targeting, budget allocation, or campaign measurement; use a dedicated media-operations workflow for those decisions.

## Changelog

| Version | Date | Change |
|---------|------|--------|
| 1.0.0 | 2026-07-24 | Initial draft adapted from `sadekxD/ugc-ad-generator-skill`; made provider-neutral, added GxG quality gates and explicit approval controls. |
