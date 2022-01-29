## Introduction

This article will go over the fundamental commands for interacting with a test instance of the Imversed network. The
primary commands for transferring funds, issuing NFTs, and creating a new token are examined.

### CLI Command structure

In order to use Imversed the user needs a binary client and know the address of a full node.

List of binaries for different architecture and OS:

```
https://static.fdvr.co/apps/imversed/imversed_windows_amd64.tar.gz
https://static.fdvr.co/apps/imversed/imversed_linux_amd64.tar.gz
https://static.fdvr.co/apps/imversed/imversed_darwin_arm64.tar.gz
https://static.fdvr.co/apps/imversed/imversed_darwin_amd64.tar.gz
```

After downloaded app requires no setup and could be used from any directory.

Most of CLI commands has the same structure and contains command, module name, action and parameters

```imversed command [module] [action] [parameters] --node nodeaddress:port```

In order to run command over test network node address should be added as parameter to every command. Node address of
test network is: ```http://qs.imversed.com:26657```

So testnet commands may look like:

```imversed command [module] [action] [parameters] --node http://qs.imversed.com:26657```

List of commands we review in this tutorial is:

- keys: Manage your application's keys
- query (or just q): Readonly requests to blockchain state
- tx: Modify blockchain state commands

### Address/Wallet

All assets in Imversed belongs to accounts. Account (or wallet) is a public/private key pair. Public key contains public
address which is used for transferring and identification. In imversed address will look like: `imv*`.

In order to create your own address you need to execute the next command:

_Request_:

```imversed keys add general-barnaky```

_general-barnaky is a random name and could be replaced by any other name_

_Response:_

```
- name: general-barnaky 
  type: local 
  address: imv172ddedlnl94xp8705eg0rrwyy6ce5vjpzf88rv 
  pubkey: '{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A49EqEiCCe0QyPTPee8 3lYQ/bZyuvV98SMYcE9XemdNq"}' 
  mnemonic: ""
  
  **Important** 
  write this mnemonic phrase in a safe place. It is the only way to recover your account if you ever forget your password. 
  
  Encoded Private Key
  
  fence diamond vibrant this cargo entire clay genuine world welcome veteran
  sand gloom social crew catalog symptom load month snack private stumble ****** ******
```

You've just generated a pair of public and private keys on your local machine. Make a copy of your address and use it to
communicate with others. Other members of the community - the address is not a secret. Mnemonic phrases are your most
important secret and must be remembered. never saved or remembered and never shared with anyone. If you need to recover
your address in the future for any reason, you must run the command.:

```imversed keys add juggoknot –recover```

_juggoknot is a random name and could be replaced by any other name_

## Bank:

The bank module is in charge of storing, transferring, and displaying all assets available on the network in the form of
IMV coins and user-created tokens. Let's take a look at some of the most commonly used bank module commands.

Command to check overall network balance:

_Request_:

```imversed q bank total --node http://qs.imversed.com:26657```

_Response_:

```
pagination:
next_key:
null total: "1"
supply:

- amount: "204117083327187"
  denom: nimv How to check balance To check balance of a particular user we need to get the public address of the
  him/her. imv172ddedlnl94xp8705eg0rrwyy6ce5vjpzf88rv
```

_Request_:

```imversed q bank balances imv172ddedlnl94xp8705eg0rrwyy6ce5vjpzf88rv --node http://qs.imversed.com:26657```

_Response_:

```
balances: 
  - amount: "100200"   
    denom: nimv 
    pagination:   
      next_key: null
      total: "0"
```   

In general a command to send funds from one account to another will looks like:

```
imversed tx bank send [from] [to] [amountdenom] --from [key-name] --node http://qs.imversed.com:26657
```

Please note that every transaction requires `fees` to be paid through `--fees` parameter. Simple transactions like funds
transfer may require as little as 300 nano IMV which should be defined as `300nimv`. For example:

_Request_:

```
imversed tx bank send imv172ddedlnl94xp8705eg0rrwyy6ce5vjpzf88rv imv1kge5sxr3krwmqyt2f26l723edh70tw48ksnqhp 100200nimv \ 
    --from general-barnaky --node http://qs.imversed.com:26657
```

Because all transactions are async, the response from this command simply informs you that a TX was sent to a node and
returns the transaction hash. Hash is a unique identifier that aids in the identification of specific transactions. To
see the current status of a transaction, issue a 'q tx' request with the transaction hash as a parameter.

```imversed q tx [transaction_hash] --node http://qs.imversed.com:26657```

## NFT

Here is a guide to create an NFT. Before creating an nft we need to create a denomination, as in our network NFT is a
first class entity. A denomination is a collection. Issue denomination CLI This command is used to create

### Create denomination

_Request_:

```
imversed tx nft issue bos --name "Brotherhood of steel" --mint-restricted=false \ 
    --update-restricted=false --schema "https://s.imversed.com/nft/schemas/default.json" \ 
    --fees 300 nimv --from "general-barnaky" --node http://qs.imversed.com:26657
```

_Response_:

```
...
txhash: C09133B78505C8F7C8A366B8FF9332F9C2FFDB591A1D333FDD4B3CDDB63B6432
... 
```

We can check the denomination issue transaction status the same as we did it for bank using ```q tx``` command with
transaction hash provided:

_Request_:

```
imversed q tx C09133B78505C8F7C8A366B8FF9332F9C2FFDB591A1D333FDD4B3CDDB63B6432 --node http://qs.imversed.com:26657
```

_Response_:

```
code: 0
...
height: 921956
...
txhash: C09133B78505C8F7C8A366B8FF9332F9C2FFDB591A1D333FDD4B3CDDB63B6432
```

Transaction contains a lot of fields, but most interesting are code and height. Code 0 means transaction successfully
included into a block. Height is a number of the block which includes the transaction.

### List of denominations

To check the list of denominations exists in the blockchain execute the given command.

```
imversed q nft denoms --node http://qs.imversed.com:26657
```

### Mint NFT

After creating the denominations next step is to mint a NFTs. NFT command requires denomination ID and NFT ID and few
required parameters `imversedd tx nft mint <denom-id> <nft-id> --uri=<uri> --data=<data>`. Parameters detail:

- denom-id: denomination have to be created before minting any NFT
- nft-id: only letters and digits and starts from a letter
- uri (--uri parameter): uri for supplemental off-chain tokenData (should return a JSON object)
- data (--data parameter): the origin data of the nft

_Request_:

```
imversed tx nft mint bos alpha --name "Bunker Alpha" \ 
--data "{ 'description': 'Bunker Alpha is a location in Fallout Tactics. It is a base of operations for the Brotherhood of Steel in the Midwest, located in the area near the former city of Chicago, Illinois, being formed sometime after the Brotherhood airships crashed there.', 'ImageUrl': 'http://img3.wikia.nocookie.net/__cb20130113155811/fallout/images/6/64/FoT_Bunker_Alpha.png'}" \
--from general-barnaky --fees 300nimv --node http://qs.imversed.com:26657
```

Request a NFT data in Imversed could be done by this command:

_Request_:

```
imversed q nft token bos alpha --node http://qs.imversed.com:26657
```

_Response_:

```
data: |-
{ 'description': 'Bunker Alpha is a location in Fallout Tactics. It is a base of operations for the Brotherhood of Steel in the Midwest, located in the area near the former city of Chicago, Illinois, being formed sometime after the Brotherhood airships crashed there.',
'ImageUrl': 'http://img3.wikia.nocookie.net/__cb20130113155811/fallout/images/6/64/FoT_Bunker_Alpha.png'}
id: alpha
name: Bunker Alpha
owner: imv172ddedlnl94xp8705eg0rrwyy6ce5vjpzf88rv
uri: ""
```

To find all the NFTs minted in a particular denomination run this command:

_Request_:

``` 
imversed q nft collection bos --node http://qs.imversed.com:26657
```

_Response_:

```
collection:
  denom:
    creator: imv172ddedlnl94xp8705eg0rrwyy6ce5vjpzf88rv
    id: bos
    mint_restricted: false
    name: Brotherhood of steel
    schema: https://s.imversed.com/nft/schemas/default.json
    symbol: ""
    update_restricted: false
  nfts:
  - data: |-
      { 'description': 'Bunker Alpha is a location in Fallout Tactics. It is a base of operations for the Brotherhood of Steel in the Midwest, located in the area near the former city of Chicago, Illinois, being formed sometime after the Brotherhood airships crashed there.',
      'ImageUrl': 'http://img3.wikia.nocookie.net/__cb20130113155811/fallout/images/6/64/FoT_Bunker_Alpha.png'}
    id: alpha
    name: Bunker Alpha
    owner: imv172ddedlnl94xp8705eg0rrwyy6ce5vjpzf88rv
    uri: ""
pagination:
  next_key: null
  total: "0"
```

## Currency module

People can create their own tokens using the currency module. Assume General Barnaky wishes to create a token of the
Brotherhood of Steel and distribute it to its members. Token denomination must be introduced prior to the minting of
tokens. The only requested parameter is the denomination's name.
_Request_:

```
imversed tx currency issue "scrip" --from general-barnaky --fees 300nimv --node http://qs.imversed.com:26657
```

Next step is to mint tokens themselves. It is heavy operation and requires 3000000nimv paid as fee. Required paramters
are denomination-id and amount of tokens followed by token name:

_Request_:

```
imversed tx currency mint 1000000000000000scrip --from general-barnaky --gas auto --fees 3000000nimv --node http://qs.imversed.com:26657
```

Because Imversed does not support decimal, it is best to issue the desired number of coins multiplied by 1.000.000.
Let's say you need 200.000 xyz tokens; the recommended amount is 200.000.000.000.

Minted tokens will be added to the issuer's balance and can be checked via the bank module:
_Request_:

```
imversed q bank balances imv172ddedlnl94xp8705eg0rrwyy6ce5vjpzf88rv --node http://qs.imversed.com:26657
```

_Response_:

```
balances:
- amount: "193898300"
  denom: nimv
- amount: "1000000000000000"
  denom: scrip
pagination:
  next_key: null
  total: "0"
```

### Send custom tokens

Custom tokens could be sent using same mechanism as IMV coin using the Bank module. Command
overview : `imversed tx bank send [from] [to] 1000000000scrip --node http://qs.imversed.com:26657`

_Request_:

```
imversed tx bank send imv172ddedlnl94xp8705eg0rrwyy6ce5vjpzf88rv imv1kge5sxr3krwmqyt2f26l723edh70tw48ksnqhp 100200scrip \ 
    --from general-barnaky --fees 100nimv --gas auto --node http://qs.imversed.com:26657
```

## Conclusion

Imversed blockchain has far more capabilities than those described in this article. More information can be obtained
from the Imversed client via CLI help. 











