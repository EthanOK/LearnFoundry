# forge inspect <CONTRACT> <FIELD>

## <FIELD>

```
abi, bytecode, deployedBytecode, assembly, assemblyOptimized, methodIdentifiers, gasEstimates, storageLayout, devdoc, ir, irOptimized, metadata, userdoc, ewasm, errors, events
```

## `forge inspect ERC20 methodIdentifiers`

获取合约的 methodIdentifiers `selector`

```json
{
  "allowance(address,address)": "dd62ed3e",
  "approve(address,uint256)": "095ea7b3",
  "balanceOf(address)": "70a08231",
  "decimals()": "313ce567",
  "decreaseAllowance(address,uint256)": "a457c2d7",
  "increaseAllowance(address,uint256)": "39509351",
  "name()": "06fdde03",
  "symbol()": "95d89b41",
  "totalSupply()": "18160ddd",
  "transfer(address,uint256)": "a9059cbb",
  "transferFrom(address,address,uint256)": "23b872dd"
}
```

## `forge inspect Error errors`

获得合约的 errors `selector`

```json
{
  "InvalidInput()": "b4fa3fb3",
  "InvalidSignature()": "8baa579f",
  "InvalidState()": "baf3f0f7",
  "NotOwner()": "30cd7471"
}
```

## `forge inspect Counter abi`

获得合约的 abi

```json
[
  {
    "type": "function",
    "name": "bug",
    "inputs": [],
    "outputs": [],
    "stateMutability": "nonpayable"
  },
  {
    "type": "function",
    "name": "increment",
    "inputs": [],
    "outputs": [],
    "stateMutability": "nonpayable"
  },
  {
    "type": "function",
    "name": "number",
    "inputs": [],
    "outputs": [
      {
        "name": "",
        "type": "uint256",
        "internalType": "uint256"
      }
    ],
    "stateMutability": "view"
  },
  {
    "type": "function",
    "name": "setNumber",
    "inputs": [
      {
        "name": "newNumber",
        "type": "uint256",
        "internalType": "uint256"
      }
    ],
    "outputs": [],
    "stateMutability": "nonpayable"
  }
]
```

## `forge inspect Counter bytecode`

获得合约的 bytecode ,用于部署

```
0x608060405234801561001057600080fd5b5061014a806100206000396000f3fe608060405234801561001057600080fd5b506004361061004c5760003560e01c80633f2de4e8146100515780633fb5c1cb1461005b5780638381f58a1461006e578063d09de08a14610089575b600080fd5b610059610091565b005b6100596100693660046100b2565b600055565b61007760005481565b60405190815260200160405180910390f35b61005961009c565b6100696064436100cb565b6000805490806100ab836100ed565b9190505550565b6000602082840312156100c457600080fd5b5035919050565b6000826100e857634e487b7160e01b600052601260045260246000fd5b500690565b60006001820161010d57634e487b7160e01b600052601160045260246000fd5b506001019056fea264697066735822122070a8d15904ceeb4b801537854594c327c3315f76851c4d05439f556c31f0d6b764736f6c63430008120033
```

## `forge inspect ERC20 storage`

获得合约的 storage 布局

```json
{
  "storage": [
    {
      "astId": 29105,
      "contract": "lib/openzeppelin-contracts/contracts/token/ERC20/ERC20.sol:ERC20",
      "label": "_balances",
      "offset": 0,
      "slot": "0",
      "type": "t_mapping(t_address,t_uint256)"
    },
    {
      "astId": 29111,
      "contract": "lib/openzeppelin-contracts/contracts/token/ERC20/ERC20.sol:ERC20",
      "label": "_allowances",
      "offset": 0,
      "slot": "1",
      "type": "t_mapping(t_address,t_mapping(t_address,t_uint256))"
    },
    {
      "astId": 29113,
      "contract": "lib/openzeppelin-contracts/contracts/token/ERC20/ERC20.sol:ERC20",
      "label": "_totalSupply",
      "offset": 0,
      "slot": "2",
      "type": "t_uint256"
    },
    {
      "astId": 29115,
      "contract": "lib/openzeppelin-contracts/contracts/token/ERC20/ERC20.sol:ERC20",
      "label": "_name",
      "offset": 0,
      "slot": "3",
      "type": "t_string_storage"
    },
    {
      "astId": 29117,
      "contract": "lib/openzeppelin-contracts/contracts/token/ERC20/ERC20.sol:ERC20",
      "label": "_symbol",
      "offset": 0,
      "slot": "4",
      "type": "t_string_storage"
    }
  ],
  "types": {
    "t_address": {
      "encoding": "inplace",
      "label": "address",
      "numberOfBytes": "20"
    },
    "t_mapping(t_address,t_mapping(t_address,t_uint256))": {
      "encoding": "mapping",
      "key": "t_address",
      "label": "mapping(address => mapping(address => uint256))",
      "numberOfBytes": "32",
      "value": "t_mapping(t_address,t_uint256)"
    },
    "t_mapping(t_address,t_uint256)": {
      "encoding": "mapping",
      "key": "t_address",
      "label": "mapping(address => uint256)",
      "numberOfBytes": "32",
      "value": "t_uint256"
    },
    "t_string_storage": {
      "encoding": "bytes",
      "label": "string",
      "numberOfBytes": "32"
    },
    "t_uint256": {
      "encoding": "inplace",
      "label": "uint256",
      "numberOfBytes": "32"
    }
  }
}
```
