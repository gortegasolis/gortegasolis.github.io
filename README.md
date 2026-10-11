# gortegasolis.github.io

Personal landing page, built with [Quarto](https://quarto.org/) and served at
<https://geomattr.org>.

## Structure

| File | Content |
|------|---------|
| `index.qmd` | Home page, with featured projects |
| `projects.qmd` | Projects listing |
| `tutorials.qmd` | Tutorials listing |
| `about.qmd` | Short bio and link to the CV |
| `data/projects.yml`, `data/tutorials.yml` | The entries shown in the listings |
| `_templates/cards.ejs` | Card layout used by all listings |
| `light.scss`, `dark.scss`, `styles.scss` | Theme colours and shared styles |

## Adding a project or tutorial

Add an entry to `data/projects.yml` or `data/tutorials.yml`:

```yaml
- title: My project
  description: One or two sentences.
  categories: [R package]
  website: https://gortegasolis.github.io/my-project/  # optional
  code: https://github.com/gortegasolis/my-project     # optional
  featured: true                                      # projects only: show on home page
```

## Building and publishing

Preview locally with `quarto preview`. Pushing to `main` renders the site and
deploys it to GitHub Pages through `.github/workflows/publish.yml`; in the
repository settings, set **Pages → Source** to **GitHub Actions**.

## Custom domain

Set `geomattr.org` under **Settings → Pages → Custom domain** (the `CNAME`
file is kept in the output as well). The domain's DNS needs:

- `A` records for `geomattr.org` → `185.199.108.153`, `185.199.109.153`,
  `185.199.110.153`, `185.199.111.153`
- `CNAME` record for `www` → `gortegasolis.github.io`

Once set, every project page (e.g. `gortegasolis.github.io/geomattR/`) is also
served under the domain (`geomattr.org/geomattR/`).
