# requests-bitcoin-cli

A tiny script to run Bitcoin JSON-RPC commands using requests

## Usage

```python
from rpc import BitcoinCLI

# port: 18332 - testnet, 18443 - regtest, 8332 - mainnet
cli = BitcoinCLI("bitcoinrpc", "mysecretpassword", port=18443)

print(cli.url)

print(cli.getmininginfo())

print(cli.listwallets())

##### WORKING WITH WALLETS #########

# specify wallet name as a key argument
print(cli.getbalance(wallet=""))

# or create a new instance for this wallet
w = cli.wallet("mywallet") # will load default wallet.dat

# url will be different
print(w.url)

print(w.getbalance()) # now you can call commands for the wallet
```