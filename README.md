# Shovel Group: coming soon page

A temporary one-page site for shovelgroup.com, so the domain shows a real business website
(Apple Developer enrollment checks this). Plain HTML, no build step. Separate from the app stack.

Preview locally: `python3 -m http.server 4321` in this folder, then open http://localhost:4321

## Publish on GitHub Pages (free)

1. Create a new public GitHub repo, e.g. `shovelgroup-site`, and push the contents of this folder
   to its `main` branch (the files at the repo root, including `CNAME` and `.nojekyll`).
2. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Custom domain: `shovelgroup.com` (already set by the `CNAME` file).
4. At your DNS provider, add these records. Leave the Zoho MX, SPF and verification records alone.

   | Type  | Name | Value                   |
   |-------|------|-------------------------|
   | A     | @    | 185.199.108.153         |
   | A     | @    | 185.199.109.153         |
   | A     | @    | 185.199.110.153         |
   | A     | @    | 185.199.111.153         |
   | CNAME | www  | YOUR-GITHUB-USERNAME.github.io |

   Remove any other A or AAAA records on `@` (often a registrar "parked" page).
5. Once GitHub shows the domain as verified, tick "Enforce HTTPS" (the certificate can take up to an hour).

When the real app launches, shovelgroup.com moves to the production server and this repo retires.
