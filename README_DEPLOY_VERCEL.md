# JARVIS — Vercel website deployment bundle

This bundle deploys the **public static website** for `jarvis-intel.com`. It does not deploy the private Python AI/device-control backend, and the device approval panel is a local demo only. No API key belongs in this bundle.

## Deploy through Vercel (requires your account login)

1. Sign in at https://vercel.com/ and create a new project connected to a Git repository containing these files. If you don't have a Git repository, create one at https://github.com/new, upload the contents of this folder, and then import that repository in Vercel.
2. Framework preset: **Other**. Build command: leave empty. Output directory: `.` (the project root). Install command: leave empty.
3. Click **Deploy** and wait for Vercel to report success. Vercel should provide a `*.vercel.app` preview URL; open it and check the page on mobile and desktop.
4. In Vercel project **Settings → Domains**, add `jarvis-intel.com` and optionally `www.jarvis-intel.com`.
5. At the DNS provider for your domain, enter exactly the DNS records Vercel shows for the domain. Do not guess records or remove existing email-related DNS records. If the domain is registered elsewhere, keep the registrar and update its DNS records as instructed by Vercel.
6. Wait for Vercel to verify the domain and provision HTTPS, then test `https://jarvis-intel.com` and `https://www.jarvis-intel.com` if you added `www`.

Official docs:
- Import a project: https://vercel.com/docs/getting-started-with-vercel/import
- Add a domain: https://vercel.com/docs/domains/working-with-domains/add-a-domain

## Important limitations before public launch

- This is a static marketing/interface preview. Chat, real AI responses, account sign-in, and remote device control are **not connected** in this bundle. The approval buttons are explicitly demo-only.
- Do not expose the local Flask server or desktop agents directly to the internet. Before connecting live AI or device control, deploy a secure backend with authentication, authorization, rate limiting, audit logs, device revocation, and server-side API secrets.
- Add a real privacy policy and contact/support details before collecting user data or submitting apps to stores.
- Deployment is not complete until you sign into Vercel, deploy, add the domain, configure DNS, and verify the live HTTPS site. This package itself does not publish anything.


## Updated PIN lock
The website now shows a keypad before the main interface. The demo PIN is `0103`.
This PIN is checked in browser JavaScript, so it is only a visual/demo lock and is NOT strong security for private information. Use server-side authentication for real protection.
