# TB50K Tracker

Cloudflare Worker + Telegram bot live tracker for Madeline's Taco Bell 50K.

## Cloudflare secrets
- `TELEGRAM_BOT_TOKEN` — already created in the Worker.
- `SETUP_KEY` — create a random private value.

## Optional persistent storage
Create a Cloudflare KV namespace and bind it to this Worker as `TRACKER_KV`. Without KV, the tracker uses temporary Worker memory and will not reliably persist across restarts.

## First setup
1. Deploy the Worker.
2. Add `SETUP_KEY` as a secret.
3. Open `https://YOUR-WORKER.workers.dev/setup-webhook?key=YOUR_SETUP_KEY` once in Safari.
4. Open the Telegram bot and send `/race` to start the race.
5. Send location/live location, text, and photos to the bot.
6. Public tracker is the Worker root URL.

## Commands
- `/race` starts the timer and resets progress.
- `/finish` records a finish.

The route is embedded from the supplied 2026 Taco Bell 50K GPX.
