# Publishing to GitHub Pages

Five steps to get this live at `https://jessicacarin.github.io/b2b-attribution-calculator/`

---

## Step 1 — Create the repository

1. Go to [github.com/new](https://github.com/new)
2. Set the repository name to: `b2b-attribution-calculator`
3. Set visibility to **Public** (required for free GitHub Pages)
4. Do NOT initialize with a README (you already have one)
5. Click **Create repository**

---

## Step 2 — Push the files

From your terminal, in the folder where you downloaded these files:

```bash
git init
git add .
git commit -m "Initial commit: B2B attribution calculator"
git branch -M main
git remote add origin https://github.com/jessicacarin/b2b-attribution-calculator.git
git push -u origin main
```

---

## Step 3 — Enable GitHub Pages

1. In your new repo, click **Settings** (top nav)
2. In the left sidebar, click **Pages**
3. Under "Branch," select `main` and folder `/ (root)`
4. Click **Save**

GitHub will show a green banner with your live URL within 1–2 minutes:
`https://jessicacarin.github.io/b2b-attribution-calculator/`

---

## Step 4 — Add the live URL to your README

Once it's live, open `README.md` and confirm this line at the top already points to the right URL:

```markdown
**[Live demo →](https://jessicacarin.github.io/b2b-attribution-calculator/)**
```

Commit and push if you make any changes:

```bash
git add README.md
git commit -m "Update live demo URL"
git push
```

---

## Step 5 — Add a description and topics to the repo

On your repo's main page, click the gear icon next to "About" (top right of the file list).

- **Description:** `Interactive B2B marketing attribution calculator — model pipeline revenue across first touch, last touch, linear, time decay, and U-shaped frameworks`
- **Website:** `https://jessicacarin.github.io/b2b-attribution-calculator/`
- **Topics:** `marketing`, `demand-generation`, `attribution`, `b2b-marketing`, `marketing-analytics`, `marketing-ops`

Topics help the repo surface in GitHub search and show up under your profile's contribution activity.

---

## Done

Your repo will now show:
- A live, interactive tool at a public URL you can link from your resume and LinkedIn
- A README that explains the attribution math and use cases
- Clean, readable source code that shows MarTech fluency
- GitHub Pages deployment (signals you know how to ship, not just write code)

Link it from your portfolio at `jessicacarin.github.io` and pin it to your GitHub profile.
