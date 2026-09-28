# ehoche.com

Personal site for Ezra Ehoche.

- `/` — Salesforce Developer portfolio (`index.html`)
- `/wedding` — Ebere & Ezra wedding page (`wedding/index.html`)

Plain HTML/CSS/JS. No build step, no dependencies. Works on GitHub Pages out of the box.

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `ehoche.com`).
2. Upload everything in this folder to the repo root (or push with git):
   ```
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/ehoche.com.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Source: Deploy from a branch → main / (root)**.
4. Custom domain: in **Settings → Pages**, enter `ehoche.com` (the `CNAME` file in this repo already matches). At your domain registrar, point the domain at GitHub Pages:
   - `A` records for `ehoche.com`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Optional `CNAME` record for `www` → `YOUR_USERNAME.github.io`
5. Tick **Enforce HTTPS** once the certificate is issued (can take a few minutes).

The site will be live at `https://ehoche.com` and the wedding page at `https://ehoche.com/wedding`.

## Things to edit before/after launch

Search for `✏️ EDIT` comments in the HTML — each marks a spot to update:

**`wedding/index.html`**
- Gallery — drop photos into `assets/wedding/` and replace each `<span class="soon">E &amp; E</span>` inside the `<figure>` tags with `<img src="../assets/wedding/photo1.jpg" alt="Ebere and Ezra">`.
- Venue — add it to The Details section when you're ready to share it.
- The RSVP phone number and account number are lightly obfuscated in the `<script>` at the bottom (reversed chunks) so bots scraping the page source don't harvest them; edit them there if they change.

**`index.html` (portfolio)**
- Contact email — currently `hello@ehoche.com`; change to whichever address you use.
- Experience entries use generic organisation descriptors (no employer names). Adjust wording as you like.

## Structure

```
├── index.html            # Portfolio landing page
├── wedding/
│   └── index.html        # Wedding page
├── assets/
│   ├── portfolio/        # (empty) portfolio images if you add any
│   └── wedding/          # (empty) drop wedding photos here
├── CNAME                 # Custom domain for GitHub Pages
├── .nojekyll             # Tells GitHub Pages to serve files as-is
└── README.md
```
