# Rowe AI Marketing Site (roweai.ca)

This repo is the **public marketing website** for roweai.ca — not the app platform.

## Important: hosting

**roweai.ca must be deployed from this repo**, not from `ai-platform-frontend`.

If roweai.ca points to `ai-platform-frontend-uaaa.onrender.com`, visitors will only see the chat widget page instead of the full marketing site.

### Deploy on Render (recommended for private GitHub repo)

1. [Render Dashboard](https://dashboard.render.com) → **New** → **Static Site**
2. Connect this `roweai-website` repository
3. Settings:
   - **Build command:** `echo "static site"`
   - **Publish directory:** `.` (root)
4. **Custom Domains:** add `roweai.ca` and `www.roweai.ca`
5. **Remove** `roweai.ca` from the `ai-platform-frontend` service custom domains (if attached there)

### DNS (GoDaddy)

Point roweai.ca to your **Render Static Site** URL (Render provides DNS instructions when you add the custom domain).

Do **not** point roweai.ca CNAME to `ai-platform-frontend-uaaa.onrender.com`.

### App platform (separate)

- Billing / login / dashboard: `https://ai-platform-frontend-uaaa.onrender.com`
- API: `https://ai-platform-backend-ulqs.onrender.com`
