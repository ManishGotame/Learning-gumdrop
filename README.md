# Learning-gumdrop

Just exploring and learning

## Gumdrop has been moved to its separate repository

Can run its frontend by going into ``` packages/gumdrop ```

```npm start```


## Create a test wallet

```solana-keygen new -o ~/.config/solana/devnet.json```


## Create a spl token and mint it

Spl token is equivalent to ERC-20 token in the ethereum network

```
spl-token create-token --decimals 0

spl-token create-account <token address> 

spl-token mint <token address> <value>

spl-token accounts (to check the balance of token)

```

## Create a distirbution list
The list is a json file containing the wallet address and the amount of token they are supposed to recieve

```
[
  {
    "handle": <address>,
    "amount": <claimable amount>,
    ["Edition": <Edition number>] // not needed for spl-tokens
  }
]
```

## Create the gumdrop distribution

Required items:

1) keygen pair: the solana account you created
```./~/.config/solana/devnet.json```

2) spl-token account
``` spl-token accounts```

Run the code:

```
ts-node gumdrop/packages/cli/src/gumdrop-cli.ts create -e devnet --keypair ./~/.config/solana/devnet.json --distribution-list whitelist.json --claim-integration transfer --transfer-mint JEEqZsbHRkGVt2aYQDEhNzY276zbnz2SSSEkbqoJAf6Z --distribution-method wallets
```












