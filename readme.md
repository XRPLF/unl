# Unique Node List (UNL)

The XRP Ledger Foundation maintains a Unique Node List (UNL) for the XRPL. This repo is the source for that UNL, published at [https://unl.xrplf.org](https://unl.xrplf.org/).

## Editing the UNL

The process of creating a signed UNL is manual and intentionally non-automated.

To suggest an update to this list, make a Pull Request. If approved, the next build of the UNL will include these changes.

- Only changes to `source/unl-raw.yaml` are required in your Pull Request.

## Historical Record

The `record` directory contains a historical record of the `unl.json` files, postfixed with `-YYYYMMDDNN` where `NN` is a 2-digit sequence number for the day.

