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
