# Simple Manual Deployment

Copy and paste these commands one by one:

## Step 1: Clone Your Repo (if you don't have it)

```bash
cd ~
git clone https://github.com/saiteja313/portfolio-penugonda-dev.git
cd portfolio-penugonda-dev
```

## Step 2: Clean Old Files

```bash
rm -rf content/ themes/ config.toml static/ templates/
```

## Step 3: Download Files from Claude

1. Download these 3 files from Claude:
   - `index.html`
   - `images/1579699755133.jpeg`
   - `CNAME`

2. Place them in your `portfolio-penugonda-dev` folder:
   ```
   portfolio-penugonda-dev/
   ├── index.html          ← Put here
   ├── CNAME              ← Put here
   └── images/
       └── 1579699755133.jpeg  ← Put here (create images folder first)
   ```

## Step 4: Create Images Folder

```bash
mkdir -p images
```

Then copy your photo into `images/1579699755133.jpeg`

## Step 5: Verify Files

```bash
ls -la
# You should see:
# - index.html
# - CNAME
# - images/ (with your photo inside)
```

## Step 6: Commit and Push

```bash
git add .
git commit -m "Deploy modern portfolio"
git push origin main
```

## Step 7: Enable GitHub Pages

1. Open: https://github.com/saiteja313/portfolio-penugonda-dev/settings/pages
2. Under "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
   - Click **Save**
3. Under "Custom domain":
   - Enter: `www.penugonda.dev`
   - Click **Save**
4. Wait a minute, then check **Enforce HTTPS**

## Done! 🎉

Wait 2 minutes, then visit:
- https://www.penugonda.dev
- https://saiteja313.github.io/portfolio-penugonda-dev

---

## If You Get Permission Errors

You need to authenticate Git:

```bash
# Use GitHub CLI (easiest)
gh auth login

# Or configure Git with your credentials
git config --global user.name "saiteja313"
git config --global user.email "saiteja313@gmail.com"
```

When pushing, GitHub will ask for your password. Use a **Personal Access Token** instead:

1. Go to: https://github.com/settings/tokens
2. Click "Generate new token (classic)"
3. Give it a name: "Portfolio Deploy"
4. Check: `repo` (all)
5. Click "Generate token"
6. Copy the token
7. Use it as your password when Git asks

---

## Alternative: Upload via Web

Don't want to use Git? Upload via GitHub website:

1. Go to: https://github.com/saiteja313/portfolio-penugonda-dev
2. Delete old files (content/, themes/, config.toml)
3. Click "Add file" → "Upload files"
4. Drag `index.html` and `CNAME`
5. Create `images` folder
6. Upload `1579699755133.jpeg` into images folder
7. Enable GitHub Pages (Step 7 above)

Done!
