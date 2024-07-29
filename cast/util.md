## Hex to Decimal

```shell
cast --to-dec 0x135605c
```

## encode calldata

```shell
cast calldata --help

ABI-encode a function with arguments

Usage: cast calldata <SIG> [ARGS]...

Arguments:
  <SIG>      The function signature in the format `<name>(<in-types>)(<out-types>)`
  [ARGS]...  The arguments to encode

```

```shell
cast calldata "transfer(address,uint256)" 0x67547791b4749e8cb7c6317d986df20260a2f72f 500000000000000000
```

执行结果:

```
0xa9059cbb00000000000000000000000067547791b4749e8cb7c6317d986df20260a2f72f00000000000000000000000000000000000000000000000006f05b59d3b20000
```

## decode calldata

Decode ABI-encoded input data

```shell
cast calldata-decode "transfer(address,uint256)" 0xa9059cbb000000000000000000000000e78388b4ce79068e89bf8aa7f218ef6b9ab0e9d0000000000000000000000000000000000000000000000000008a8e4b1a3d8000
```

执行结果:

```
0xE78388b4CE79068e89Bf8aA7f218eF6b9AB0e9d0
39000000000000000 [3.9e16]
```

## 优雅输出解析 calldata

```shell
cast pretty-calldata 0xa9059cbb00000000000000000000000067547791b4749e8cb7c6317d986df20260a2f72f000000000000000000000000000000000000000000000000000000004190ab00
```

执行结果:

```
 Possible methods:
 - transfer(address,uint256)
 ------------
 [000]: 00000000000000000000000067547791b4749e8cb7c6317d986df20260a2f72f
 [020]: 000000000000000000000000000000000000000000000000000000004190ab00
```

## 通过 selector 获取函数签名

```shell
cast 4byte 0xa9059cbb
```

执行结果:

```
transfer(address,uint256)
```

## 通过函数签名计算 selector

```shell
cast sig "transfer(address,uint256)"
```

执行结果:

```
0xa9059cbb
```

## 通过 Topics[0] 获取事件签名

```shell
cast 4byte-event 0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef
```

执行结果:
`Transfer(address,address,uint256)`

# 账户管理

## 生成私钥

```shell
cast wallet new
```

执行结果:

```
Address:     0x4d402c08665D9baa2a6304019b668325D55F7ACE
Private key: 0x450bf982b9bca97ce7a7fee475d048723ffc6f2281a3012b8a341313356f8daf
```

## 生成助记词

```shell
cast wallet new-mnemonic
```

## 签名数据

```shell
cast wallet sign "hello" --private-key 0x450bf982b9bca97ce7a7fee475d048723ffc6f2281a3012b8a341313356f8daf
```

执行结果:

```
0x168fbca568a88bcc7d80c0e6550c3ea40d1c3158dd80da27c689b89c7bf3761d7706a7626ab6a25770b0d14543b81f328246e4767b8b4332c700fd25db68b8ff1c
```

## 验证签名

```shell
cast wallet verify --address 0x4d402c08665D9baa2a6304019b668325D55F7ACE "hello" 0x168fbca568a88bcc7d80c0e6550c3ea40d1c3158dd80da27c689b89c7bf3761d7706a7626ab6a25770b0d14543b81f328246e4767b8b4332c700fd25db68b8ff1c
```

执行结果:

```
Validation succeeded. Address 0x4d402c08665D9baa2a6304019b668325D55F7ACE signed this message.

```

## 计算 mapping 中的 slot 位置

`cast index <KEY_TYPE> <KEY> <SLOT_NUMBER>`

```shell
cast index address 0xF977814e90dA44bFA03b6295A0616a897441aceC 1
```

执行结果:

```
0x563888e0f7cf9f7af91fd78748d5c42f1d7df4f94ff0717b6af6deb33c5baf8e
```
