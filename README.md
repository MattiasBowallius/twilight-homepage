# Twilight Challenge

Webbplats för kappseglingen **Twilight Challenge** – 80 NM nattsegling i Öresund med start och mål i Lomma (lördag 30 maj 2026, start 15:00). Innehåller tävlingsinfo, banbeskrivning, Seglingsföreskrifter och anmälan.

Statisk webbplats (HTML, CSS, JS). Ingen build-steg.

## Local development

Open `index.html` in a browser, or run a simple server:

```bash
# Python 3
python3 -m http.server 8000

# or npx (Node)
npx serve .
```

Then visit http://localhost:8000

## Sign-up form

The race sign-up form is set up to work with [Formspree](https://formspree.io/) (free tier: 50 submissions/month). To enable it:

1. Sign up at [formspree.io](https://formspree.io/) and create a new form.
2. Copy your form ID (e.g. `xjvglkqa` from `https://formspree.io/f/xjvglkqa`).
3. In `index.html`, find the sign-up form and replace `YOUR_FORM_ID` in the `action` attribute with your form ID:
   `action="https://formspree.io/f/YOUR_FORM_ID"`

Submissions will be sent to your Formspree email. You can also use another form backend (e.g. Netlify Forms, Google Forms) by changing the form `action` and field `name` attributes.

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
