# QuickDukan Auth Page

Hosted social-login page for the QuickDukan **user app** (Google / Facebook / Telegram).

## How it works
1. The app opens this page in the system browser.
2. User taps a provider button and signs in.
3. This page deep-links the verified provider token back into the app:
   `quickdukan://social?provider=...&idToken=...`
4. The app sends that token to the backend (`action=socialLogin`), which verifies it
   server-side and returns a session token.

## Setup (edit CONFIG at the top of index.html)
- `GOOGLE_CLIENT_ID`  — from Google Cloud Console (OAuth client, Web). Add this page's
  origin to **Authorized JavaScript origins**.
- `FACEBOOK_APP_ID`   — from Meta for Developers. Add this page's URL as the site URL.
- `TELEGRAM_BOT_USERNAME` — your bot. Set the bot's domain (/setdomain) to this page's domain.

Only these three values go here. Secrets (Facebook App Secret, Telegram bot token) live
in the backend Script Properties, never in this page.
