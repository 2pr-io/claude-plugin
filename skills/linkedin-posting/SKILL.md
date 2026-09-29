---
name: linkedin-posting
description: Write, refine, schedule and publish LinkedIn posts through 2pr.io. Use when the user wants a LinkedIn post drafted, rewritten in their voice, turned into a carousel or image post, scheduled for later, or published now.
---

# LinkedIn posting with 2pr.io

The 2pr.io connector acts on the user's real LinkedIn account. Drafting is safe to repeat; publishing is public and cannot be taken back.

## Workflow

1. **Pick the profile.** Call `profile_list` first. Most tools need a `profile_id`. If the user manages more than one profile, ask which one before drafting.
2. **Load the voice.** Call `persona_get` so the draft sounds like the user, not like a generic LinkedIn post. Only change the persona with `persona_appendDirective` or `persona_replace` when the user asks for a lasting style change.
3. **Find an angle (optional).** When the user has a topic but no angle, call `viral_search` for proven posts on that topic and borrow the structure, never the words. `inspiration_getTopics` suggests topics from the user's niche.
4. **Draft.** Call `draft_create` with the user's idea. It returns three variants of the same angle (regular, extended, one-line-per-thought) and a link that opens the draft in the 2pr.io editor. Show the user the variant that fits best and the link.
5. **Refine.** Use `draft_refine` for edits ("shorter", "stronger hook", "less salesy"). Use `draft_get` to re-read a draft before acting on it.
6. **Add media (optional).** `media_generateImage`, `media_uploadFromUrl` and `draft_attachImages` / `draft_attachMedia` attach images, carousels or video.
7. **Ship it.** Only after the user confirms the final text:
   - `post_schedule` for a future time. Suggest a slot from `analytics_getPostingTimes` when the user has no preference.
   - `post_publish` to post now.
   - `x_publish` / `x_schedule` to cross-post to X when the user asks.

## Rules

- Never call `post_publish`, `post_schedule`, `x_publish` or `post_delete` without an explicit yes from the user for that exact post.
- Show the final text before publishing. Do not silently edit it after approval.
- `post_list` shows what is already scheduled; check it before adding a post on a day that is already taken.
- If a tool says the plan does not include this feature, tell the user that the 2pr.io connector needs a Pro or Team plan and link https://2pr.io/pricing.
