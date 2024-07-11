# Test Contract

## 运行所有测试合约

```shell
forge test -vvv
```

## 运行某个测试合约

```shell
forge test --match-path test/USDTFork.t.sol -vvv
```

```shell
forge test --match-contract USDTForkTest -vvv
```

## 测试链上合约 fork-url

```shell
forge test --match-path test/USDTFork.t.sol -vvv --fork-url https://rpc.ankr.com/eth
```

另一种方式在测试合约内指定 fork-url
步骤 1：

```solidity
    function setUp() external {
        // 配置 fork url; INFURA_MAINNET_RPC 为 .env 文件中的环境变量
        uint256 forkId = vm.createFork(vm.envString("ETH_RPC_URL"));
        vm.selectFork(forkId);
        // TODO
    }

```

步骤 2:

```shell
forge test --match-path test/USDTFork.t.sol -vvv
```
