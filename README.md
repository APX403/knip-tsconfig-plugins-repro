# knip-tsconfig-plugins-repro

`apps/web/tsconfig.json` extends `@repo/typescript-config/nextjs.json`, which
sets `"plugins": [{ "name": "next" }]`. `apps/web` lists `next` and the preset
package has no dependencies.

```sh
pnpm install
pnpm knip
```

Expected: no issues.

Actual, with Knip 6.43.0:

```
Unresolved imports (1)
next  packages/typescript-config/nextjs.json
```
