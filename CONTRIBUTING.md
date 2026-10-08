# Contributing

Thanks for taking a look at RoleSignal. Focused bug fixes, accessibility improvements, and clear documentation are welcome.

## Before you open a pull request

- For changes to product behavior, the interface, or the Cloudflare setup, open an issue first so the scope can be agreed.
- Keep each pull request focused. Explain what changed and why it helps.
- Include a screenshot for changes that affect the interface.

## Work locally

Follow the **Local setup** section in [README.md](./README.md). It covers the required Node.js version, installing dependencies, and starting the local app.

Use the fictional candidate and role data included with the project. Do not add personal candidate information, credentials, account identifiers, or local environment files to issues or commits.

## Run the project checks

Before opening a pull request, run:

```bash
npm run check
```

This checks formatting, lint, and TypeScript. After changing Cloudflare bindings or Workflow and Durable Object configuration, regenerate the binding types with:

```bash
npm run types
```

The project does not currently include an automated unit-test suite. If your change needs a manual check, describe what you exercised in the pull request.

## Describe the change

Open pull requests against `main`. Include a short summary, the reason for the change, and the checks you ran. For interface changes, add a screenshot so reviewers can see the result.
