# Free Stack Launch

A Claude Code plugin that takes an app working on your machine (often vibe-coded) and puts it into production on free tiers. If the app has a mobile client, it also helps publish it to the App Store and Google Play.

## What it sets up

| Need | Default (free tier) | Fallback |
|---|---|---|
| API server | Google Cloud Run | Render |
| Database | MongoDB Atlas M0 | Neon / Supabase |
| Files | Cloudflare R2 | Supabase Storage |
| Email | Resend | Brevo |
| Errors + logs | Sentry | Axiom / Grafana Cloud |
| Analytics | PostHog | Firebase Analytics |
| Uptime | UptimeRobot | HetrixTools |
| Landing | Cloudflare Pages | Netlify |
| Code | GitHub (private repo) | GitLab |
| Secrets | Doppler | Infisical |

Optional: a staging environment, which it suggests and explains first, and only sets up if you say yes.

At the end it writes a `STACK.md` in your repo: what lives where, each free limit, and the sign that it's time to upgrade.

## Install

```bash
claude plugin marketplace add koliasyniuha/free-stack-launch
claude plugin install free-stack-launch@free-stack-launch
```

Then, in your project, tell Claude Code: "deploy a free stack for my app".

## Browser setup

With your permission, the plugin opens the services' dashboards in your Chrome (Claude in Chrome extension, `claude --chrome`) and clicks through the steps that have no CLI: creating projects, generating API tokens straight into your secrets manager, and changing settings. You watch it live and can stop it at any time. Logins, payments, legal agreements and ID checks always stay with you.

## What you still do yourself

- Create the accounts (signups have captchas, card checks and ToS). The plugin gives you the links and tells you what to pick.
- Log in through each CLI. Tokens are entered in the terminal, not in chat.
- Approve every step that costs money or can't be undone. Nothing paid is created without your OK.

## Costs that aren't free

- Apple Developer Program: $99/year
- Google Play Console: $25 one-time. New personal accounts need a closed test with 12 testers for 14 days before production.
- Some providers (Cloud Run, R2) need a card. The plugin sets budget alerts.

Free-tier limits change often; the plugin checks current limits before it relies on them.

## Privacy

- The plugin has no server of its own. It collects, stores and retains no data.
- It reads your project's files on your machine to plan the setup.
- With your permission, it sends your app's code and config to the services you pick in the table above (for example Cloud Run, MongoDB Atlas, Cloudflare). Each service's own privacy policy applies to that data.
- API keys and tokens go straight into your secrets manager. The plugin never writes them to chat, tracked files, logs or screenshots.
- It does not read or store personal data such as names, emails or addresses.

## License

MIT
