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

| Key | Name | Avatar |
|---|---|---|
| `hub-capacity-issue-log` | Hub Capacity Issue Log | [avatars/hub-capacity-issue-log.png](avatars/hub-capacity-issue-log.png) |
| `rca-log-book-submission` | RCA Log Book Submission | [avatars/rca-log-book-submission.png](avatars/rca-log-book-submission.png) |
| `piket-data-huddle-senin` | Piket Data Huddle Senin | [avatars/piket-data-huddle-senin.png](avatars/piket-data-huddle-senin.png) |
| `piket-dp-huddle-senin` | Piket DP Huddle Senin | [avatars/piket-dp-huddle-senin.png](avatars/piket-dp-huddle-senin.png) |
| `hub-capacity-ticket-submission` | Hub Capacity Ticket Submission | [avatars/hub-capacity-ticket-submission.png](avatars/hub-capacity-ticket-submission.png) |

Avatar URLs follow this pattern (the repo must be public for them to load):

```
https://raw.githubusercontent.com/rickyastro/ricky-assets/main/avatars/<key>.png
```

## Adding a webhook

1. Add the image to `avatars/<key>.png` (square, ~256×256).
2. Add an entry to `assets.json`.
3. Add `WEBHOOK_<KEY>=` to `.env.example`.
4. Add a row to the table above.

## Webhook URLs

Webhook URLs are secrets: anyone who has one can post to the space. Keep them in a local `.env` (it's gitignored) or in your script's secret store, not in this repo.
