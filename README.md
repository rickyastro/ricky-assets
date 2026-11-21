# ricky-assets

Avatar images and a lookup dictionary for Google Chat webhook bots.

## Structure

```
ricky-assets/
├── avatars/          # one PNG per webhook, named <key>.png
├── assets.json       # dictionary: key → name, avatar_url, webhook_env
├── .env.example      # webhook URL template (copy to .env, never commit)
└── README.md
```

## Webhooks

| Key | Name | Character | Avatar |
|---|---|---|---|
| `hub-capacity-issue-log` | Hub Capacity Issue Log | Squidward | [avatars/hub-capacity-issue-log.png](avatars/hub-capacity-issue-log.png) |
| `rca-log-book-submission` | RCA Log Book Submission | Plankton | [avatars/rca-log-book-submission.png](avatars/rca-log-book-submission.png) |
| `piket-data-huddle-senin` | Piket Data Huddle Senin | Sandy | [avatars/piket-data-huddle-senin.png](avatars/piket-data-huddle-senin.png) |
| `piket-dp-huddle-senin` | Piket DP Huddle Senin | Patrick | [avatars/piket-dp-huddle-senin.png](avatars/piket-dp-huddle-senin.png) |
| `hub-capacity-ticket-submission` | Hub Capacity Ticket Submission | Mr. Krabs | [avatars/hub-capacity-ticket-submission.png](avatars/hub-capacity-ticket-submission.png) |
| `data-sc` | Data SC (bugs, deployments, weekly recap) | SpongeBob | [avatars/data-sc.png](avatars/data-sc.png) |
| `github-relay-ricky` | GitHub Relay Ricky | Karen | [avatars/github-relay-ricky.png](avatars/github-relay-ricky.png) |
| `scms-homebrew-cafe-data` | SCMS Homebrew Cafe Data (Superset cookie expired, refresh needed) | Gary | [avatars/scms-homebrew-cafe-data.png](avatars/scms-homebrew-cafe-data.png) |

Avatar URLs follow this pattern (the repo must be public for them to load):

```
https://raw.githubusercontent.com/rickyastro/ricky-assets/main/avatars/<key>.png
```

## Adding a webhook

1. Add the image to `avatars/<key>.png` (square, ~256×256). PNG or JPG; avoid SVG/WebP. If you use JPG, update `avatar_file`/`avatar_url` in `assets.json` to match.
2. Add an entry to `assets.json`.
3. Add `WEBHOOK_<KEY>=` to `.env.example`.
4. Add a row to the table above.

## Webhook URLs

Webhook URLs are secrets: anyone who has one can post to the space. Keep them in a local `.env` (it's gitignored) or in your script's secret store, not in this repo.
