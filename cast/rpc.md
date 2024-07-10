# RPC

## 获取 最新区块号

```shell
cast rpc eth_blockNumber --rpc-url "https://rpc.ankr.com/eth"
```

```shell
cast block-number --rpc-url "https://rpc.ankr.com/eth"
```

## 通过 blockNumber 获取区块信息

```shell
cast rpc eth_getBlockByNumber "latest" false --rpc-url "https://rpc.ankr.com/eth"

cast rpc eth_getBlockByNumber 0x135605c false --rpc-url "https://rpc.ankr.com/eth"

cast block 20275399 --rpc-url "https://rpc.ankr.com/eth"
```

## 获取交易信息

```shell
cast tx 0x81182c33059eac1057d9ef2aa40cdbaae73de08af5178fbe7f192818b4f61091 --rpc-url "https://rpc.ankr.com/eth"
```

获取交易 [gasPrice] 具体字段

```shell
cast tx 0x81182c33059eac1057d9ef2aa40cdbaae73de08af5178fbe7f192818b4f61091 gasPrice --rpc-url "https://rpc.ankr.com/eth"
```

获取 json 格式

```shell
cast tx 0x81182c33059eac1057d9ef2aa40cdbaae73de08af5178fbe7f192818b4f61091 --rpc-url "https://rpc.ankr.com/eth" --json | jq
```

```json
{
  "hash": "0x81182c33059eac1057d9ef2aa40cdbaae73de08af5178fbe7f192818b4f61091",
  "nonce": "0x24cd",
  "blockHash": "0x81b36535141e32f7ecbdbae991314345b78999829c802ad0a47a8439d62e09fb",
  "blockNumber": "0x1356100",
  "transactionIndex": "0xaf",
  "from": "0xdf99a0839818b3f120ebac9b73f82b617dc6a555",
  "to": "0x08e9ad0b5558b44154c47f42995be44718c6d2b1",
  "value": "0x5f5214e7dd160e",
  "gasPrice": "0xc5ed3f21",
  "gas": "0x5208",
  "maxFeePerGas": "0xc5ed3f21",
  "maxPriorityFeePerGas": "0x0",
  "input": "0x",
  "r": "0x14de5b6d9a543c356f8d1d60492766a4672013289439d694eafc9937ad4eda33",
  "s": "0x62229b66c6fe0c2705aa4bd0074bff7bd70f8dd2b64bc5e36f41a38fc7cc70f1",
  "v": "0x0",
  "yParity": "0x0",
  "chainId": "0x1",
  "accessList": [],
  "type": "0x2"
}
```

### 获取交易 [input] data

```shell
cast tx 0xa49f5c6486da1839daa8f446c0565273734577a5fa8afa67c7e2641bd708ad7b --rpc-url "https://rpc.ankr.com/eth" input
```

## 获取交易 receipt 信息

```shell
cast receipt 0xa49f5c6486da1839daa8f446c0565273734577a5fa8afa67c7e2641bd708ad7b --rpc-url "https://rpc.ankr.com/eth"
```

输出 json 格式

```shell
cast receipt 0xa49f5c6486da1839daa8f446c0565273734577a5fa8afa67c7e2641bd708ad7b --rpc-url "https://rpc.ankr.com/eth" --json | jq
```

### 获取交易 [logs] data

```shell
cast receipt 0xa49f5c6486da1839daa8f446c0565273734577a5fa8afa67c7e2641bd708ad7b logs --rpc-url "https://rpc.ankr.com/eth"
```

## 执行区块中的先前交易 并输出调用栈

```shell
cast run 0x8053a0562721fc322a93af674a7445bc955897f3ea3a86fbf63c63cf1635480b --rpc-url https://rpc.ankr.com/eth_sepolia
```
