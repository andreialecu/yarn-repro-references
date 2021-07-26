# yarn-repro-references

Go into `packages/shared/index.ts` and right click > `Find all references` on `SomeType`. It should find the usages in `consumer1` and `consumer2`.

When using `node_modules` everything works. With PnP it fails.
