# Project instructions for coding agents

## Cloudflare documentation

Cloudflare Workers, Agents, Workflows, Durable Objects, and Workers AI APIs change frequently. Before implementing or changing Cloudflare-specific behavior, retrieve the current official documentation for the product involved and follow the linked product guidance. Check the product's platform limits when a change depends on quotas or runtime ceilings. Prefer official Cloudflare sources.

Useful references:

- Workers: <https://developers.cloudflare.com/workers/>
- Agents SDK: <https://developers.cloudflare.com/agents/>
- Durable Objects best practices: <https://developers.cloudflare.com/durable-objects/best-practices/rules-of-durable-objects/>
- Workflows best practices: <https://developers.cloudflare.com/workflows/build/rules-of-workflows/>
- Workers AI: <https://developers.cloudflare.com/workers-ai/>

## Development commands

- `npm run dev` starts the Vite and Cloudflare local runtime.
- `npm run check` runs formatting, Oxlint, and TypeScript checks.
- `npm run types` regenerates Cloudflare binding types after changing `wrangler.jsonc`.
- `npm run deploy` builds and deploys the Worker to the Wrangler-selected account. Review the target account and deployment configuration first.

Workers AI is configured as a remote binding for local development. Model calls may use the authenticated Cloudflare account. Durable Object and Workflow state in local development remains local to the runtime.

## Local runtime inspection

When the local runtime is active, its Local Explorer API is available at the URL printed in the dev output. Useful read-only endpoints include:

- `GET /cdn-cgi/local/explorer/api/local/workers` lists local Workers and bindings.
- `GET /cdn-cgi/local/explorer/api/workflows` lists local Workflows.
- `GET /cdn-cgi/local/explorer/api/workers/durable_objects/namespaces` lists Durable Object namespaces.
- `POST /cdn-cgi/local/explorer/api/local/observability/query` runs a read-only `SELECT` or `WITH` query over local `spans` and `logs`.

The full API schema is available at `GET /cdn-cgi/local/explorer/api` when additional endpoint details are needed.
