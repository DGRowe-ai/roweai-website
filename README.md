# roweai.ca — GitHub Pages

## One-time setup (you must click these in GitHub)

### Step A — Enable Pages (2 clicks)

1. Open: **https://github.com/DGRowe-ai/roweai-website/settings/pages**
2. Under **Build and deployment** → **Source**, choose **Deploy from a branch**
3. **Branch:** `main` → folder **`/ (root)`** → Save

Every push to `main` rebuilds the site automatically (usually within 1–2 minutes).

### Step B — Repo must be Public (free plan)

If the repo is **private** and you are on GitHub Free, Pages will not work.

**Settings → General → Danger Zone → Change visibility → Public**

(Or upgrade to GitHub Pro to keep it private.)

### Step C — Custom domain

On the same Pages settings page:

- **Custom domain:** `roweai.ca`
- Wait for green check → **Enforce HTTPS**

The `CNAME` file in this repo already says `roweai.ca`.

### Step D — GoDaddy DNS (switch back from Render)

**Delete** Render records (`216.24.57.x` A records, www → Render CNAME).

**Add:**

| Type | Name | Value |
|------|------|--------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `dgrowe-ai.github.io` |

### Step E — Remove roweai.ca from Render

Render → **ai-platform-frontend-uaaa** → Custom Domains → **remove** roweai.ca

---

## After setup

- Site: **https://roweai.ca**
- App (billing/login): **https://ai-platform-frontend-uaaa.onrender.com**

Pushes to `main` auto-deploy from the `main` branch (root folder).
