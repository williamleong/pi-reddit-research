# pi-reddit-research

Reddit JSON research tools and a matching skill for [pi](https://github.com/mariozechner/pi), focused on compact evidence packs for opinions, bugs, fixes, comparisons, settings, alternatives, trends, guides, hardware, and real-world cases.

## Features

Registers these pi tools:

- `reddit_url_extract` — parse Reddit URLs, permalinks, post IDs, and comment IDs.
- `reddit_resolve_subreddits` — find and rank subreddit candidates for a topic.
- `reddit_pack` — build a compact evidence pack from posts and top comments.
- `reddit_search` — search Reddit posts without fetching full comment threads.
- `reddit_thread` — fetch one thread and top comments.
- `reddit_subreddits` — raw subreddit search.
- `reddit_trends` — inspect hot/top/new posts in one or more subreddits.

Also registers `/reddit` command:

- `/reddit status`
- `/reddit search <query>`

## Install

From npm:

```bash
pi install npm:pi-reddit-research
```

From GitHub:

```bash
pi install git:github.com/SaintNerona/pi-reddit-research
```

For local development:

```bash
pi -e /absolute/path/to/pi-reddit-research
```

## Usage

Ask pi questions like:

- "What does Reddit think about Claude Code vs OpenCode?"
- "Find Reddit fixes for this error: ..."
- "What settings do ComfyUI users recommend for ...?"

The bundled skill teaches the model when to use `reddit_pack`, `reddit_search`, `reddit_thread`, and related tools.

## Configuration

Environment variables:

| Variable | Default | Description |
| --- | --- | --- |
| `PI_REDDIT_CACHE_DIR` | `~/.cache/pi-reddit-research` | Cache directory. |
| `PI_REDDIT_SQLITE_PATH` | `$PI_REDDIT_CACHE_DIR/reddit.sqlite` | SQLite cache path. |
| `PI_REDDIT_USER_AGENT` | `pi-reddit-research/0.1 personal-use (https://www.reddit.com/.json)` | User-Agent for Reddit JSON requests. |
| `PI_REDDIT_DELAY_MS` | `1200` | Minimum delay between Reddit requests. |
| `PI_REDDIT_CACHE_TTL_MS` | `3600000` | Search/request cache TTL. |
| `PI_REDDIT_THREAD_TTL_MS` | `21600000` | Thread cache TTL. |
| `PI_REDDIT_SUBREDDIT_TTL_MS` | `604800000` | Subreddit cache TTL. |
| `PI_REDDIT_TOPIC_TTL_MS` | `2592000000` | Topic-to-subreddit cache TTL. |
| `PI_REDDIT_MAX_OUTPUT_CHARS` | `14000` | Max compact output size. |
| `PI_REDDIT_STATUS_FOOTER` | `true` | Show "Reddit: sqlite" in the TUI footer. Set to `0` or `false` to hide. |

## Notes

This extension uses Reddit's public `.json` endpoints and local SQLite caching. Treat Reddit posts and comments as anecdotal evidence, not verified facts.

## License

MIT
