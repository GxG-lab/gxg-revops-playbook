# Video Prompts and Production Handoff

Use this reference after the first frame is approved. Write one prompt per generated segment; keep segments at 15 seconds or less unless the selected tool documents another limit.

## Prompt structure

```text
{ratio}. {duration} seconds. One continuous UGC-style phone-camera shot.

References: creator = {approved first frame}; product = {product image};
setting = {setting reference, if supplied}.

[0:00–0:05] {camera movement, action of both hands, face, product state,
background, light direction, what must remain out of frame}.

[0:05–0:10] {next action and proof/demonstration; preserve creator, wardrobe,
setting, lighting, and product identity}.

[0:10–0:15] {closing action, expression, CTA moment, and a clean end frame}.

Audio: {speaker age range and conversational energy}; {room tone appropriate to
setting}; natural pacing. Dialogue: "{supportable, casual spoken line}".
```

Adapt the number of time blocks to the actual duration. Each block should specify the creator's action, face, product visibility, surface/background, and light continuity.

## Continuity for longer ads

1. Generate segment one from the approved first frame.
2. Extract and inspect a stable late frame; use it as the visual reference for the next segment when the tool permits.
3. Continue the story from hook to proof to benefit to CTA without changing creator, wardrobe, room, lighting, or audio atmosphere.
4. Present the next-segment prompt and reference frame for approval before another paid call.
5. Concatenate compatible files with `ffmpeg`; re-encode only if the segments do not share compatible codec, resolution, and frame rate.

## Production manifest

```markdown
| Ad | Segment | Generation ID | Reference assets | Approval | Output | Status |
|----|---------|---------------|------------------|----------|--------|--------|
```

## Safety and delivery

- Do not claim a prompt has been generated into media when no authorized provider is available.
- Preserve source links for product claims and customer evidence.
- Require final approval before publishing to any social account.
- Deliver local file paths or reachable URLs, codec, duration, ratio, caption draft, and the manifest to the production owner.
