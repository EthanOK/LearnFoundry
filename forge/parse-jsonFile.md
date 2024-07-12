foundry.toml

```toml
fs_permissions = [{ access = "read", path = "./"}]
```

test/json/demo.json

```json
{
  "accounts": [
    {
      "account": "0x7E5F4552091A69125d5DfCb7b8C2659029395Bdf",
      "amount": 1000000
    },
    {
      "account": "0x7E5F4552091A69125d5DfCb7b8C2659029395Bdf",
      "amount": 200000000
    },
    {
      "account": "0x7E5F4552091A69125d5DfCb7b8C2659029395Bdf",
      "amount": 500000000
    }
  ],
  "name": "Account Table"
}
```

test/ReadJsonFile.T.sol

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

import "forge-std/Test.sol";

contract ReadJsonFileTest is Test {
    struct Account {
        address account;
        uint256 amount;
    }

    struct AccountTable {
        Account[] accounts;
        string name;
    }

    function testReadFile() public view {
        string memory root = vm.projectRoot();
        // emit log(root);
        string memory path = string.concat(root, "/test/json/demo.json");
        // emit log(path);
        string memory json = vm.readFile(path);
        // emit log(json);
        bytes memory data = vm.parseJson(json);
        AccountTable memory table = abi.decode(data, (AccountTable));

        console2.log("Welcome to", table.name);
        for (uint256 i = 0; i < table.accounts.length; i++) {
            Account memory account = table.accounts[i];

            console2.log(
                "Account: %s, Amount: %d",
                account.account,
                account.amount
            );
        }
    }
}
```
