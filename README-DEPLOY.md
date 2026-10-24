# Dadsthatcode website deployment

Static HTML/CSS site, with no build step or third-party runtime dependencies.

## Cloudflare Pages
1. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git.
2. Choose GitHub account **dadsthatcode**, repository **dadsthatcode-website**, production branch **main**.
3. Framework preset: **None**. Build command: **leave blank**. Build output directory: **/** (repository root; some UI versions use an empty field or `.`).
4. Deploy and check the temporary *.pages.dev URL.
5. In the Pages project → Custom domains → Add **dadsthatcode.com** and optionally **www.dadsthatcode.com**. Follow Cloudflare's DNS prompts. Enable redirects so only one canonical hostname is used.
6. Verify https://dadsthatcode.com, https://dadsthatcode.com/cordkintv/, and https://dadsthatcode.com/privacy.html, including mobile layout and HTTPS.
7. In Google Search Console, add domain property dadsthatcode.com and verify using the offered DNS TXT record in Cloudflare DNS. Continue the Google Play Console website verification workflow with the same Google account/property.

## Notes
- The site is informational; it does **not** offer IPTV subscriptions or stream content.
- CORDKIN TV copy clearly marks the product as coming soon and in development. Do not claim features have shipped until they have been tested and released.
- The website privacy notice covers the company website only. The CORDKIN TV app privacy and terms pages are pre-release drafts and require production data-flow, SDK, retention, billing and provider-rights audits before publishing app-store disclosures.
- The `_headers` file is consumed by Cloudflare Pages for response security headers.
- Never commit secrets, authentication keys, or backend .env files.

## CORDKIN TV launch page
- Product URL: `https://dadsthatcode.com/cordkintv/` (source: `cordkintv/index.html`).
- Estimated roadmap: web and compatible Google Play Android TV/phone/tablet devices on December 1, 2026; Roku on January 1, 2027; iOS and iPadOS on February 1, 2027.
- These are targets only. Update the public dates before they become stale; do not imply app-store review or platform availability is already complete.

## CORDKIN TV legal and privacy release gates
- App privacy: `/cordkintv/privacy/`; Terms of Use and Recording Responsibility: `/cordkintv/terms/`; Account deletion information: `/cordkintv/account-deletion/`.
- These public pages are **pre-release drafts**, not a statement that production data flows have been audited or that a user has accepted the terms.
- Verify actual user/stream-provider credential flows and configured source/EPG defaults. Do not assert that all sources are user-supplied if production configuration embeds a third-party source.
- Verify AWS storage/recording lifecycle, shared-owner media behavior, media-access controls, SDKs, diagnostic logs, subprocessor inventory, deletion/backup retention, and whether the final privacy disclosures are accurate.
- Implement in-app account deletion for supported phone/tablet apps, functional web deletion requests, and operational backend deletion; do not claim completion before testing.
- Present active terms version and capture affirmative user acceptance in app; the existing backend `GET /terms/status` and `POST /terms/accept` APIs are integration starting points.
- Require an explicit authorized-recording confirmation in the client before first recording/scheduling; no pre-checked consent. Reinforce provider terms, copyright rights, and applicable law.
- Before cloud recording for public customers, obtain legal review of copyright/secondary-liability exposure, repeat-infringer implementation, notice-and-takedown, and whether DMCA designated-agent registration is needed for safe-harbor eligibility.
- Have qualified counsel review final limitations-of-liability language, arbitration/governing law as appropriate, and the actual provider integrations.
