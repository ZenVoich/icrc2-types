# icrc2-types

[![mops](https://oknww-riaaa-aaaam-qaf6a-cai.raw.ic0.app/badge/mops/icrc2-types)](https://mops.one/icrc2-types)
[![documentation](https://oknww-riaaa-aaaam-qaf6a-cai.raw.ic0.app/badge/documentation/icrc2-types)](https://mops.one/icrc2-types/docs)

[ICRC-2](https://github.com/dfinity/ICRC-1/tree/main/standards/ICRC-2) canister interface for Motoko.

Includes the [ICRC-1](https://github.com/dfinity/ICRC-1/tree/main/standards/ICRC-1) interface.


## Install
```
mops add icrc2-types
```

## Usage

Get the token allowance that the spender account can transfer from the specified account on the `ryjl3-tyaaa-aaaaa-aaaba-cai` (ICP) canister.

```motoko
import ICRC2 "mo:icrc2-types";

let icp = actor("ryjl3-tyaaa-aaaaa-aaaba-cai") : ICRC2.Service;

let allowance = await icp.icrc2_allowance({
  account = targetAccount;
  spender = spenderAccount;
});

Debug.print("Allowance amount: " # debug_show(allowance.allowance));
Debug.print("Allowance exires at: " # debug_show(allowance.expires_at));
```