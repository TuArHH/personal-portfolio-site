# For Deployment for Strato


Astro already **minifies everything** (HTML, CSS, JS) in production. No extra tools needed.

```bash
# 1 — Install dependencies (only needed once or after changes)
npm install

# 2 — Build the production site
npm run build
# → output lands in dist/
```


Then upload the **contents of `dist/`** to your Strato webspace via FTP (FileZilla, Cyberduck, or command line):


```bash
# Command-line FTP upload example (replace with your Strato credentials)
ftp -n your-strato-ftp-host << EOF
user your-username your-password
binary
cd /
mput dist/*
bye
EOF
```



**What gets uploaded from `dist/`:**

* `index.html` — full page, minified
* `_astro/index.[hash].css` — all styles, minified
* `TugrulArslan.webp` — your photo
* `favicon.svg` — B&W profile favicon

**Tip:** Each time you rebuild, the CSS filename changes (content hash). Always upload the full `dist/` folder fresh, not just individual files.


### Git commands


```bash
# Navigate to the project
cd "/Users/tugrularslan/Documents/_DEV/Cloud/Personal Landing Page/personal-portfolio-v2"

# Initialize git
git init

# Stage all files
git add .

# First commit
git commit -m "Initial commit: personal portfolio v2"

# Point to your GitHub repo
git remote add origin https://github.com/TuArHH/YOUR-REPO-NAME.git

# Push
git branch -M main
git push -u origin main or 
git push -u origin main --force
```
