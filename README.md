# firedash-landing

Static landing page and privacy policy for **FireDash**, the iOS Firebase console.

Static files, no build step:

- `index.html` — what the app does, how it avoids wrecking production, and the support contact
- `privacy.html` — the privacy policy
- `terms.html` — terms of service for OAuth and App Store review
- `data-deletion.html` — how users revoke Google access and remove local app data

`index.html` doubles as the App Store **Support URL** and Marketing URL, so the support
section has to stay reachable and has to offer a real way to reach a person — Apple checks.

## Why this exists

It isn't only marketing. Google's OAuth verification for sensitive scopes requires a
**public homepage** and a **public privacy policy** on a **domain verified in Google Search
Console**, and the privacy policy must carry the Limited Use disclosure. `privacy.html` has
that disclosure, and the scope table in it must be kept in step with the scopes FireDash
actually requests (`FireDash/Core/Auth/GoogleScope.swift`).

## Deploying

Same as the other landing repos: push to `zhiyao92/firedash-landing` and enable GitHub Pages
on the default branch. Lands at `https://zhiyao92.github.io/firedash-landing/`.

**Before submitting for OAuth verification**, that host has to be verified in Google Search
Console and set as the app's homepage on the OAuth consent screen.

## OAuth verification checklist

Use these URLs in Google Cloud Console:

- Homepage: `https://zhiyao92.github.io/firedash-landing/`
- Privacy policy: `https://zhiyao92.github.io/firedash-landing/privacy.html`
- Terms of service: `https://zhiyao92.github.io/firedash-landing/terms.html`
- Support URL: `https://zhiyao92.github.io/firedash-landing/#support`
- Data deletion instructions: `https://zhiyao92.github.io/firedash-landing/data-deletion.html`

Before submitting:

- Verify `zhiyao92.github.io` or the custom domain in Google Search Console.
- Ensure the OAuth consent screen app name says `FireDash`.
- Add every requested scope and justify each one using the feature that needs it.
- Record a demo video showing Google sign-in, the consent screen, project selection and each Firebase screen that uses sensitive scopes.
- Confirm the privacy policy link on the homepage matches the privacy policy URL in Google Cloud Console.
