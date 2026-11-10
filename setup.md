# Setup notes (for developers only)

This file is for the person who maintains the website. SafiriCare's team does not need it to view the site.

## Open the site

Download `index.html` and double click it. It opens in the browser.

## Edit the text

Everything is in `index.html`. Each piece of text appears twice, once per language:

```html
<span data-en>English text</span>
<span data-fr>Texte français</span>
```

Change both. The language button at the top switches between them.

## Change the colours

Colours are defined once at the top of `index.html` under `:root`. Change `--primary`, `--secondary` and `--accent` to match the logo when it is confirmed.

## Put the site online (when SafiriCare is ready)

Putting the site online makes it visible to everyone, so do this only when the content is approved.

- Netlify or Vercel: free plans, work with a private repository.
- GitHub Pages: free for public repositories. Repository Settings, Pages, deploy from branch main, folder root.

## Still to confirm with SafiriCare

- Contact email in the footer (currently shows "Contact email to be confirmed")
- Exact official wording about registration and validation
- Logo and colours
- Team section (not yet included)
- French text proofread by a French speaker
- Fictional medical example checked by a clinician

## Rule for statistics

Only add a number to the page with its source next to it.
