indexers
========

[![Build Status](https://travis-ci.org/mwanon/bchd.png?branch=master)](https://travis-ci.org/mwanon/bchd)
[![ISC License](http://img.shields.io/badge/license-ISC-blue.svg)](http://copyfree.org)
[![GoDoc](https://godoc.org/github.com/mwanon/bchd/blockchain/indexers?status.png)](http://godoc.org/github.com/mwanon/bchd/blockchain/indexers)

Package indexers implements optional block chain indexes.

These indexes are typically used to enhance the amount of information available
via an RPC interface.

## Supported Indexers

- Transaction-by-hash (txbyhashidx) Index
  - Creates a mapping from the hash of each transaction to the block that
    contains it along with its offset and length within the serialized block
- Transaction-by-address (txbyaddridx) Index
  - Creates a mapping from every address to all transactions which either credit
    or debit the address
  - Requires the transaction-by-hash index

## Installation

```bash
$ go get -u github.com/mwanon/bchd/blockchain/indexers
```

## License

Package indexers is licensed under the [copyfree](http://copyfree.org) ISC
License.
