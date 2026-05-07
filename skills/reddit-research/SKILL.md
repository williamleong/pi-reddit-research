---
name: reddit-research
description: Use Reddit JSON research tools to find compact evidence about user opinions, bugs, fixes, comparisons, settings, alternatives, trends, guides, hardware, and real-world cases.
---

# Reddit Research

Use the local Reddit tools when the user asks what people on Reddit say, recommend, complain about, compare, or use in real practice.

## Tool Choice

- Use `reddit_pack` for most research questions. It searches posts and fetches top comments for a small evidence pack.
- Use `reddit_search` when you only need candidate posts or want to find whether a topic/repo/error was discussed.
- Use `reddit_thread` when the user gives a Reddit URL or one thread from `reddit_search` looks important.
- Use `reddit_resolve_subreddits` when the user asks where a topic is discussed or when a focused subreddit scope would improve search.
- Use `reddit_subreddits` only for raw subreddit search when ranking is not needed.
- Use `reddit_url_extract` when the user gives an arbitrary Reddit URL, old.reddit URL, post id, or comment id.
- Use `reddit_trends` for "what is currently hot/top/new in r/LocalLLaMA" style questions.

## Intent Mapping

- opinions: "what do people think", product/tool sentiment, praise vs criticism.
- bugs: frequent problems, complaints, failure modes, risks.
- fixes: how people solved an error or configuration issue.
- compare: A vs B, which tool users pick, migration reasons.
- settings: sampler, scheduler, config, parameters, low denoise, hardware settings.
- alternatives: replacements for a library, service, app, or workflow.
- trends: what topics are surfacing recently.
- guides: tutorials, walkthroughs, reproducible setup posts.
- hardware: devices, VRAM/RAM, speed, thermals, purchase advice.
- general: fallback for broad Reddit research.

## Depth

- `quick`: first-pass orientation; fewer posts and comments.
- `normal`: default for most user questions.
- `deep`: use only when the user asks for thorough research; it fetches more comments and costs more tokens/time.

## Answering Rules

- When a tool has a `subreddits` parameter, pass multiple subreddits as one comma-separated string like `LocalLLaMA, LocalLLM, ClaudeCode`, not as a JSON/list value.
- Treat Reddit as anecdotal evidence, not truth.
- Separate repeated patterns from one-off comments.
- Mention uncertainty when evidence is thin or old.
- Cite evidence by post number, subreddit, or thread URL from tool output.
- Prefer concrete details from comments: versions, commands, settings, hardware, exact error text, and final outcome.
- For comparisons, group findings by option and distinguish direct user experience from speculation.
- Do not invent subscriber counts, trend numbers, score totals, or popularity claims unless the tool output includes them.
- Use `evidence_items` and clusters from `reddit_pack` as hints, not as final truth.
