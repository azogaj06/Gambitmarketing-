# Deploying gambitmarketing.ca — handoff notes

These notes are for whoever (or whichever Claude session) finishes the launch. Everything in the repo is ready. Two things remain, and both are done in a web browser while logged in as the owner.

## What is already done

- The site is a single `index.html` plus `assets/`, on branch `claude/eloquent-curie-ro1fx0` (the repo's default branch).
- `CNAME` contains `gambitmarketing.ca`, so GitHub Pages will serve the site under that domain once Pages is turned on.
- The page's canonical URL and share image already point at `https://gambitmarketing.ca/`.
- An attempt to enable Pages from a GitHub Actions workflow failed with "Resource not accessible by integration". Pages must be enabled by hand in the repo settings.

## Step 1 — turn on GitHub Pages (github.com)

1. Open https://github.com/azogaj06/Gambitmarketing-/settings/pages
2. Under **Build and deployment**:
   - Source: **Deploy from a branch**
   - Branch: **claude/eloquent-curie-ro1fx0**, folder **/ (root)**
   - Click **Save**.
3. Under **Custom domain**, type `gambitmarketing.ca` and click **Save**.
   GitHub will show "DNS check in progress" or a failure until Step 2 is done. That is expected.
4. Come back after Step 2 has propagated (see Step 3) and tick **Enforce HTTPS**.

## Step 2 — point the domain at GitHub (WHC, Web Hosting Canada)

1. Log in at https://clientzone.whc.ca and open the domain **gambitmarketing.ca** (Domains → My Domains → Manage, then the DNS / Zone Editor for the domain).
2. Leave the nameservers alone. Do not remove MX or TXT records. Only the `@` and `www` entries below change.
3. Delete any existing **A** record on `@` (the bare domain) and any existing **A** or **CNAME** record on `www`. New WHC domains are usually parked on a WHC server; those are the records to remove.
4. Add these records (TTL can stay at the default):

   | Type  | Name / Host | Value                |
   |-------|-------------|----------------------|
   | A     | @           | 185.199.108.153      |
   | A     | @           | 185.199.109.153      |
   | A     | @           | 185.199.110.153      |
   | A     | @           | 185.199.111.153      |
   | CNAME | www         | azogaj06.github.io   |

   Some WHC screens want the host written as `gambitmarketing.ca.` instead of `@`, and the CNAME value as `azogaj06.github.io.` with a trailing dot. Either form is fine.
5. Save.

## Step 3 — verify

- DNS usually propagates within an hour, sometimes up to 24 h.
- https://github.com/azogaj06/Gambitmarketing-/settings/pages should show "DNS check successful". Then tick **Enforce HTTPS** (it may take a further few minutes for the certificate to issue).
- https://gambitmarketing.ca and https://www.gambitmarketing.ca should both open the site with a padlock.

After that, every push to the branch is live within a minute or two. No build step, no further setup.
