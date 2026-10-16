# GitHub Pages site base

Repository for the personal website published at **https://m-jethro.github.io/**.

This repository intentionally contains no website HTML or design yet. Upload your existing site files when you're ready.

## 1. Upload your website folder

Your website is a static site, so the key requirement is that **index.html must be in the repository root** (the top level beside this README), not buried inside a nested folder.

### Recommended: GitHub Desktop (best for folders and images)

1. Install GitHub Desktop: https://desktop.github.com/
2. In GitHub, open this repository and select **Code → Open with GitHub Desktop** (or use **File → Clone repository** and choose `M-Jethro/M-Jethro.github.io`).
3. Choose a local folder on your Mac for the repository and clone it.
4. Open the local repository folder in Finder.
5. Open your existing website folder in another Finder window.
6. Copy the **contents** of your website folder into the cloned repository folder. Copy `index.html`, CSS/JavaScript files, and image/assets folders while keeping their existing folder structure. Do not copy the website folder as an extra nested level unless your `index.html` is at the repository root.
7. If Finder asks whether to replace an existing file, review it first. Keep this README, `.nojekyll`, and any GitHub-generated `CNAME` file if present; do not overwrite them accidentally.
8. Open GitHub Desktop. Review the changed files, enter a summary such as `Add existing website files`, click **Commit to main**, then click **Push origin**.

After that, future changes follow the same cycle: edit your files in the local repository → commit → push. GitHub Pages will publish the pushed changes automatically once you enable it below.

### Alternative: Upload in the GitHub website

Open the repository, choose **Add file → Upload files**, and upload the files from your website folder. Be sure to upload `index.html` at the repository root and preserve relative paths for images, CSS and JavaScript. For many files or large image collections, GitHub Desktop is usually easier.

## 2. Enable GitHub Pages (one-time setup)

1. Open this repository: https://github.com/M-Jethro/M-Jethro.github.io
2. Select **Settings → Pages**.
3. In **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Set the branch to **main** and the folder to **/(root)**.
5. Click **Save**.

After an `index.html` is in the root, GitHub Pages should publish the site at https://m-jethro.github.io/. Check **Settings → Pages** or the repository Actions tab for publishing status. This repository is public, and anything published through Pages is publicly accessible.

## 3. Connect a GoDaddy domain

First decide whether you want the main address to be the bare domain (for example, `example.com`) or `www.example.com`. You can set up both and have GitHub redirect one to the other.

1. In the GitHub repository, open **Settings → Pages**.
2. Under **Custom domain**, enter your exact domain (for example, `example.com`) and click **Save**. Do this before changing the DNS records in GoDaddy. If GitHub asks for domain verification, follow its verification instructions first.
3. In GoDaddy, open **My Products → Domains → your domain → DNS / Manage DNS**.
4. For the bare domain (for example, `example.com`), create these four **A** records. Set **Name/Host** to `@`, and use the following values (one record per IP):
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
5. To support `www.example.com`, create a **CNAME** record with **Name/Host** `www` and **Value/Points to** `M-Jethro.github.io` (not the repository URL and not a URL containing `https://`).
6. Remove only conflicting old website records for `@` or `www` if they point elsewhere. Do not delete email-related DNS records (such as MX or email-verification TXT records).
7. Return to **Settings → Pages** and wait for the domain check to pass. Once available, enable **Enforce HTTPS**.

DNS updates can take up to 24 hours to propagate, and HTTPS may take additional time to become available.

**Important:** GitHub Pages is public static hosting, not private file storage. Don't commit credentials, API keys, confidential documents, or personal records. Keep the directory structure of images and other assets consistent with the paths used by your HTML.

## Helpful official guides

- GitHub Pages publishing source: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- GitHub custom domains and DNS: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- GitHub domain verification: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages
- GoDaddy DNS management: https://www.godaddy.com/help/manage-dns-records-680
