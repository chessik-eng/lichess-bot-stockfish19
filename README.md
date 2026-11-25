# Lichess bot — Stockfish 19

This repository runs the official `lichess-bot` client with the official Stockfish 19 Linux x86-64 universal binary.

## One-time setup

1. Create a separate Lichess account for this bot. Do not convert your personal playing account into a bot account.
2. On that account, create a personal API token with the `bot:play` scope.
3. In this GitHub repository, open **Settings → Secrets and variables → Actions → New repository secret**.
4. Name the secret exactly `LICHESS_BOT_TOKEN` and paste the token as its value. Never commit the token or post it in chat.
5. Open **Actions → Lichess bot — Stockfish 19 → Run workflow** to start the first run.

## Runtime

- GitHub Actions starts a run every six hours (UTC) and can also be started manually.
- Each run keeps the bot online for up to 5 hours 45 minutes, then exits cleanly so the next scheduled run can start.
- GitHub-hosted runners are temporary. This is a scheduled service, not guaranteed uninterrupted 24/7 hosting; scheduled starts can be delayed by GitHub.
- The workflow downloads the current `lichess-bot` client and the pinned Stockfish 19 release when it starts.
- Engine settings: 2 threads and 2048 MB hash. Actual strength depends on the runner CPU, time control, and Lichess opponents; no fixed Lichess rating is guaranteed.

## Upstream projects

- lichess-bot: https://github.com/lichess-bot-devs/lichess-bot
- Stockfish 19 release: https://github.com/official-stockfish/Stockfish/releases/tag/sf_19

The lichess-bot client is distributed under AGPL-3.0-or-later. Stockfish is distributed under GPL-3.0-or-later; see the upstream projects for their license notices.
