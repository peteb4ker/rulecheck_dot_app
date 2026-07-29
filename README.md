# rulecheck.app

Marketing site for RuleCheck, a free, fully offline rules reference for trading
card game players and judges.

Static HTML and hand-written CSS. No build step, no dependencies, no JavaScript.

> The repo is named `rulecheck_dot_app` rather than `rulecheck.app` because
> macOS treats `.app` directories as application bundles.

## Layout

```
index.html            landing page
privacy.html          privacy policy
404.html              not-found page
assets/css/site.css   all styling; palette and type tokens in :root
assets/favicon.svg
CNAME                 custom domain for GitHub Pages
.nojekyll             serve files as-is, no Jekyll processing
```

## Local preview

Open `index.html` directly, or serve it so root-relative paths behave the same
as production:

```bash
python3 -m http.server 8000
```

## Deployment

GitHub Pages serves the root of `main` at https://rulecheck.app. Every push to
`main` publishes. `www` and plain HTTP both redirect to the canonical HTTPS
apex.

DNS is at Porkbun: four A records and four AAAA records on the apex pointing at
GitHub's Pages addresses, plus a `www` CNAME to `peteb4ker.github.io`. See
[GitHub's apex domain documentation](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain)
for the current addresses.
