# ethcc

> **Unmaintained — do not use.** This project is archived and kept for reference only.
>
> - It targets the web3.py 5 API (`buildTransaction`, `toChecksumAddress`,
>   `setGasPriceStrategy`, ...), which current web3.py no longer has, so it fails at
>   construction.
> - Contract functions are called with `.call()`, and when the result is `True` a real
>   signed transaction is sent. A read-only function returning `True` would therefore
>   spend gas.
> - Transactions are hard-coded to chain id 1 (mainnet) with legacy gas pricing.
>
> Use web3.py's [contract API](https://web3py.readthedocs.io/) directly, or
> [ape](https://github.com/ApeWorX/ape), which choose between call and transaction
> from the function's ABI.

Ethereum smart contracts interface on top of web3py

In `example.py` you can find a definition for a `flag map` smart contract where you have two methods, `updateFlagCoords` and `flagIdToCoords`. Those two methods are said to accept and return an array of two ints, and in the model you can see how that is handled, so by defining an `encode` method and a `decode` method: those two will be automatically picked up - if defined - by the contract interface (`ethcc/contract_interface.py`).
