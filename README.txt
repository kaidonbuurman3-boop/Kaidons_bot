KAIDON'S BOT — FULL STARTER PACKAGE

INCLUDES
- Installable mobile web app (PWA) and basic offline app-shell
- Offline commands: .help, .joke, .quiz, .answer 1/2/3, .score, .game, .guess, .rules, .info, .play
- Online AI chat and .photo image generation through a Cloudflare Worker

IMPORTANT
- This is a standalone app, NOT a WhatsApp bot. It cannot join or control WhatsApp groups.
- .play does not stream music; it points users to share licensed music links.
- Online AI/image generation needs internet, an eligible adult-managed provider account and may have usage limits or charges.
- Keep GEMINI_API_KEY only as a Cloudflare Worker Secret. Never put it in app.js or GitHub.
- ALLOWED_ORIGIN limits browser origins but is not authentication. Before public launch, an adult must configure Cloudflare rate limiting or a suitable access-control layer. Do not share the Worker publicly before this.
- Do not upload private photos or anyone else's images without permission.

PUBLISH THE APP
1. Replace the old app files in the root of your GitHub Pages repository with index.html, style.css, app.js, manifest.webmanifest and sw.js.
2. Wait for GitHub Pages to redeploy. Offline commands should work.

CONFIGURE THE WORKER (adult helper handles account, key and billing)
1. In Cloudflare Workers, open your Worker and replace its code with worker.js.
2. Add a Worker Secret named GEMINI_API_KEY; paste the key into the secret field only.
3. Add a plain-text variable ALLOWED_ORIGIN equal to your exact GitHub Pages origin, e.g. https://your-account.github.io (no path/trailing slash).
4. Deploy the Worker.
5. In app.js, set API_BASE to your Worker URL, e.g. https://your-worker.workers.dev, then upload app.js again.
6. Have the adult configure rate limiting/access control before making it public.

TEST
.help
.quiz
.answer 2
.score
.game
.guess 3
.photo create a futuristic gaming logo

IMAGE API
Uses Gemini Nano Banana 2.1 through Google's Interactions API. Model availability, access and pricing can change. See https://ai.google.dev/gemini-api/docs/image-generation

WHATSAPP
A direct WhatsApp group connection is not included. Official WhatsApp group API access has strict business eligibility and is not a reliable fit for a normal friends' group.
