# roweai.ca — GitHub Pages

Marketing site for **https://roweai.ca**

## Host on GitHub Pages (correct setup)

### 1. Repo visibility (required)

GitHub Pages on a **private** repo needs **GitHub Pro** ($4/mo).

On the **free** plan, make this repo **Public**:

`Settings → General → Danger Zone → Change repository visibility → Public`

### 2. Turn on Pages

`Settings → Pages`

| Setting | Value |
|---------|--------|
| Source | Deploy from a branch |
| Branch | `main` |
| Folder | `/ (root)` |
| Custom domain | `roweai.ca` |

Wait for the green DNS check, then enable **Enforce HTTPS**.

The `CNAME` file in this repo already contains `roweai.ca`.

### 3. GoDaddy DNS (replace Render records)

**Delete** any A records pointing to `216.24.57.x` (Render).

**Delete** the CNAME for `www` → `ai-platform-frontend-uaaa.onrender.com`.

**Add** these records:

| Type | Name | Value | TTL |
|------|------|--------|-----|
| A | `@` | `185.199.108.153` | 1 Hour |
| A | `@` | `185.199.109.153` | 1 Hour |
| A | `@` | `185.199.110.153` | 1 Hour |
| A | `@` | `185.199.111.153` | 1 Hour |
| CNAME | `www` | `dgrowe-ai.github.io` | 1 Hour |

### 4. Remove roweai.ca from Render

In Render → **ai-platform-frontend-uaaa** → Settings → Custom Domains:

**Remove** `roweai.ca` and `www.roweai.ca`.

The app stays at: `https://ai-platform-frontend-uaaa.onrender.com`

### 5. Wait and test

DNS can take 15–60 minutes. Then:

- https://roweai.ca — full marketing homepage
- https://roweai.ca/instant-demo/ — demo page
- Hard refresh: **Ctrl+Shift+R**

## Do NOT point roweai.ca at Render

roweai.ca must use **GitHub Pages** only. The app platform is a separate URL on Render.
