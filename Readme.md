# Ranploy

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/3cc4f4c6999f48738ff8c6dbe26b11b7)](https://www.codacy.com/app/lucadanielcostin/ranploy)
[![PyPI](https://img.shields.io/pypi/v/ranploy.svg)](https://pypi.org/project/ranploy/)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/ambv/black)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=cleanunicorn_ranploy&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=cleanunicorn_ranploy)

Tool to generate the transaction payload `data` that will deploy a random hex string as a smart contract.

## Install

```console
$ pip install --user ranploy
```

## Demo

[![asciicast](https://asciinema.org/a/5Z0qEdjjb5fVvvYZbmhi6zxZq.svg)](https://asciinema.org/a/5Z0qEdjjb5fVvvYZbmhi6zxZq)

## Example

```shell
$ ranploy --bytecode 11223344
6004600d60003960046000f30011223344
```

You then need to create a transaction and use this as the payload data

```console
web3.eth.sendTransaction({
    from: "0x8d26D6d498a01243820154c7Ddb63b47c00DbF6e",
    data: "0x6004600d60003960046000f30011223344"
})
```

Your contract will have this bytecode

```console
web3.eth.getCode("0xDdB083baD281D7242FF69E36c7565b003785cb1A")
'0x11223344'
```
