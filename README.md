# yougoboom.app — Static Website

Two pages:
- `/` → index.html (landing page)
- `/privacy` → privacy/index.html (privacy policy)

---

## How to deploy to Cloudflare Pages

### Step 1 — Push to GitHub

Open Terminal, cd into this folder, and run:

```
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-GITHUB-USERNAME/yougoboom-website.git
git push -u origin main
```

(Create the empty GitHub repo first at github.com/new — name it yougoboom-website, leave it empty, no README.)

### Step 2 — Connect to Cloudflare Pages

1. Go to dash.cloudflare.com → Workers & Pages
2. Click Create application → Pages tab → Import an existing Git repository
3. Select your yougoboom-website repo → Begin setup
4. Set these values:
   - Production branch: `main`
   - Build command: `exit 0`
   - Build output directory: `/` (just a forward slash, or leave blank)
5. Click Save and Deploy

Cloudflare will give you a *.pages.dev URL to preview it.

### Step 3 — Connect your yougoboom.app domain

Because you bought the domain through Cloudflare, this is automatic:

1. In your Pages project, go to Custom domains tab
2. Click Set up a custom domain
3. Type: yougoboom.app → Continue
4. Cloudflare will detect the domain is already on your account and configure the DNS record automatically
5. Also add: www.yougoboom.app (optional, redirects to apex)

That's it. SSL is automatic. Usually live within a few minutes.

### Future updates

Any time you change index.html or the privacy page, just:

```
git add .
git commit -m "Update site"
git push
```

Cloudflare Pages redeploys automatically on every push to main.
