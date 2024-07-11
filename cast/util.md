## Hex to Decimal

```shell
cast --to-dec 0x135605c
```

## 解析 calldata

```shell
cast pretty-calldata 0xa9059cbb00000000000000000000000067547791b4749e8cb7c6317d986df20260a2f72f000000000000000000000000000000000000000000000000000000004190ab00
```

## 通过 selector 获取函数签名

```shell
cast 4byte 0xa9059cbb
```

## 通过函数签名计算 selector

```shell
cast sig "transfer(address,uint256)"
```

## 通过 Topics[0] 获取事件签名

```shell
cast 4byte-event 0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef
```

`Transfer(address,address,uint256)`

# 账户管理

## 生成私钥

```shell
cast wallet new
```

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

## 验证签名

```shell
cast wallet verify --address 0x4d402c08665D9baa2a6304019b668325D55F7ACE "hello" 0x168fbca568a88bcc7d80c0e6550c3ea40d1c3158dd80da27c689b89c7bf3761d7706a7626ab6a25770b0d14543b81f328246e4767b8b4332c700fd25db68b8ff1c
```

## 计算 mapping 中的 slot 位置

`cast index <KEY_TYPE> <KEY> <SLOT_NUMBER>`

```shell
cast index address 0xF977814e90dA44bFA03b6295A0616a897441aceC 1
```
