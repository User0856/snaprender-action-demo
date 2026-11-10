# SnapRender Action demo: screenshots of every pull request preview

A working example of the [SnapRender Screenshot](https://github.com/marketplace/actions/snaprender-screenshot) GitHub Action.

On every pull request, [`.github/workflows/preview.yml`](.github/workflows/preview.yml):

1. deploys the `site/` folder as a preview on GitHub Pages (`/pr-preview/pr-<number>/`, with [rossjrw/pr-preview-action](https://github.com/rossjrw/pr-preview-action)),
2. waits until the preview serves the pull request's commit,
3. captures it full page on desktop and on an iPhone 15 Pro with SnapRender,
4. posts both screenshots as a comment on the pull request and keeps the files as a workflow artifact.

Fieldnote, the site in `site/`, is a made-up product used only for this demo.

## Use it in your repository

1. Get a SnapRender API key (the free plan includes 200 captures a month): https://app.snap-render.com/auth/signup
2. Add it as a repository secret named `SNAPRENDER_API_KEY` (Settings, Secrets and variables, Actions).
3. Copy the workflow and point `urls` at your own preview URL. On Vercel, Netlify or Cloudflare Pages, trigger on `deployment_status` and use `github.event.deployment_status.environment_url`.

Full list of inputs and outputs: https://github.com/User0856/snaprender-screenshot-action
