# WGMLEARN Jekyll Site

This is a basic Jekyll site template configured for GitHub Pages. It resides in its own folder to keep the root of the repository clean.

## Local Development

If you have Ruby and Bundler installed, you can run this site locally:

1. Navigate to this directory: `cd docs`
2. Install dependencies: `bundle install`
3. Serve the site: `bundle exec jekyll serve`
4. View the site at `http://localhost:4000`

## Deployment

This site is configured to be automatically deployed via GitHub Actions to GitHub Pages. 
Check the `.github/workflows/deploy-pages.yml` file in the root of the repository for the deployment pipeline configuration.


## GitHub Actions Setup

Create a file at  .github/workflows/deploy-pages.yml  with the following content to enable deployment:

```yaml
name: Deploy Jekyll site to Pages

on:
  push:
    branches: ["main", "master"]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: '3.1'
          bundler-cache: true
          working-directory: './docs'
      - name: Setup Pages
        uses: actions/configure-pages@v5
      - name: Build with Jekyll
        working-directory: ./docs
        run: bundle exec jekyll build --baseurl "${{ steps.pages.outputs.base_path }}"
        env:
          JEKYLL_ENV: production
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./docs/_site

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```
I have created a basic Jekyll site template for you inside the docs directory to keep it cleanly separated from the rest of your repository's files.

Here is what was added to the docs folder:

_config.yml: The main configuration for the site, utilizing the default minima theme.
Gemfile: Configured to use standard Jekyll and the github-pages plugin for maximum compatibility.
index.md: The homepage template for the site.
README.md: Contains local development instructions and the deployment template.
Deployment Note: Due to security boundaries, I cannot automatically create the .github/workflows file. Instead, I've appended the exact GitHub Actions YAML you need directly into docs/README.md.

To enable the automated deployment to GitHub Pages:

Create a file at .github/workflows/deploy-pages.yml in your repository.
Copy the YAML code block provided at the bottom of docs/README.md into that file.
Commit and push the changes.
Ensure your repository settings in GitHub have Pages set to build from GitHub Actions (under Settings > Pages > Source).