# Twilight Homepage

A static website. No build step—just HTML, CSS, and JS.

## Local development

Open `index.html` in a browser, or run a simple server:

```bash
# Python 3
python3 -m http.server 8000

# or npx (Node)
npx serve .
```

Then visit http://localhost:8000

## Deploy (cheapest options)

**Free hosting** is the cheapest. All of these support custom domains and HTTPS.

| Option | Cost | Notes |
|--------|------|--------|
| **GitHub Pages** | **Free** | Push to a repo, enable Pages in repo Settings → Pages. Use `main` branch, `/ (root)` or `/docs`. |
| **Cloudflare Pages** | **Free** | Unlimited bandwidth. Connect Git or upload a folder. |
| **Netlify** | **Free** | Drag-and-drop or Git. Free tier has build/bandwidth limits. |
| **Vercel** | **Free** | Git-based, good for static and JAMstack. |

**Recommendation:** Use **GitHub Pages** (see below) for zero cost and minimal setup. No build step needed—GitHub serves your files as-is.

### Deploy with GitHub Pages

1. **Create a new repo** on GitHub (e.g. `twilight-homepage`). Don’t add a README or .gitignore—you already have files locally.

2. **Push this project** from your machine (run these in the project folder):

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/twilight-homepage.git
   git push -u origin main
   ```
   Replace `YOUR_USERNAME` and `twilight-homepage` with your GitHub username and repo name.

3. **Turn on Pages:** In the repo on GitHub, go to **Settings** → **Pages** (left sidebar). Under **Build and deployment**:
   - **Source:** Deploy from a branch
   - **Branch:** `main` / **Folder:** `/ (root)`
   - Click **Save**.

4. **Wait 1–2 minutes.** Your site will be at:
   - **Project site:** `https://YOUR_USERNAME.github.io/twilight-homepage/`
   - **User/org site:** If the repo is named `YOUR_USERNAME.github.io`, it’s `https://YOUR_USERNAME.github.io/`

Later: every `git push` to `main` will update the live site automatically.

### Quick deploy: Cloudflare Pages

1. Go to [pages.cloudflare.com](https://pages.cloudflare.com/).
2. **Create a project** → **Direct Upload**.
3. Drag the project folder (or a zip of it) and deploy.
4. Or connect your Git repo for automatic deploys on push.
