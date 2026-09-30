# Security Policy

## Reporting a vulnerability

If you find a security vulnerability in WaxFrame Free, **please report it privately** — do not open a public issue, since a public issue tips off potential attackers before a fix is out.

Use GitHub's **private vulnerability reporting**: go to the
[Security tab](https://github.com/WeirDave/WaxFrame-Free/security)
and click **Report a vulnerability**. This opens a private channel visible only to the maintainer.

Please include:

- What the vulnerability is and where it lives (file / feature / release).
- Steps to reproduce, or a minimal proof of concept.
- The release you are running, from [GitHub Releases](https://github.com/WeirDave/WaxFrame-Free/releases).

You'll get an acknowledgment as soon as it's seen. Confirmed issues are patched on a priority basis and credited in the release notes unless you ask otherwise.

## Supported versions

Only the **latest release** is supported for security fixes. If you're running an older copy, download the latest before reporting.

## Scope and design notes

WaxFrame Free is a **local-first, static browser application** — `index.html`, `app.js` and `style.css`, with no build step and no server:

- There is no account, backend or telemetry, and the app makes no calls to any AI provider. Prompts are copied out and responses pasted in by hand.
- Session state lives in the browser's `localStorage` and in session files you export yourself.
- Because the app renders text pasted from AI responses and imported session files, the most serious class of vulnerability is **anything that can execute script in the page** (XSS). Reports of injection vectors through pasted content or crafted session files are especially valued.
