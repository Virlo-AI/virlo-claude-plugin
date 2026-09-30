# Virlo for Claude

Short-form social intelligence for Claude. Ask what is trending on TikTok, YouTube Shorts, or
Instagram Reels and get live data back: emerging trends, viral videos ranked by weighted
virality instead of raw views, creator profiles with outlier videos and audience demographics,
breakout sounds, trending hashtags, and proven opening hooks. You can also start research
agents that study a niche once, or keep watching it on a schedule and report what changed.

Built for content marketers, social media operators, agencies, founders, and creators who work
on organic short-form video and want the data inside the conversation instead of in another tab.

## What you get

**Skills**

- `virlo` — routes a question to the right Virlo tool, explains what each call costs, polls
  async research agents correctly, and ranks results by weighted virality.
- `short-form-trend-research` — turns live trend data into a weekly content plan: which trends
  and sounds to ride, which hooks and formats are working, which creators to study.

**Commands**

- `/virlo:trend-scout` — what is trending right now across all three platforms.
- `/virlo:niche-analysis` — full niche workup: research agent, creators, recurring monitor.
- `/virlo:creator-deep-dive` — one creator's outlier videos, cadence, and audience.
- `/virlo:genre-monitor` — stand up a recurring monitor for a genre or scene.

## Setup

Connect the Virlo connector from the plugin's **Connectors** tab and sign in when Virlo prompts
you. Sign-in is OAuth, so there is no API key to create, paste, or store. If you do not have a
Virlo account yet, you can create one during sign-in.

## What this plugin does, exactly

Disclosed in full so you can judge it before installing:

- **It connects to one endpoint and nothing else:** Virlo's hosted MCP server at
  `https://dev.virlo.ai/api/mcp/mcp`, over HTTPS. There is no other network destination, no
  telemetry, and no analytics.
- **It runs no local code.** The plugin ships skills, commands, and one remote MCP server
  declaration. It contains no hooks, no scripts, no executables, and no `bin/` directory. It
  does not read or write files on your machine.
- **It authenticates as you, through OAuth.** The plugin never reads an environment variable,
  never asks for a key, and never handles a credential itself. Your Virlo session is held by
  the client, and Virlo's authorization server issues it.
- **It reads public social data.** It does not post, comment, follow, or connect to your own
  TikTok, YouTube, or Instagram accounts. It has no write access to any social platform.
- **It spends Virlo credits.** Research agents, creator lookups, video analysis, and some
  trend, hashtag, and sound reads bill against your Virlo balance per call. The `virlo` skill
  tells Claude to check your balance and quote the expected cost before any paid run, and to
  get your go-ahead before creating a recurring agent, because a recurring agent bills on
  every run. Credits are purchased on virlo.ai, never inside Claude.

## Costs and billing

Virlo is pay-as-you-go against a prepaid balance. Reads of results you already created are
free; starting new work is not. The `X-Cost` response header on every call is the authoritative
charge. Live per-tool pricing is at [dev.virlo.ai/docs/mcp](https://dev.virlo.ai/docs/mcp).

## Links

- Product: [virlo.ai](https://virlo.ai)
- MCP docs and tool reference: [dev.virlo.ai/docs/mcp](https://dev.virlo.ai/docs/mcp)
- Support: [virlo.ai/support](https://virlo.ai/support)
- Privacy: [virlo.ai/legal/privacy-policy](https://virlo.ai/legal/privacy-policy)
- Terms: [virlo.ai/legal/terms-of-service](https://virlo.ai/legal/terms-of-service)

## License

MIT. See [LICENSE](./LICENSE).
