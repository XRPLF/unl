# Unique Node List (UNL)

The XRP Ledger Foundation maintains a Unique Node List (UNL) for the XRPL. This repo is the source for that UNL, published at [https://unl.xrplf.org](https://unl.xrplf.org/).

## Editing the UNL

The process of creating a signed UNL is manual and intentionally non-automated.

To suggest an update to this list, make a Pull Request. If approved, the next build of the UNL will include these changes.

## Example Source File

We use a YAML file to define the list of validators using the following format:

```yaml
nodes:
  - id: nHBgyVGAEhgU6GoEqoriKmkNBjzhy6WJhX9Z7cZ71yJbv28dzvVN
    name: v2.xrpl-commons.org
  - id: nHU4bLE3EmSqNwfL4AP1UZeTNPrSPPP6FXLKXo2uqfHuvBQxDVKd
    name: ripple.com
```

The `id` field is the public key of the validator, and the `name` field is a human-readable name for the validator. Only the `id` field is required, but it is recommended to include the `name` field for clarity.

