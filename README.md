# ProBet live collector

Standalone public scheduling configuration for the public ProBet API. It contains no application dataset or private application code.

Uses standard free GitHub-hosted runners in a public repository. Set repository secret LIVE_CRON_SECRET; the API must use the same restricted live-only secret. The workflow starts every five minutes, samples every 30 seconds for up to four minutes when matches are active, and exits early if there is no active round. GitHub scheduling is best effort: delays and missed runs are possible. No generated artifacts or caches are retained.

Check the Actions page periodically. GitHub automatically disables scheduled workflows in public repositories after 60 days without repository activity. If disabled, open Actions → Collect live observations → Enable workflow, then Run workflow to check the API connection. Keep the secret private; never add it to the workflow or README. [GitHub scheduling limits](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule).
