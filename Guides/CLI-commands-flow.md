# Imversed CLI commands flow

```
- name: mary
  address: imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x
```

```
- name: john
  address: imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r
```


## IMV TOKENS (transfer, gas, fees)

#### check john's balance
``` 
./imversed q bank balances \
    imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    --node https://tx-endpoint-test.imversed.com:443
```

#### check mary's balance
```
./imversed q bank balances \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443

```
#### send john -> mary

```
./imversed tx bank send \
    imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    5000aimv \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --fees 200aimv
```
#### check transaction result
```
./imversed q tx --type hash \
    BF0073E745373BD378EF0840501EC15DFD617B34EDF62B7F940DDBEE584821BE \
    --node https://tx-endpoint-test.imversed.com:443
```

#### check mary's balance
```
./imversed q bank balances \
   imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
   --node https://tx-endpoint-test.imversed.com:443
```

#### send john -> mary with gas auto no fees

```
./imversed tx bank send \
    imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    500aimv \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --gas auto
```

#### send john -> mary with gas auto with less fees because of gas auto

```
./imversed tx bank send \
    imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    500aimv \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --gas auto --fees 200aimv
```

#### check transaction result

```
./imversed q tx --type hash \
    [tx_hash] \
    --node https://tx-endpoint-test.imversed.com:443
```

## CREATE A TOKEN

#### issue denom from john
```
./imversed tx currency issue johntoken ""\
    --from imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --gas auto \
    --fees 200aimv
```

#### check transaction result
```
./imversed q tx --type hash \
    1B2888D76D5BB963D14759B0699104F5D79203E5A4C603E94419AE593DEA0BF1 \
    --node https://tx-endpoint-test.imversed.com:443
```

#### check currency list
```
./imversed q currency list \
    --node https://tx-endpoint-test.imversed.com:443
```

#### mint some tokens from john no gas (tx fails)
```
./imversed tx currency mint \
    100000000johntoken --from imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 \
    --fees 200aimv
```

#### check transaction result (tx fails, no gas provided)
```
./imversed q tx --type hash \
    TX_HASH \
    --node https://tx-endpoint-test.imversed.com:443
```

#### mint some tokens from john with gas and fees
```
./imversed tx currency mint \
    100000000johntoken --from imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 \
    --fees 2000aimv --gas auto
```

#### check transaction result (tx fails, no gas provided)
```
./imversed q tx --type hash \
    [tx_hash] \
    --node https://tx-endpoint-test.imversed.com:443
```

#### check john's balance
```
./imversed q bank balances \
   imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
   --node https://tx-endpoint-test.imversed.com:443
```

#### mint some tokens from mary in john's denom with gas and fees (fails: sender is not owner)
```
./imversed tx currency mint \
    100johntoken --from imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 \
    --fees 2000aimv --gas auto
```

#### issue denom mary
```
./imversed tx currency issue marytoken ""\
    --from imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --gas auto \
    --fees 200aimv
```

#### check currency list
```
./imversed q currency list \
    --node https://tx-endpoint-test.imversed.com:443
```

#### mint some tokens from mary with gas and fees
```
./imversed tx currency mint \
    2000marytoken --from imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 \
    --fees 2000aimv --gas auto
```

#### check transaction result (tx fails, no gas provided)
```
./imversed q tx --type hash \
    [tx_hash] \
    --node https://tx-endpoint-test.imversed.com:443
```

#### check mary's balance
```
./imversed q bank balances \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443
```

#### send john -> mary johntoken
```
./imversed tx bank send \
    imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    5000johntoken \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --fees 200aimv
```
#### check mary's balance
```
./imversed q bank balances \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443
```

## LIQUIDITY POOLS
#### john creates l-pool
```
./imversed tx pools create-pool  \
    --pool-file pool.json \
    --from imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --fees 200aimv
```

#### check transaction result (tx fails, no gas provided)
```
./imversed q tx --type hash \
    4398D97260E56819D17681E90B69A6823A7BE7D013F3680FD224AA2848A413CD \
    --node https://tx-endpoint-test.imversed.com:443
```

#### check pools list
```
./imversed q pools pools \
    --node https://tx-endpoint-test.imversed.com:443
```
    
## SWAP
    
#### check mary's balance before swap
```
./imversed q bank balances \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443
```

#### get swap amount estimate
```
./imversed q pools estimate-swap-exact-amount-in 1  \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    1000aimv --swap-route-denoms johntoken --swap-route-pool-ids 1 \
     --node https://tx-endpoint-test.imversed.com:443
```

#### mary swaps johntoken in aimv
```
./imversed tx pools swap-exact-amount-in 500aimv 2 \
    --swap-route-pool-ids 2 --swap-route-denoms johntoken \
    --from imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --fees 200aimv
```
#### check transaction result
```
./imversed q tx --type hash \
    60554DCB3186945DEE747F94353E2C556D1E90555C72FB43A0B6E3E915202859 \
    --node https://tx-endpoint-test.imversed.com:443
```

#### check mary's balance
```
./imversed q bank balances \
    imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443
```

## NFT
#### john issues nft denom
```
./imversed tx nft issue johnnftdenom \
    --from=imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    --name=johnnftdenom --mint-restricted=false \
    --update-restricted=false \
    --schema=https://metachain-web.fdvr.co/nft/schemas/schema.json \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --fees 200aimv
```

#### check nft denoms
```
./imversed q nft denoms \
     --node https://tx-endpoint-test.imversed.com:443
```

#### mint nft
```
./imversed tx nft mint johnnftdenom john_nft_id_1 --uri https://picsum.photos/id/237/700/500 \
    --from imv1xphu0vapz3pklrdl65g8s4ul9mfkff0zrfmv5r \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --fees 200aimv
```
    
#### check nft johnnftdenom nft collection
```
./imversed q nft  collection johnnftdenom  \
     --node https://tx-endpoint-test.imversed.com:443
```

#### mint nft from john nft denom but from mary, mary will be owner
```
./imversed tx nft mint johnnftdenom john_nft_id_2 --uri https://picsum.photos/id/200/700/500 \
    --from imv13cct0vjpr89w6ycaw4rjtkvwjgfwpwqp97t95x \
    --node https://tx-endpoint-test.imversed.com:443 \
    --chain-id imversed-test-1 --fees 200aimv
```
