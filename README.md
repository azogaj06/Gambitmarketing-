# Gambit Marketing

One-page site. No build step, no dependencies: `index.html` plus the files in `assets/`.

## Edit

- **Email address**: `gambitmkt07@gmail.com` appears in the contact section (link and form action) and the footer. Search `index.html` to change it.
- **Instagram**: `https://www.instagram.com/shotbygambit/` is linked from the hero, the proof section, the contact section and the footer. Search `index.html` for `shotbygambit` to change it.
- **Proof clips**: drop short vertical videos into `assets/clips/` named `clip-1.mp4` to `clip-4.mp4` (9:16, muted, ideally under 3 MB each, 5 to 15 seconds). Optional poster frames go next to them as `clip-1.jpg` and so on. Until a file exists, its tile shows the emblem and "Watch on Instagram" and links to the profile. Clips play only while on screen and are muted, so they stay light on mobile.
- **Copy**: everything is plain text in `index.html`. The page order is: hero, the problem, the fix, what changes, the proof, why Gambit (the board), contact.
- **Logo**: the knight emblem used in the header, hero, favicon and clip tiles is embedded in the CSS as a data URI (`--mark`). The original upload is kept at `assets/logo-source.png`.

## Expanding later

When search or ads start bringing cold traffic, the natural additions are: a case-study page per client (problem, what we did, numbers), a pricing or packages page, and a short "how we work" page. Each section on the current page is already written as a headline plus proof, so each can grow into its own page without redesigning the home page.

## Publish

The site is served by GitHub Pages at **https://gambitmarketing.ca** (the `CNAME` file holds the domain). The one-time launch steps, for GitHub and for the WHC DNS panel, are in [DEPLOY.md](DEPLOY.md). After that, every push to the branch is live within a minute or two.

## Contact form

The form has no backend. Submitting opens the visitor's mail app with the message pre-filled (a `mailto:` link). If you want submissions delivered without a mail app, swap the form `action` for a service like Formspree or Basin.
