# Gambit Marketing

One-page site. No build step, no dependencies: `index.html` plus the files in `assets/`.

## Edit

- **Email address**: search `index.html` for `gambitmkt07@gmail.com` (it appears twice, in the contact link and the form action) and replace both.
- **Social links**: the three `href="#"` links in the footer.
- **Copy**: everything is plain text in `index.html`.
- **Logo**: the knight emblem used in the header, hero and favicon is embedded in the CSS as a data URI (`--mark`). The original upload is kept at `assets/logo-source.png`.

## Publish

The site is served by GitHub Pages at **https://gambitmarketing.ca** (the `CNAME` file holds the domain).

One-time setup:

1. GitHub: Settings → Pages → Build and deployment → Source: "Deploy from a branch" → pick the branch and `/ (root)` → Save. Under "Custom domain" enter `gambitmarketing.ca` and Save. Once the DNS check passes, tick "Enforce HTTPS".
2. Registrar (WHC): in the DNS zone for `gambitmarketing.ca`, add four `A` records for `@` pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, and one `CNAME` record for `www` pointing to `azogaj06.github.io`. Remove any parking `A` or `CNAME` records on `@` and `www` first.

After that, every push to the branch goes live within a minute or two.

## Contact form

The form has no backend. Submitting opens the visitor's mail app with the message pre-filled (a `mailto:` link). If you want submissions delivered without a mail app, swap the form `action` for a service like Formspree or Basin.
