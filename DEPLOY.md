# Deploy: Content Studio Landing Page

Push this folder to `github.com/Qlarify/Content-` and deploy to Vercel for the `content.qlarify.health` subdomain.

## One-time setup (run in your Mac Terminal)

The Cowork sandbox can't push to GitHub for permissions reasons. Run these commands locally on your Mac, in your own Terminal:

```bash
# Move into the folder
cd "/Users/vijayadutta/Campaign Planning/content-studio-deploy"

# Wipe any stale .git that the sandbox half-initialised
rm -rf .git

# Initialise fresh, on the main branch
git init -b main
git config user.email "info@qlarify.health"
git config user.name "Qlarify Health"

# Add the remote
git remote add origin https://github.com/Qlarify/Content-.git

# Stage and commit
git add .
git commit -m "Initial commit: Healthcare Content Studio landing page

- Hero: content + social + video as infrastructure
- Audit form (Web3Forms wired to info@qlarify.health)
- Video infrastructure section with patient-journey film + 4-stage framework
- Seven content pillars
- Three pricing tiers (Studio 2.99L / Studio+ 4.99L / Engine 7.99L)
- Trust layer: 4 anonymised testimonials + 10K+ / 17+ / 10+ credentials
- About + footer
"

# Push
git push -u origin main
```

If `git push` asks for credentials, use your GitHub username and a Personal Access Token (not your password). Create a token at https://github.com/settings/tokens with `repo` scope.

## Vercel setup (one-time)

1. In Vercel, click **Add New > Project**
2. Import the `Qlarify/Content-` repo
3. Framework preset: **Other** (or "No framework")
4. Root directory: leave as `./`
5. Build command: leave empty (static site)
6. Output directory: leave empty
7. Click **Deploy**

## Custom domain

1. After the first deploy succeeds, go to **Settings → Domains**
2. Add `content.qlarify.health`
3. Vercel will show the DNS record to add (CNAME pointing to `cname.vercel-dns.com`)
4. Add the CNAME at your DNS provider (the same place where `180days.qlarify.health` and `video.qlarify.health` are configured)
5. Wait 5-30 minutes for DNS to propagate and Vercel to provision SSL

## Future updates

After the first push, you can update the page directly through this folder:

```bash
cd "/Users/vijayadutta/Campaign Planning/content-studio-deploy"
# edit index.html or assets
git add .
git commit -m "Describe the change"
git push
```

Vercel auto-deploys on every push to `main`.

## Form submissions

Web3Forms delivers to `info@qlarify.health` using the access key embedded at line ~545 of `index.html`. Same access key the 180-days landing page uses. Test by submitting the audit form on the live site once after deploy.

## GA4 tracking

Already wired with measurement ID `G-61S9HK1N7X`. The `audit_request_submitted` event fires when the form's success redirect lands back on the page with `?submitted=1`.
