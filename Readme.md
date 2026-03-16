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
