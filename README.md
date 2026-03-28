# Gmail Terminator

A lightweight, single-file web app for bulk managing your Gmail inbox — no backend, no installs, runs entirely in your browser.

## Features

- **Bulk Delete** — Move emails older than a chosen date to Trash (Gmail auto-purges Trash after 30 days)
- **Mark as Read** — Mark thousands of unread emails as read in seconds
- **Location Filters** — Target Inbox, Sent, Spam, Trash, or everywhere at once
- **Time Range Filters** — Scope mark-as-read to today, last 7 days, last 30 days, or all time
- **Privacy first** — Your OAuth token never leaves your browser; no server ever sees your emails

## Setup

The app requires a Google OAuth Client ID to authenticate with the Gmail API. Here's how to get one:

1. Go to [Google Cloud Console](https://console.cloud.google.com/) → **APIs & Services** → **Credentials**
2. Click **Create Credentials** → **OAuth client ID** → choose **Web application**
3. Under **Authorized JavaScript origins**, add the domain you'll host the app on (e.g. `http://localhost` for local testing)
4. Copy the generated **Client ID**
5. Open `index.html` and replace the `CLIENT_ID` value near the top of the `<script>` tag:

```js
const CLIENT_ID = 'YOUR_CLIENT_ID_HERE';
```

6. Enable the **Gmail API** for your project under **APIs & Services** → **Library**

## Usage

Open `index.html` in a browser (or host it anywhere — GitHub Pages, Netlify, etc.), sign in with Google, and use the cards to bulk delete or mark emails as read.

> **Note:** After running an action, refresh your Gmail tab to see the changes reflected.

## Hosting

Since it's a single HTML file, you can host it anywhere static files are served:

- **GitHub Pages** — push to a `gh-pages` branch or enable Pages on `main`
- **Netlify / Vercel** — drag and drop the file
- **Locally** — open `index.html` directly, or serve with `npx serve .`

## Permissions

The app requests the `gmail.modify` OAuth scope, which allows reading and modifying (but not permanently deleting) messages. Emails moved to Trash can be recovered within 30 days.

## License

MIT
