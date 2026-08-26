# firedash-landing

Static landing page and privacy policy for **FireDash**, the iOS Firebase console.

Two files, no build step:

- `index.html` — what the app does and how it avoids wrecking production
- `privacy.html` — the privacy policy

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
