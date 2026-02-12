# Deploy to GitHub Pages (and use your own domain)

Follow these steps to put your Valentine game online and optionally use a custom domain.

---

## 1. Push the project to GitHub

### If you don’t have Git yet
- Install: [git-scm.com](https://git-scm.com/)

### In a terminal (PowerShell or Command Prompt), from the project folder:

```bash
cd "c:\Users\izabi\Desktop\skyesvday"

# Turn this folder into a Git repo
git init

# Stage all files
git add .

# First commit
git commit -m "Valentine game - initial commit"
```

### Create the repo on GitHub and connect it

1. Go to [github.com](https://github.com) and sign in (or create an account).
2. Click **New** (green “New repository”).
3. Name it whatever you like (e.g. `valentine-max`).
4. Leave it **empty** (no README, no .gitignore).
5. Click **Create repository**.

Then run (replace `YOUR_USERNAME` and `YOUR_REPO` with your GitHub username and repo name):

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git branch -M main
git push -u origin main
```

When asked, sign in to GitHub (browser or token). After this, your code is on GitHub.

---

## 2. Turn on GitHub Pages

1. Open your repo on GitHub.
2. Click **Settings**.
3. In the left sidebar, click **Pages** (under “Code and automation”).
4. Under **Build and deployment** → **Source**, choose **Deploy from a branch**.
5. Under **Branch**, pick **main** and **/ (root)**.
6. Click **Save**.

After a minute or two, your site will be at:

**`https://YOUR_USERNAME.github.io/YOUR_REPO/`**

This project includes an **index.html** (same as the main game), so opening that URL will load the game automatically.

---

## 3. Use a custom domain (optional)

1. In the same **Settings → Pages** section, find **Custom domain**.
2. Type your domain (e.g. `valentine.yourdomain.com` or `yourdomain.com`).
3. Click **Save**.
4. GitHub will show a message like “DNS check still in progress” and show the record you need.

### What to add at your domain registrar

- **If GitHub tells you to add a CNAME record**  
  - Name/host: the subdomain you use (e.g. `valentine` or `www`).  
  - Value/target: `YOUR_USERNAME.github.io`

- **If you use an apex domain (e.g. `yourdomain.com`)**  
  GitHub often suggests **A records** pointing to:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`

After you add the records, wait 5–60 minutes. Then in **Settings → Pages**, click **Enforce HTTPS** if you want the site to load only over HTTPS.

---

Visiting your Pages URL (or your custom domain) will show the Valentine game.
