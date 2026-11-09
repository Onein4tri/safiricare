# Setup and deployment

## Run locally

No install needed.

**Option A:** double-click `index.html`. It opens in your browser.

**Option B (recommended, behaves like a real server):**

```bash
cd safiricare
python3 -m http.server 8000
```

Open http://localhost:8000

## Deploy for free (GitHub Pages)

1. Push this repository to GitHub.
2. In the repository, go to **Settings → Pages**.
3. Under "Build and deployment", set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**.
4. Save. After about one minute the site is live at `https://<username>.github.io/safiricare/`.

Note: GitHub Pages makes the site public. The brief says the repository stays private at first. A private repository can still use Pages on a paid GitHub plan; otherwise deploy to Netlify or Vercel (both have free tiers and support private repositories).

## Edit content

Everything is in `index.html`. Each piece of text appears twice:

```html
<span data-en>English text</span>
<span data-fr>Texte français</span>
```

Change both. The language button at the top switches between them.

Colours are defined once at the top of the file under `:root`. Change `--primary`, `--secondary` and `--accent` to match the logo when it is confirmed.

## Replace the placeholders

Before showing this to partners, update:

- Contact email in the footer (currently `contact@safiricare.org`)
- Statistics in the hero and Problem section: verify each number against a current WHO or DHS source and add the source
- Certificate or validation wording once the official document is available
- Team section (not yet included, add when names and photos are confirmed)
