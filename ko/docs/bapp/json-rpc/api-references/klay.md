---
description: >-
  계정, 블록, 트랜잭션, 노드 등과 관련된 API입니다.
---

# Namespace klay <a id="namespace-klay"></a>

`klay` namespace는 계정, 블록, 트랜잭션, 네트워크 또는 노드의 환경설정, 필터 등과 관련한 함수를 제공합니다. 아래는 현재 Klaytn이 지원하는 API 함수들의 목록입니다.


### [계정(Account)](./klay/account.md) <a id="account"></a>
- [klay_accountCreated](./klay/account.md#klay_accountcreated)
- [klay_accounts](./klay/account.md#klay_accounts)
- [klay_getAccount](./klay/account.md#klay_getaccount)
- [klay_getAccountKey](./klay/account.md#klay_getaccountkey)
- [klay_getBalance](./klay/account.md#klay_getbalance)
- [klay_getCode](./klay/account.md#klay_getcode)
- [klay_getTransactionCount](./klay/account.md#klay_gettransactioncount)
- [klay_isContractAccount](./klay/account.md#klay_iscontractaccount)
- [klay_sign](./klay/account.md#klay_sign)


### [블록](./klay/block.md) <a id="block"></a>
- [klay_blockNumber](./klay/block.md#klay_blocknumber)
- [klay_getBlockByNumber](./klay/block.md#klay_getblockbynumber)
- [klay_getBlockByHash](./klay/block.md#klay_getblockbyhash)
- [klay_getBlockReceipts](./klay/block.md#klay_getblockreceipts)
- [klay_getBlockTransactionCountByNumber](./klay/block.md#klay_getblocktransactioncountbynumber)
- [klay_getBlockTransactionCountByHash](./klay/block.md#klay_getblocktransactioncountbyhash)
- [klay_getBlockWithConsensusInfoByHash](./klay/block.md#klay_getblockwithconsensusinfobyhash)
- [klay_getBlockWithConsensusInfoByNumber](./klay/block.md#klay_getblockwithconsensusinfobynumber)
- [klay_getCommittee](./klay/block.md#klay_getcommittee)
- [klay_getCommitteeSize](./klay/block.md#klay_getcommitteesize)
- [klay_getCouncil](./klay/block.md#klay_getcouncil)
- [klay_getCouncilSize](./klay/block.md#klay_getcouncilsize)
- [klay_getStorageAt](./klay/block.md#klay_getstorageat)
- [klay_mining](./klay/block.md#klay_mining)
- [klay_syncing](./klay/block.md#klay_syncing)


### [트랜잭션(Transaction)](./klay/transaction.md) <a id="transaction"></a>
- [klay_call](./klay/transaction.md#klay_call)
- [klay_estimateGas](./klay/transaction.md#klay_estimategas)
- [klay_estimateComputationCost](./klay/transaction.md#klay_estimatecomputationcost)
- [klay_getTransactionByBlockHashAndIndex](./klay/transaction.md#klay_gettransactionbyblockhashandindex)
- [klay_getTransactionByBlockNumberAndIndex](./klay/transaction.md#klay_gettransactionbyblocknumberandindex)
- [klay_getTransactionByHash](./klay/transaction.md#klay_gettransactionbyhash)
- [klay_getTransactionBySenderTxHash](./klay/transaction.md#klay_gettransactionbysendertxhash)
- [klay_getTransactionReceipt](./klay/transaction.md#klay_gettransactionreceipt)
- [klay_getTransactionReceiptBySenderTxHash](./klay/transaction.md#klay_gettransactionreceiptbysendertxhash)
- [klay_sendRawTransaction](./klay/transaction.md#klay_sendrawtransaction)
- [klay_sendTransaction](./klay/transaction.md#klay_sendtransaction)
- [klay_signTransaction](./klay/transaction.md#klay_signtransaction)


### [환경설정](./klay/config.md) <a id="configuration"></a>
- [klay_chainID](./klay/config.md#klay_chainid)
- [klay_clientVersion](./klay/config.md#klay_clientversion)
- [klay_gasPrice](./klay/config.md#klay_gasprice)
- [klay_gasPriceAt](./klay/config.md#klay_gaspriceat)
- [klay_isParallelDBWrite](./klay/config.md#klay_isparalleldbwrite)
- [klay_isSenderTxHashIndexingEnabled](./klay/config.md#klay_issendertxhashindexingenabled)
- [klay_protocolVersion](./klay/config.md#klay_protocolversion)
- [klay_rewardbase](./klay/config.md#klay_rewardbase)
- [klay_writeThroughCaching](./klay/config.md#klay_writethroughcaching)


### [필터](./klay/filter.md) <a id="filter"></a>
- [klay_getFilterChanges](./klay/filter.md#klay_getfilterchanges)
- [klay_getFilterLogs](./klay/filter.md#klay_getfilterlogs)
- [klay_getLogs](./klay/filter.md#klay_getlogs)
- [klay_newBlockFilter](./klay/filter.md#klay_newblockfilter)
- [klay_newFilter](./klay/filter.md#klay_newfilter)
- [klay_newPendingTransactionFilter](./klay/filter.md#klay_newpendingtransactionfilter)
- [klay_uninstallFilter](./klay/filter.md#klay_uninstallfilter)


### [기타](./klay/misc.md) <a id="miscellaneous"></a>
- [klay_sha3](./klay/misc.md#klay_sha3)
