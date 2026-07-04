# Scrapio Docs

Source for the [Scrapio](https://scrapio.dev) API documentation, built with [Mintlify](https://mintlify.com) and deployed at [docs.scrapio.dev](https://docs.scrapio.dev).

## Structure

- `docs.json` — Mintlify site config: navigation, theme, branding, API settings.
- `openapi.json` — generated OpenAPI spec, powers the API Reference pages. **Do not edit by hand.**
- `*.mdx`, `guides/`, `api-reference/` — documentation content.
- `logo/`, `favicon.svg` — branding assets.

## OpenAPI spec

`openapi.json` is generated from the API source in the [scrapping-tool](https://github.com/xsronhou/scrapping-tool) repo (`npm run generate:openapi`, output at `openapi/openapi.json` there). A GitHub Actions workflow in that repo ([`sync-docs.yml`](https://github.com/xsronhou/scrapping-tool/blob/main/.github/workflows/sync-docs.yml)) pushes the latest spec here automatically whenever it changes on `main`. Manual edits to `openapi.json` in this repo will be overwritten by the next sync.

## Local preview

```
npx mintlify dev
```

## Deployment

This repo is connected to Mintlify's dashboard, which auto-deploys on every push to `main`.

Note: Mintlify reserves `/mcp` as a built-in MCP protocol endpoint for the docs site itself. The MCP client setup guide lives at `/mcp-server` to avoid colliding with it.
