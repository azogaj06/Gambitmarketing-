# Gambit Marketing

One-page site. No build step, no dependencies: `index.html` plus the files in `assets/`.

## Edit

- **Email address**: search `index.html` for `gambitmkt07@gmail.com` (it appears twice, in the contact link and the form action) and replace both.
- **Social links**: the three `href="#"` links in the footer.
- **Copy**: everything is plain text in `index.html`.
- **Logo**: the knight emblem used in the header, hero and favicon is embedded in the CSS as a data URI (`--mark`). The original upload is kept at `assets/logo-source.png`.

## Publish

The site is served by GitHub Pages at **https://gambitmarketing.ca** (the `CNAME` file holds the domain). The one-time launch steps, for GitHub and for the WHC DNS panel, are in [DEPLOY.md](DEPLOY.md). After that, every push to the branch is live within a minute or two.

## Contact form

The form has no backend. Submitting opens the visitor's mail app with the message pre-filled (a `mailto:` link). If you want submissions delivered without a mail app, swap the form `action` for a service like Formspree or Basin.
