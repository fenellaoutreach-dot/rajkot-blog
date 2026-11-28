# Rajkot.blog

Static, responsive starter for a Rajkot city portal and local news publication.

## Deploy free to Cloudflare Pages

1. Create a GitHub repository (e.g. `rajkot-blog`) and upload `index.html`, `robots.txt`, `sitemap.xml` to its root.
2. In Cloudflare Dashboard > Workers & Pages > Create > Pages > Connect to Git, select the repository.
3. Select **no framework**, leave build command empty, set output directory to `/` (repository root). If your Cloudflare UI requires a build command, use `exit 0`.
4. Deploy and check the generated `*.pages.dev` URL.
5. In Pages > Custom domains, add `rajkot.blog` and follow the displayed DNS instructions.
6. At Dynadot, update nameservers to the exact pair Cloudflare provides **only after** adding the domain to Cloudflare and checking existing DNS/email records. DNS propagation may take time.

## Editorial note
This is a launch-ready design **starter**, not a live news feed. Add dated, sourced, reviewed articles before claiming news coverage. The editorial email is a placeholder and must be configured before public use.

## Permanent homepage heading

Keep exactly one homepage H1 inside `<main>`: `<h1 id="homepage-heading">Rajkot News, Travel, Food, Business &amp; Education</h1>`. It belongs to the permanent `.home-intro` block, not the rotating `.feature` section. When updating the featured article, retain `<h2 id="hero-heading">` and its `aria-labelledby` relationship, and update only its title, description, label and link. Do not replace or regenerate the permanent H1. The live SEO audit independently checks the repository and deployed homepage against this contract on pushes and daily runs; it fails if the heading is missing, duplicated or changed.
