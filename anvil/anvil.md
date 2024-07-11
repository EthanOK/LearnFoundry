## 启动本地节点

```shell
anvil --block-time 6
```

6s 产生 1 个区块

## 自定义助记词

```shell
anvil --mnemonic "candy maple cake sugar pudding cream honey rich smooth crumble sweet treat"  --block-time 6
```

### fork mainnet

```shell
anvil --fork-url https://mainnet.infura.io/v3/9aa3d95b3bc440fa88ea12eaa4456161
```

fork 指定区块

```shell
anvil --fork-url https://mainnet.infura.io/v3/9aa3d95b3bc440fa88ea12eaa4456161 --fork-block-number 20281608
```
