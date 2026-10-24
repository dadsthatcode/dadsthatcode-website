# Dadsthatcode website deployment

Static HTML/CSS site, with no build step or third-party runtime dependencies.

## Cloudflare Pages
1. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git.
2. Choose GitHub account **dadsthatcode**, repository **dadsthatcode-website**, production branch **main**.
3. Framework preset: **None**. Build command: **leave blank**. Build output directory: **/** (repository root; some UI versions use an empty field or `.`).
4. Deploy and check the temporary *.pages.dev URL.
5. In the Pages project → Custom domains → Add **dadsthatcode.com** and optionally **www.dadsthatcode.com**. Follow Cloudflare's DNS prompts. Enable redirects so only one canonical hostname is used.
6. Verify https://dadsthatcode.com and https://dadsthatcode.com/privacy.html, including mobile layout and HTTPS.
7. In Google Search Console, add domain property dadsthatcode.com and verify using the offered DNS TXT record in Cloudflare DNS. Continue the Google Play Console website verification workflow with the same Google account/property.

## Notes
- The site is informational; it does **not** offer IPTV subscriptions or stream content.
- CORDKIN TV copy clearly marks the product as coming soon and in development. Do not claim features have shipped until they have been tested and released.
- The website privacy notice covers this website only; publish a separate policy describing actual mobile/TV app behavior before releasing CORDKIN TV.
- The `_headers` file is consumed by Cloudflare Pages for response security headers.
- Never commit secrets, authentication keys, or backend .env files.
