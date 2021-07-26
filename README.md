# yarn-repro-references

Go into `packages/shared/index.ts` and right click > `Find all references` on `SomeType`. It should find the usages in `consumer1` and `consumer2`.

When using `node_modules` everything works. With PnP it fails.

With PnP:

<img width="425" alt="Screenshot 2021-07-26 at 15 28 42" src="https://user-images.githubusercontent.com/697707/126988666-f0bbdf02-bc39-49d4-aad5-eaea3cbdf161.png">

With `node_modules`:

<img width="433" alt="Screenshot 2021-07-26 at 15 31 33" src="https://user-images.githubusercontent.com/697707/126989026-f931321a-c5e4-44e8-9b8e-fb2ffed60ddf.png">

(note that you may need to manually briefly open `consumer1/index.ts` and `consumer2/index.ts` in VSCode before running Find References to see the output above, otherwise it may look similar to the PnP one)

If you remove `lodash` from `shared`'s peers, the PnP scenario works correctly.
