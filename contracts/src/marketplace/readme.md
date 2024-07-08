# Plooty Marketplace Contract

Plooty Marketplace allows users Buy Sell NFTs


Plooty marketplace smart contract allows users to buy and sell NFTs. A seller list an NFT for sales by specifying a certain price, and anyone can buy it by paying the demanded price.

There are 4 actions that available to plooty Marketplace interact with this aiken-lang smart contract:

- list asset
- buy asset
- updating listing
- cancel listing

## Initialize the Marketplace

Utilizing the Marketplace contract requires a blockchain provider and a connected browser wallet. Here is an example how we can initialize the Marketplace.

```
import { PlootyMarketplaceContract } from '@meshsdk/contracts';
import { BlockfrostProvider, MeshTxBuilder } from '@meshsdk/core';

const blockchainProvider = new BlockfrostProvider(APIKEY);

const meshTxBuilder = new MeshTxBuilder({
  fetcher: blockchainProvider,
  submitter: blockchainProvider,
});

const contract = new PlootyMarketplaceContract(
  {
    mesh: meshTxBuilder,
    fetcher: blockchainProvider,
    wallet: wallet,
    networkId: 0,
  },
  'addr1qytwdrrh5g4h7e0rv4dtmflylwe7yqsevulltx3k0xzu98rr4quhjmjxf2qmh49hcjf0u4dhx4p4wnrk3mha3lqqg4tqry05su',
  200
);
```


Second and third parameters are the ownerAddress and feePercentageBasisPoint. The ownerAddress is the address of the marketplace owner which will receive the marketplace fee. The feePercentageBasisPoint is the percentage of the sale price that the marketplace owner will take. The fee numerator is in the order of hundreds, for example 200 implies a fee of 2%.
