# php-ethereum-offline-tx [![Build Status](https://travis-ci.org/kornrunner/php-ethereum-offline-tx.svg?branch=master)](https://travis-ci.org/kornrunner/php-ethereum-offline-tx)  [![Coverage Status](https://coveralls.io/repos/github/kornrunner/php-ethereum-offline-tx/badge.svg?branch=master)](https://coveralls.io/github/kornrunner/php-ethereum-offline-tx?branch=master)

Pure PHP Ethereum Offline Transaction Signer

## Installation

```sh
$ composer require kornrunner/ethereum-offline-tx
```

## Usage

```php
use kornrunner\Ethereum\Transaction;

$nonce    = '04';
$gasPrice = '03f5476a00';
$gasLimit = '027f4b';
$to       = '1a8c8adfbe1c59e8b58cc0d515f07b7225f51c72';
$value    = '2a45907d1bef7c00';

$privateKey = 'b2f2698dd7343fa5afc96626dee139cb92e58e5d04e855f4c712727bf198e898';

$transaction = new Transaction ($nonce, $gasPrice, $gasLimit, $to, $value);
$transaction->sign ($privateKey);
$transaction->getRaw ();
// f86d048503f5476a0083027f4b941a8c8adfbe1c59e8b58cc0d515f07b7225f51c72882a45907d1bef7c00801ba0e68be766b40702e6d9c419f53d5e053c937eda36f0e973074d174027439e2b5da0790df3e4d0294f92d69104454cd96005e21095efd5f2970c2829736ca39195d8
```