# HadalCore LLC Website

Simple, professional site for **HadalCore.com** — custom computer programming services (541511).

## What’s included

- **index.html** — Single-page site: hero, services, about, contact
- **styles.css** — Brand styling (blues, dark theme) and layout
- **assets/logo.png** — Your HadalCore logo

## Run locally

Open `index.html` in a browser, or use a local server:

```bash
# Python
python -m http.server 8000

# Node (npx)
npx serve .
```

Then visit `http://localhost:8000`.

## Host on GitHub and use HadalCore.com (recommended)

Use **GitHub Pages** to host the site for free, then point your domain HadalCore.com to it.

### 1. Put the site on GitHub

1. Create a new repository on [GitHub](https://github.com/new) (e.g. `hadalcore-website` or `hadalcore.com`). Don’t add a README, .gitignore, or license.
2. In this project folder, point the remote at your new repo and push (the initial commit is already done):

   ```powershell
   git remote set-url origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git push -u origin main
   ```

   Replace `YOUR_USERNAME` and `YOUR_REPO_NAME` with your GitHub username and repo name.

### 2. Turn on GitHub Pages

1. In the repo on GitHub: **Settings** → **Pages** (left sidebar).
2. Under **Build and deployment**:
   - **Source**: Deploy from a branch
   - **Branch**: `main` (or `master`) — folder: **/ (root)**
3. Click **Save**. The site will be at `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/` until you add a custom domain.

### 3. Use your domain HadalCore.com

GitHub checks **both** the main domain and the **www** subdomain (“alternate name”). You must configure **both** at your DNS provider.

1. In the same **Pages** settings, under **Custom domain**, type: `hadalcore.com` and click **Save**.
2. At your DNS provider (e.g. **Namecheap**), do the following.

   **A. Apex domain (hadalcore.com)**  
   - Remove any existing **A** record for `@` (or `hadalcore.com`) that points to a parking or other IP.  
   - Add these **four A records** (same Name/Host for all four; only the Value changes):

   | Type | Name/Host | Value           |
   |------|-----------|-----------------|
   | A    | `@`       | `185.199.108.153` |
   | A    | `@`       | `185.199.109.153` |
   | A    | `@`       | `185.199.110.153` |
   | A    | `@`       | `185.199.111.153` |

   **B. www (www.hadalcore.com)**  
   - Remove any existing **CNAME** for `www`.  
   - Add **one CNAME** record. The value must be exactly (all lowercase, no `https://`, no path):

   | Type  | Name/Host | Value                  |
   |-------|-----------|------------------------|
   | CNAME | `www`     | `hadalcore.github.io`  |

   In Namecheap, enter **hadalcore.github.io** in the Value/Target field (some DNS require a trailing dot: `hadalcore.github.io.`). Do **not** use `HadalCore.github.io` or the repo URL.

   **Namecheap:** Domain List → **Manage** next to hadalcore.com → **Advanced DNS**. Delete the old A and CNAME records above, then add the 4 A records and the CNAME as in the tables. Use `@` for the A records and `www` for the CNAME name.

3. Wait 5–30 minutes (sometimes up to 24 hours). In GitHub **Pages** settings, check **Enforce HTTPS** once the domain shows as verified.

After DNS propagates, **https://hadalcore.com** and **https://www.hadalcore.com** will work. Updates: edit files, commit, and push to `main`; GitHub Pages will redeploy automatically.

## Customization

- **Contact email**: In `index.html`, change `contact@hadalcore.com` to your real address.
- **Logo**: Replace `assets/logo.png` with a new file (same name) to keep the same look.
- **Colors**: Edit the `:root` variables in `styles.css` to tweak blues and backgrounds.

## License

© HadalCore LLC. All rights reserved.
