---
description: >-
`eth` namespace APIs.
---

# Namespace eth <a id="namespace-eth"></a>

The namespace `eth` provides functions related to accounts, blocks, transactions,
configurations of networks or nodes, filters, and so on.

Klaytn now supports the namespace `eth` of [Ethereum's JSON-RPC API](https://eth.wiki/json-rpc/API). Please note that
some return values have been adjusted to match Ethereum's API response. 

And due to the fundamental design differences between Klaytn and Ethereum, 
Klaytn's data structure (Transaction, Block, and TransactionReceipt) cannot be fully supported via `eth` namespace APIs.

Please check the [Summary of Differences from Ethereum](#summary_of_differences_from_ethereum) in this document.

**NOTE**: `eth` namespace APIs are supported from Klaytn v1.8.0.

The list below enumerates the API functions. All `eth` namespace APIs are supported on Klaytn.

### [Account](./eth/account.md) <a id="account"></a>
- [eth_accounts](./eth/account.md#eth_accounts)
- [eth_getBalance](./eth/account.md#eth_getbalance)
- [eth_getCode](./eth/account.md#eth_getcode)
- [eth_getTransactionCount](./eth/account.md#eth_gettransactioncount)
- [eth_sign](./eth/account.md#eth_sign)

### [Block](./eth/block.md) <a id="block"></a>
- [eth_blockNumber](./eth/block.md#eth_blocknumber)
- [eth_getHeaderByNumber](./eth/block.md#eth_getheaderbynumber)
- [eth_getHeaderByHash](./eth/block.md#eth_getheaderbyhash)
- [eth_getBlockByNumber](./eth/block.md#eth_getblockbynumber)
- [eth_getBlockByHash](./eth/block.md#eth_getblockbyhash)
- [eth_getBlockByHash](./eth/block.md#eth_getblockbyhash)
- [eth_getUncleBlockByHashAndIndex](./eth/block.md#eth_getunclebyblockhashandindex)
- [eth_getUncleByBlockNumberAndIndex](./eth/block.md#eth_getunclebyblocknumberandindex)
- [eth_getBlockTransactionCountByNumber](./eth/block.md#eth_getblocktransactioncountbynumber)
- [eth_getBlockTransactionCountByHash](./eth/block.md#eth_getblocktransactioncountbyhash)
- [eth_getUncleCountByBlockNumber](./eth/block.md#eth_getunclecountbyblocknumber)
- [eth_getUncleCountByBlockHash](./eth/block.md#eth_getunclecountbyblockhash)
- [eth_getStorageAt](./eth/block.md#eth_getstorageat)
- [eth_mining](./eth/block.md#eth_mining)
- [eth_syncing](./eth/block.md#eth_syncing)


### [Transaction](./eth/transaction.md) <a id="transaction"></a>
- [eth_call](./eth/transaction.md#eth_call)
- [eth_estimateGas](./eth/transaction.md#eth_estimategas)
- [eth_getTransactionByBlockHashAndIndex](./eth/transaction.md#eth_gettransactionbyblockhashandindex)
- [eth_getTransactionByBlockNumberAndIndex](./eth/transaction.md#eth_gettransactionbyblocknumberandindex)
- [eth_getTransactionByHash](./eth/transaction.md#eth_gettransactionbyhash)
- [eth_getTransactionReceipt](./eth/transaction.md#eth_gettransactionreceipt)
- [eth_sendRawTransaction](./eth/transaction.md#eth_sendrawtransaction)
- [eth_sendTransaction](./eth/transaction.md#eth_sendtransaction)
- [eth_signTransaction](./eth/transaction.md#eth_signtransaction)


### [Configuration](./eth/config.md) <a id="configuration"></a>
- [eth_coinbase](./eth/config.md#eth_coinbase)
- [eth_etherbase](./eth/config.md#eth_etherbase)
- [eth_chainId](./eth/config.md#eth_chainid)
- [eth_gasPrice](./eth/config.md#eth_gasprice)


### [Filter](./eth/filter.md) <a id="filter"></a>
- [eth_getFilterChanges](./eth/filter.md#eth_getfilterchanges)
- [eth_getFilterLogs](./eth/filter.md#eth_getfilterlogs)
- [eth_getLogs](./eth/filter.md#eth_getlogs)
- [eth_newBlockFilter](./eth/filter.md#eth_newblockfilter)
- [eth_newFilter](./eth/filter.md#eth_newfilter)
- [eth_newPendingTransactionFilter](./eth/filter.md#eth_newpendingtransactionfilter)
- [eth_subscribe](./eth/filter.md#eth_subscribe)
- [eth_uninstallFilter](./eth/filter.md#eth_uninstallfilter)
- [eth_unsubscribe](./eth/filter.md#eth_unsubscribe)


### [Gas](./eth/gas.md) <a id="gas"></a>
- [eth_feeHistory](./eth/gas.md#eth_feehistory)
- [eth_maxPriorityFeePerGas](./eth/gas.md#eth_maxpriorityfeepergas)

### [Miscellaneous](./eth/misc.md) <a id="miscellaneous"></a>
- [eth_hashrate](./eth/misc.md#eth_hashrate)
- [eth_getWork](./eth/misc.md#eth_getwork)
- [eth_submitWork](./eth/misc.md#eth_submitwork)
- [eth_submitHashrate](./eth/misc.md#eth_submithashrate)

## Differences Overview from Ethereum <a id="differences_overview_from_ethereum">

> Please check the [Caution](./eth/caution.md) section which describes the differences between Klaytn and Ethereum when serving eth namespace APIs in more detail. 

### Block <a id="block"></a>

Related APIs: [eth_getHeaderByNumber](./eth/block/#eth_getHeaderByNumber), [eth_getHeaderByHash](./eth/block/#eth_getHeaderByHash), [eth_getBlockByHash](./eth/block/#eth_getBlockByHash), [eth_getBlockByNumber](./eth/block/#eth_getBlockByNumber), [eth_getUncleByBlockHashAndIndex](./eth/block/#eth_getUncleByBlockHashAndIndex), [eth_getUncleByBlockNumberAndIndex](./eth/block/#eth_getUncleByBlockNumberAndIndex).

| Field           | Description                                                                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                                                                                                                            
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| baseFeePerGas   | This field always has the value `0x0` because Klaytn does not have a baseFeePerGas scheme yet.                                                                                                                                                                                                                                                                                                                                           |
| difficulty      | This field corresponds to `blockScore` in the Klaytn header, which is fixed to `0x1`. This is because Klaytn does not have a PoW mechanism, which renders the concept of block difficulty useless.                                                                                                                                                                                                                                                                                       |
| extraData       | This field always has the value `0x`, which means it's empty data. Because Klaytn's `extraData` contains consensus data such as validators addresses, validators signatures, and proposer signature, it is inapplicable to `eth` namespace API.  |
| gasLimit        | This field always has the value `0xe8d4a50fff`(=`999999999999` in decimal), which is an arbitrary figure since Klaytn has no GasLimit. At the time of writing, this figure is 30 times higher than the [block gas limit of Ethereum](https://ethereum.org/en/developers/docs/gas/#block-size). Please refer to [Computation Cost](../../klaytn/design/computation/computation-cost) for more details.           |
| miner           | Because the [consensus mechanism](../../klaytn/design/consensus-mechanism) in Klaytn is [PBFT](../../klaytn/design/consensus-mechanism#pbft-practical-byzantine-fault-tolerance), there is a block proposer not miner. So it returns the address of proposer of the block.                                                                                                                                                              |
| mixHash         | This field always has zeroHash (`0x00...`) because Klaytn does not use a PoW mechanism.                                                                                                                                                                                                                                                                                                                                                 |
| nonce           | This field always has zeroNonce (`0x00...`) because Klaytn does not use a PoW mechanism.                                                                                                                                                                                                                                                                                                                                                |
| sha3Uncles      | This field always have `0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347` which is the keccak256 hash of rlp encoded bytes of empty list of block headers because there is no uncles in Klaytn.                                                                                                                                                                                                                       |
| totalDifficulty | The total blockScore of the chain until this block.                                                                                                                                                                                                                                                                                                                                                                                     |
| uncles          | This field always has the value `[]` because Klaytn has no uncles.                                                                                                                                                                                                                                                                                                                                                             |

Fields not covered here are fields used synonymously with Ethereum.

### Transaction <a id="transaction"></a>

Related APIs: [eth_getTransactionByHash](./eth/transaction/#eth_getTransactionByHash), [eth_getTransactionByBlockHashAndIndex](./eth/transaction/#eth_getTransactionByBlockHashAndIndex), [eth_getTransactionByBlockNumberAndIndex](./eth/transaction/#eth_getTransactionByBlockNumberAndIndex), [eth_pendingTransactions](./eth/transaction/#eth_pendingTransactions).

> Due to the fundamental design differences between Klaytn and Ethereum,
> Klaytn transactions cannot be fully supported via `eth` namespace APIs. 

| Field    | Description                                                                                                                                                                                                                                                                                 |
|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| gasPrice | Also known as [Unit Price](../../klaytn/design/transaction-fees#unit-price) in Klaytn, this value is determined in the system by the governance.                                                                                                                                            |
| type     | The value and data type of this field are converted. The type of this field is a string(e.g. `"LegacyTransaction"`) in Klaytn but it is converted and served as hexadecimal(e.g. `0x0`) just like Ethereum Transaction. Transaction types valid only for Klaytn are served as `0x0` always. |

Klaytn transactions can have more than one signature because Klaytn supports MultiSig (Ethereum transactions only have one signature field (= v, r, s)).
In that context, fields related to signature (v, r, s) will match `tx.signatures[0].V`, `tx.signatures[0].R`, and `tx.signatures[0].S`.

Fields not covered here are fields used synonymously with Ethereum.

### Transaction Receipt <a id="transaction_receipt"></a>

Related APIs: [eth_getTransactionReceipt](./eth/transaction/#eth_getTransactionReceipt).

> Due to the fundamental design differences existing between Klaytn and Ethereum,
> Klaytn transaction receipt cannot be fully supported when served via Ethereum namespace APIs.
 
| Field             | Description                                                                                                                                                                                             |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| effectiveGasPrice | Since Klaytn uses a fixed gas price policy, the gasPrice value is returned. gasPrice(also called [Unit Price](../../klaytn/design/transaction-fees#unit-price)) is set in the system by the governance. |
| transactionIndex  | Almost same with Ethereum but unlike Ethereum, Klaytn returns integer as it is when its pending.                                                                                                        |

Fields not covered here are fields used synonymously with Ethereum.
