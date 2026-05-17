# GitHub Pages Deployment Setup

## Single-site repo

Use `.github/workflows/github-pages-single-site.yml` in a repository that contains one website at the repo root.

Steps:
1. Create a repository for a site.
2. Put `index.html` and `theme.css` at the repository root.
3. Add `.github/workflows/github-pages-single-site.yml` to the repo.
4. Push to `main`.
5. GitHub Actions will deploy the site automatically.

If the website files are in a subfolder, change `path: .` to `path: ./folder-name`.

## One repo for many sites

Yes — you can keep this entire code base in a single repository and publish all sites from one GitHub Pages deployment.

Use `.github/workflows/github-pages-multi-site.yml` in the repo root. It publishes the listed website folders together, and each site becomes available under its own path.

Example URLs:
- `https://<username>.github.io/<repo-name>/architecture/`
- `https://<username>.github.io/<repo-name>/business-consultant/`
- `https://<username>.github.io/<repo-name>/life-coach/`

To add another website later, create a new folder, place `index.html` and assets inside it, and push to `main`.

## Notes

- The workflow runs on `push` to `main`.
- GitHub Pages will use GitHub Actions as the deployment source.
- For a separate repo per website, copy the `single-site` workflow into each repo and keep `path: .`.
