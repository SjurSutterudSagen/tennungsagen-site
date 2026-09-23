This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## TypeScript setup

TypeScript 7 and 6 are installed side by side, because TypeScript 7.0 ships the
Go-native compiler without the JavaScript compiler API (it returns in 7.1):

| Command | Compiler | Notes |
| --- | --- | --- |
| `pnpm typecheck` | TypeScript 7 (`tsc`) | The native compiler — this is the fast one |
| `pnpm typecheck:ts6` | TypeScript 6 (`tsc6`) | Matches what `next build` and ESLint see |

The `typescript` dependency is an alias for
[`@typescript/typescript6`](https://www.npmjs.com/package/@typescript/typescript6),
Microsoft's compatibility package: it exposes the TypeScript 6 API under the package
name that tooling imports, so `eslint-config-next` (via `typescript-eslint`, which
supports `typescript <6.1.0`) and the Next.js IDE plugin keep working. The real
TypeScript 7 is installed as `typescript7` and provides the `tsc` binary; the
compatibility package provides `tsc6`.

`next build` type checks by running the project-local `tsc` binary
(`experimental.useTypeScriptCli`, on by default), and resolves it from the `typescript`
package — so builds currently type check with TypeScript 6 semantics.

Do not point VS Code at the workspace TypeScript version: neither package ships a
`tsserver`. The bundled editor TypeScript is the right choice here.

Once TypeScript 7.1 ships the compiler API and `typescript-eslint` supports it, this
collapses back to a plain `typescript` dependency on version 7.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
