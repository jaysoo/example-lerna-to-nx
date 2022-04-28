# Lerna to Nx example

This is an example of migrating a lerna monorepo to Nx.

You can [compare the `main` branch with the `use-nx` branch](https://github.com/jaysoo/example-lerna-to-nx/pull/1). There is minimal changes required to support linking modules, and running tasks. For managing versions, we're using [changesets](https://github.com/changesets/changesets).

> NOTE: We're combining Nx with npm workspaces in order to support linking modules. You can also use yarn or pnpm for linking.

First, run `npm install`, then...

Try running `npm start` in both branches, and see that:

1. The script looks  for a  `start` target in package scripts of each package. In this case only `packages/foo` has this target. This is handled by Lerna/Nx.
2. In `packages/foo` we are using `@acme/bar`, which is linked to `packages/bar`. This is handled by npm.

Then try running `npm run release` in both branches (the Nx one also requires `npm run version` to run  first).

That's it!

Nx also does a lot more (like local/remote computation caching, powerful plugins, etc.). Learn more by visiting [nx.dev](https://nx.dev/).

