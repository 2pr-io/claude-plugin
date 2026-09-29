---
name: linkedin-engagement
description: Work the LinkedIn comment inbox and read post analytics through 2pr.io. Use when the user wants to reply to comments on their posts, react to comments, see which posts performed, or find the best time to post.
---

# LinkedIn replies and analytics with 2pr.io

## Replying to comments

1. Call `profile_list` to get the `profile_id`.
2. Call `engage_refreshPosts` if the user says the inbox looks stale, then `engage_getInbox` to list comments waiting for a reply.
3. Call `engage_draftReplies` to get suggested replies in the user's voice. Show them grouped by post.
4. Post a reply with `engage_postReply` or react with `engage_setReaction` only after the user approves that specific reply. Replies are public.

## Reading analytics

- `analytics_getProfileStats`: follower and impression trends for the profile.
- `analytics_getPostStats`: per-post performance. Lead with the best and worst post and one concrete reason each did what it did.
- `analytics_getPostingTimes`: when this audience is most active. Use it to suggest a schedule slot.

Report numbers as they come back. Do not estimate or fill gaps with guesses; if data is missing for a period, say so.

## Prospecting (optional)

`outbound_listProspects`, `outbound_getFeed` and `outbound_addProspect` track posts from people the user wants to build a relationship with, so they can comment early. Adding or removing prospects changes the user's saved list, so confirm first.
