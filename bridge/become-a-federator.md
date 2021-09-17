# Moss Bridge

## What is the moss bridge?

In order to facilitate liquidity onboarding to the Celo network, we have partnered with the moss.earth team to add new assets to the existing moss token bridge. Currently, the moss token bridge supports the bidirectional bridging of the native cUSD and MCO2. The bridge was initially forked from the RSK bridge. This bridge allows for token transfers by having sets of contracts on the Ethereum and Celo chains using a federation network as an intermediary. The federation network consists of multiple federators that report the transactions on the base chain. Once enough confirmations have been produced by the federators, the transaction is published on the destination chain. We are aware of the centralized nature of the bridge but we want to give users the ability to bridge assets if they want to. 



**Moss Bridge average confirmation time:** ~1 hour and 15 minutes.

Below is tutorial by @human0x on how to use it from the original bridge UI.

## Tutorial 

{% embed url="https://www.youtube.com/watch?v=2X40nMudlZs" %}

## Costs

Looking at historical transaction history, the average Ethereum gas cost of bridging an asset from Ethereum is about .008 Ether ~$25. Currently the federators all have to pay the transaction costs of publishing transactions to the destination networks. This comes out to .013 Ether on average. We are working with the moss.earth team to add a transaction fee to each bridging transaction that would be sent to the federation so they could use it to pay for gas fees.  

## Side Tokens \(ERC-777\)

Side Tokens are minted and assigned to the same address that originally called the bridge. Since each side token is always backed 1:1 to its original token and vice versa, the original tokens are locked up in the Celo Bridge contract. Then the side tokens are burned, and the original tokens are “unlocked” and transferred to the same address that originally called the bridge.  It is important to note that the sale or purchase of a side token will have the same effect on the original token, and the original token ownership will be transferred to the receiving address. 

The Side token will be represented by the same symbol but with a prefix and have its own unique 18 decimal address. ****An ERC-777 token on Celo that mirrors that existing ERC-20 token on Ethereum. Unique, is that the ERC-777 displays the exact same properties of an ERC-20 token. This also means that there is no increase in the token supply, when the bridge is used. Having a standalone token for each blockchain, in this case 2, offers more versatility in use cases. ****

## **Limits**

**Daily Limit:** 1000 cUSD per day.

**Token Listing:** To avoid a hack, each supported token has to be placed on a whitelist that is managed and curated by the Dahlia Finance and OpenCelo team. 

**Incentives:** As of right now, there are no fees.  


## **Confirmations**

* 120 for Celo and Ethereum on small transactions
* 240 for Celo and Ethereum on medium transactions 
* 5760 for Celo and Ethereum on large transactions  

Values defined per token and are visible in this [Token List](https://tokenbridge.rsk.co/#token-list). 

## **Federators** 

A collection of federators are in charge of validating each transactions between Celo and Etherem from the event log through a staking mechanism where federators stake their reputation and vote.

At the moment, all the federators are run by the Moss team. If you would like to run one, please reach out to support@onepercent.io for more information.  


##  ****

##  

