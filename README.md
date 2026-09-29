# 2pr.io for Claude

Write LinkedIn posts that sound like you, schedule and publish them, answer comments and read your analytics, all from a conversation with Claude.

[2pr.io](https://2pr.io) is a LinkedIn content tool. This plugin connects Claude to your 2pr.io account through the 2pr.io MCP server and adds two skills that teach Claude the safe order of operations: load your voice, draft, refine, and only publish after you confirm.

## What you need

- A 2pr.io account on the **Pro** or **Team** plan ([pricing](https://2pr.io/pricing)).
- Your LinkedIn account connected inside 2pr.io.

The first time Claude calls a 2pr.io tool, a "Sign in with 2pr" window opens (OAuth 2.1). Approve it and you are connected. There is no token to paste, and you can revoke access at any time in 2pr.io under Preferences.

## What is inside

| Component | What it does |
| --- | --- |
| MCP server `2pr` | Remote server at `https://2pr.io/api/mcp` (Streamable HTTP). Tools for drafts, scheduling, publishing, media, the comment inbox, analytics, viral post search and cross-posting to X. Full list: [2pr.io/docs/mcp](https://2pr.io/docs/mcp). |
| Skill `linkedin-posting` | Draft, refine, attach media, schedule or publish a post. |
| Skill `linkedin-engagement` | Draft and post comment replies, read profile and post analytics, find the best posting time. |

## Examples

- "Turn these meeting notes into a LinkedIn post and schedule it for Tuesday morning."
- "Find three viral posts about hiring and draft one in my voice with a similar hook."
- "Which of my posts did best last month, and why?"
- "Draft replies to the comments I haven't answered yet."

## What this plugin sends and stores

This plugin contains no code that runs on your machine. It only points Claude at the 2pr.io MCP server and adds instructions (skills).

- **Where data goes:** only to `https://2pr.io/api/mcp`, operated by 2pr.io. 2pr.io then talks to LinkedIn (and X, if you connect it) through their official APIs to publish on your behalf.
- **What is sent:** the text and media you ask Claude to draft, post or reply with, and the IDs needed to act on your profile.
- **What 2pr.io stores:** your drafts, scheduled posts, voice settings, and the post and comment data needed for analytics and the inbox, under your 2pr.io account. See the [privacy policy](https://2pr.io/privacy).
- **Publishing is public.** The skills tell Claude to ask for your explicit confirmation before publishing, scheduling, replying or deleting.

## Privacy Policy

https://2pr.io/privacy

## Support

Email [hi@2pr.io](mailto:hi@2pr.io) or visit [2pr.io/contact](https://2pr.io/contact).

## License

MIT, see [LICENSE](LICENSE).
