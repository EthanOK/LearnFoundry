foundry.toml

```
[rpc_endpoints]
sepolia = "https://eth-sepolia.g.alchemy.com/v2/${ALCHEMY_MAINNET_KEY}"

[etherscan]
mainnet = { key = "${ETHERSCAN_MAINNET_KEY}" }
sepolia = { key = "${ETHERSCAN_MAINNET_KEY}" }

```

# forge script

`forge script [OPTIONS] <PATH> [ARGS]...`

以脚本形式运行智能合约，构建可在链上发送的交易

## 部署合约

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

import {Script, console} from "forge-std/Script.sol";
import {MyToken} from "../src/MyToken.sol";

contract MyTokenScript is Script {
    MyToken public token;

    function setUp() public {}

    function run() public {
        vm.startBroadcast(vm.envUint("PRIVATE_KEY"));

        token = new MyToken("PandaCoin", "PDC");

        vm.stopBroadcast();
    }
}
```

```shell
forge script --broadcast script/MyToken.s.sol:MyTokenScript -vvvv --rpc-url sepolia
```

## 部署的同时验证合约

```shell
forge script --broadcast --verify script/MyToken.s.sol:MyTokenScript -vvvv --rpc-url sepolia
```

## 验证合约

`forge verify-contract [OPTIONS] <ADDRESS> [CONTRACT]`

```shell
forge verify-contract --watch --constructor-args $(cast abi-encode "constructor(string,string)" "PandaCoin" "PDC") 0xEa26e92FD3262F85a7846D9cC862841656312Fba  MyToken --rpc-url sepolia --etherscan-api-key sepolia
```
