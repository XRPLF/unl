# Unique Node List (UNL)

The XRP Ledger Foundation maintains a Unique Node List (UNL) for the XRPL. This repo is the source for that UNL, published at [https://unl.xrplf.org](https://unl.xrplf.org/).

## Editing the UNL

The process of creating a signed UNL is manual and intentionally non-automated.

To suggest an update to this list, [make a Pull Request](https://github.com/XRPLF/unl/pulls). If approved, the next build of the UNL will include these changes.

- Only changes to `source/unl-raw.yaml` are required in your Pull Request.
- Once the PR has been approved, it is manually reviewed by the `XRPLF`.
- The `XRPLF` can then build a new UNL to publish to [https://unl.xrplf.org](https://unl.xrplf.org/).
- Once the `XRPLF` has published an update, it will be added to the [`Historical Record`](record) as well synchronized with the [latest unl build](https://xrplf.github.io/unl/record/unl-latest.json) url, `record/unl-latest.json`.

