# Configuration Guidance for Using the new UNL

As [part of the migration of assets](https://xrpl.org/blog/2025/move-to-the-new-xrpl-foundation-commences) from the old XRPL Foundation (now known as Inclusive Financial Technology Foundation) to the new XRPL Foundation, the old XRPL Foundation’s published UNL, known as the default UNL or dUNL, is also being migrated.

The new XRPL Foundation UNL is currently active. To make use of it, you'll need to make some changes to your `rippled` configuration.

## Updating your node configuration

If your XRP Ledger node currently trusts the UNL published by the XRP Ledger Foundation endpoint, complete the following steps to update your settings:

### 1. Edit validators.txt

Update the `[validator_list_keys]` and `[validator_list_sites]` sections and replace the XRPL Foundation’s public key and endpoint. Other keys and endpoints, if present, remain the same:

```diff

[validator_list_sites]
 https://vl.ripple.com
-https://vl.xrplf.org
+https://unl.xrplf.org

[validator_list_keys]
 #vl.ripple.com
 ED2677ABFFD1B33AC6FBC3062B71F1E8397C1505E1C42C64D11AD1B28FF73F4734
-# vl.xrplf.org
-ED45D1840EE724BE327ABE9146503D5848EFD5F38B6D5FEDE71E80ACCE5E6E738B
+#unl.xrplf.org
+ED42AEC58B701EEBB77356FFFEC26F83C1F0407263530F068C7C73D392C7E06FD1
```

_(*) Some node operators that use the legacy format might have these configuration details in their rippled.cfg file._

### 2. Re-start `rippled`

After saving the changes, restart your `rippled` service for the changes to take effect.

### 3. Confirm the New Settings

After restarting rippled, run the following admin method:

```bash
/path/to/rippled validators
```

The output should display the updated values in the `publisher_lists` key, the list should be available with an expiration on February 13th 2026:

```
{
  "result": {
    "local_static_keys": [],
    "publisher_lists": [
      {
        "available": true,
        "expiration": "2026-Feb-13 14:15:03.000000000 UTC",
        ...
        "list": [
          ...
        ],
        "pubkey_publisher": "ED42AEC58B701EEBB77356FFFEC26F83C1F0407263530F068C7C73D392C7E06FD1",
        "seq": 1,
        "uri": "https://unl.xrplf.org",
        "version": 1
      },
	...
      ]
    ...
 }
```

## Verifying connectivity with the Network

Make sure your node maintains connectivity with the network. To confirm that, first run the same admin method:

```bash
/path/to/rippled validators
```

After a few seconds, it should display a list of Trusted Validator Keys, the Validator’s required quorum and some other Validators list settings:

`trusted_validator_keys`: Array of master public keys of all currently trusted validators. You should see 28 if you are a UNL Validator or 29 otherwise.
`validation_quorum`: Minimum number of trusted validations required to validate a ledger version. Its value should be 28 or 29, depending on whether your Validator is part of the UNL. If you see a value like 4294967295 after some time, your node is struggling to find a valid UNL use and further investigation is required.
`validator_list`: will hold configurations like number of Validators list, threshold and, importantly, expiration. The status should be active.

```
{
...
"trusted_validator_keys": [       
"nHUVPzAmAmQ2QSc4oE1iLfsGi17qN2ado8PhxvgEkou76FLxAz7C", "nHBgyVGAEhgU6GoEqoriKmkNBjzhy6WJhX9Z7cZ71yJbv28dzvVN", "nHUP4RcLQdPHh3kMtFm9NFGnjEYLGXiQAyyB7qFsjATHMw2YVxHi", "nHUcNC5ni7XjVYfCMe38Rm3KQaq27jw7wJpcUYdo4miWwpNePRTw", "nHUXeusfwk61c4xJPneb9Lgy7Ga6DVaVLEyB29ftUdt9k2KxD6Hw", "nHU4bLE3EmSqNwfL4AP1UZeTNPrSPPP6FXLKXo2uqfHuvBQxDVKd", "nHUpDEZX5Zy9auiu4yhDmhirNu6PyB1LvzQEL9Mxmqjr818w663q", "nHBWa56Vr7csoFcCnEPzCCKVvnDQw3L28mATgHYQMGtbEfUjuYyB", "nHUKgFa4diHC9sN7YnVt4AUPGkaHtShrT76xJBUFdH2B5Tz5nwVQ", "nHBidG3pZK11zQD6kpNDoAhDxH6WLGui6ZxSbUx7LSqLHsgzMPec", "nHUryiyDqEtyWVtFG24AAhaYjMf9FRLietbGzviF3piJsMm9qyDR", "nHUpDPFoCNysckDSHiUBEdDXRu2iYLUgYjTzrj3bde5iDRkNtY8f", 
"nHB8QMKGt9VB4Vg71VszjBVQnDW3v3QudM4DwFaJfy96bj4Pv9fA", "nHBVACxZaNbUjZZkBfj7gRxF3xgG2vbcP4m48KzVwntdTogi5Tfs", "nHUge3GFusbqmfYAJjxfKgm2j4JXGxrRsfYMcEViHrFSzQDdk5Hq", "nHU3AenyRuJ4Yei4YHkh6frZg8y2RwXznkMAomUE1ptV5Spvqsih", "nHUrUNXCy4DgPPNABX9C6mUctpoq7CwgLKAUxjw6zYtTfiqsj1ew", "nHUFCyRCrUjvtZmKiLeF8ReopzKuUoKeDeXo3wEUBVSaawzcSBpW", "nHUvcCcmoH1FJMMC6NtF9KKA4LpCWhjsxk2reCQidsp5AHQ7QY9H", "nHDB2PAPYqF86j9j3c6w1F1ZqwvQfiWcFShZ9Pokg9q4ohNDSkAz", "nHUfPizyJyhAJZzeq3duRVrZmsTZfcLn7yLF5s2adzHdcHMb9HmQ", "nHUr8EhgKeTc9ESNt4nMYzWC2Pu7GgRHMRTsNEyGBTCfnHPxmXcm", "nHUfxETNHsA9reyYCVYwNztEbifMg6U9YUdcgVvzMwGNpphKSSf6", "nHUfbxw2zXqbSVL9tiNSVhEVPcpUQwoWKtHyWkTbm6hQj2KaNqit", "nHUdjQgg33FRu88GQDtzLWRw95xKnBurUZcqPpe3qC9XVeBNrHeJ", "nHUED59jjpQ5QbNhesXMhqii9gA8UfbBmv3i5StgyxG98qjsT4yn", "nHU2k8Po4dgygiQUG8wAADMk9RqkrActeKwsaC9MdtJ9KBvcpVji", "nHUpJSKQTZdB1TDkbCREMuf8vEqFkk84BcvZDhsQsDufFDQVajam", "nHDH7bQJpVfDhVSqdui3Z8GPvKEBQpo6AKHcnXe21zoD4nABA6xj", "nHUwGQrfZfieeLFeGRdGnAmGpHBCZq9wvm5c59wTc2JhJMjoXmd8", "nHUY14bKLLm72ukzo2t6AVnQiu4bCd1jkimwWyJk3txvLeGhvro5", "nHUDpRzvY8fSRfQkmJMqjmVSaFmMEVxBNn2tNQy5VAhFJ6is6GFk", "nHUq9tJvSyoXQKhRytuWeydpPjvTz3M9GfUpEqfsg9xsewM7KkkK", "nHULqGBkJtWeNFjhTzYeAsHA3qKKS7HoBh8CV3BAGTGMZuepEhWC", "nHUbgDd63HiuP68VRWazKwZRzS61N37K3NbfQaZLhSQ24LGGmjtn", "nHDHzXZKtmMHCkTVgdWY4dqdigDrESiseUF8JkzE93DUtfbt6s3W"
],
"validation_quorum": 28,
"validator_list": { 
	"count": COUNT,
	"expiration": "EXPIRATION_DATE",
	"status": "active",
	"validator_list_threshold": THRESHOLD
}
...
}
```

If your node is configured correctly, it should eventually sync with the network (the time to do so will depend on factors like history required, time offline, etc). To verify that, run the following command: 

```bash
/path/to/rippled server_info
```

The output should have a valid range of ledgers in the `complete_ledgers` key:

```
{
   ...
   complete_ledgers": "94719199-94720262",
   ...
}
```

## Impact of not updating the configuration settings
If you fail to switch to the new settings, your node may stop loading the XRPL Foundation’s trusted validators list from September 30th, 2025, and entirely on January 18th, 2026, when that now-deprecated UNL expires. 

If your configuration remains un-updated within the provided timelines, your node could stop connecting to the network in the following scenarios:

- Your node relies exclusively on the (old) UNL published by the XRPL Foundation.
- Depending on the  [validator_list_threshold] and the continuity of the list, there is a chance of disruption if referencing the old foundation list along with other lists.

Since [rippled 2.4.0,](https://xrpl.org/blog/2025/rippled-2.4.0) a new configuration setting [validator_list_threshold] has been added that specifies the minimum number of Validator Lists on which a validator must be listed to be considered part of the UNL.

This can be set explicitly to any positive integer number less than the size of [validator_list_keys]. If it is not set or set to 0, the value will be calculated the following way:

- If fewer than 3 Validators Lists are configured, rippled will need to load all of them, and validators will have to be in all.
- If there are three or more, the threshold becomes half the total number (rounded down) plus 1. This effectively means you need a UNL validator to be present in more than half of the lists. For example, if three Validators Lists are configured, UNL Validators should be present in at least 2 of the 3.
