RAJ MUSIC PRO — PERFORMANCE + FEATURE UPGRADE

Built on the latest working fixed version (including optional YOUTUBE_COOKIES_FILE support).

New upgrades:
- Dedicated yt-dlp worker pool (4 workers) so extraction does not block Discord's event loop.
- 90-second metadata cache (up to 128 entries) for repeated searches.
- Faster extraction timeout/retry settings.
- /voteskip — listeners in the bot's voice channel can vote to skip.
- /removeduplicates — remove duplicate waiting tracks.
- /reversequeue — reverse the waiting queue.
- Previous-track button added to the interactive dashboard.
- Existing commands, autoplay, loop, lyrics, history, queue, cookies support and Railway configuration retained.

Railway deployment:
1. Replace the current bot.py with this bot.py.
2. Keep requirements.txt, Procfile and nixpacks.toml in the repository root.
3. Railway Variables:
   DISCORD_TOKEN = your Discord bot token
   GUILD_ID = your server ID (recommended for fast slash-command sync)
   AUTO_DISCONNECT_MINUTES = 5
   OWNER_IDS = (optional comma-separated owner IDs)
   YOUTUBE_COOKIES_FILE = (optional; path to a securely provided cookies file)
4. Commit/push to GitHub and redeploy.
5. Test /ping, /dashboard, /play, /voteskip, /removeduplicates and /reversequeue.

Security and limitations:
- Never commit your bot token or cookies.txt to a public repository.
- Caching and worker tuning improve responsiveness but cannot bypass YouTube anti-bot restrictions.
- Syntax validation is not a live Discord voice or YouTube integration test.
