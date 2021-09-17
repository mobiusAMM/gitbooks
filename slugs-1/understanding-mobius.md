---
description: A cross-chain stableswap AMM on Celo.
---

# Understanding Mobius

> One of the most highly anticipated DeFi products amongst Celo users and developers has been a decentralized exchange tailored to stablecoins. **Today we are happy to announce Mobius, a cross-chain stableswap exchange built on Celo.**

## What makes Mobius unique? <a id="0af7"></a>

[Mobius](https://mobius.money/) is an Automated Market Maker \(AMM\) based on the [StableSwap](https://curve.fi/files/stableswap-paper.pdf) and [CurveCrypto](https://curve.fi/files/crypto-pools-paper.pdf) invariant that specializes in low-slippage swaps between price-stable and interest-bearing pairs, such as liquid staking tokens. Thereby paving the way for more capital efficient trades between similarly priced pairs than that of a pure constant product invariant AMM like Ubeswap. At its core, the Mobius contracts are built from a [Nerve Finance](http://nerve.fi/) variation with modifications to support additional asset types. Let’s discuss the two specific areas Mobius specializes in: \(1\) price stable \(2\) pegged assets, and soon \(4\) interest bearing / liquid staking  tokens and \(4\) capital efficient forex swaps.

### Price Stable Pools <a id="64c7"></a>

Mobius was primarily designed for swaps between assets with market prices that are theoretically equal. Examples include; _cUSD-USDC, cEUR-EURS, and cBTC-wBTC_. The price stability of stablecoins makes the liquidity providing lossless with no [impermanent loss](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22) risk. As such, Mobius is certain to attract ample liquidity for stablecoin pairs with near risk-free yields.

Since every pool can have custom parameters, Mobius can also support any asset pair that has relatively stable exchange rates like cUSD-cEUR. In fact, this was where we see Mobius greatest market potential as a DEX on Celo. The foreign exchange market is one of largest financial markets in the world, processing over $6.6T in daily volume. As the cLabs team continues to issue new stablecoins denominated in varying national currencies, we believe the need to efficiently swap between tokenized foreign currency pairs will be evermore critical. Thus, we envision Mobius to be a critical piece of DeFi infrastructure that enables anyone with a smartphone to tap into Celo’s ecology of stablecoins from their native currency.

### Interest Bearing + Liquid Staking Pools <a id="5336"></a>

Proof of Stake blockchains like Celo require large quantities of their native token to be locked and staked in order to secure their network. These tokens are often left idle and as non-productive assets beyond governance. Fortunately, projects like [sCELO](https://docs.savingscelo.com/) have created tokenized versions of staked CELO that are liquid. Now users can transact with their staked CELO and stack their yields from both passive staking and farming. While you may assume CELO and sCELO are ‘price stable,’ this is actually not the case. 1 CELO is currently equal to roughly 65000 sCELO. Moreover, sCELO accrues interest similarly to [Compound](https://compound.finance/) tokens, with one sCELO theoretically worth more in CELO tomorrow than it is today. However, the price of liquid staking tokens and their underlying assets are highly correlated in price. Therefore, like with price stable pairs, Mobius can offer lower slippage on these trades. By providing an efficient market for CELO-sCELO trades, we may also open the door to new applications, such as using sCELO as collateral for loans on protocols like Moola Market.

## **The Mobius Curve** <a id="5a8f"></a>

The StableSwap invariant \(implemented by Curve\) has normally been used to only swap between assets that are pegged to the same value. However, there is a more generalizable version of the StableSwap invariant named the CurveCrypto invariant \(implemented in Curve V2\) that is more applicable to a wider set of pools. CurveCrypto uses an internal moving average price oracle to concentrate liquidity around the normal trading rate, while keeping liquidity across all prices. We’ve been using historical swap data from Ubeswap to determine which pairs could experience lower slippage from using a more specialized invariant. Ultimately, this will allow users to get better priced trades in an order of magnitude times better.

### Simulations <a id="c1d5"></a>

The results of these simulations will help us determine the ideal parameters to initialize our pools with and quantify the slippage difference over the current array of DEXs on Celo. We based our simulations on the USD/EUR exchange pair because there is a large amount of trade history on Ubeswap and any Celo based exchange would have a negligible impact on the global market. Our simulations involved testing varying values of the amplification coefficient, somewhat equatable constant product invariant with leverage. We calculated slippage values for different trade sizes as well as using the historical trade data to check for liquidity provider returns.

### **Results** <a id="4ea7"></a>

![](https://miro.medium.com/max/30/1*Ft38GUOYQfq4GdF4mC0_9A.png?q=20)![](https://miro.medium.com/max/700/1*Ft38GUOYQfq4GdF4mC0_9A.png)![](https://miro.medium.com/max/30/1*1uVO0kiYHv-LkMtJ6LoJgA.png?q=20)![](https://miro.medium.com/max/700/1*1uVO0kiYHv-LkMtJ6LoJgA.png)

We can see the effectiveness of Mobius over available exchanges. We can also use this data to select the amplification coefficient that would balance low slippage with high liquidity provider returns. The advantages of Mobius are highlighted the most for large swaps that would cause high slippage on traditional decentralized exchanges.

## Liquidity Providers <a id="179c"></a>

For current liquidity providers \(LPs\) on CPMMs like Ubeswap and Sushiswap, Mobius will offer LPs an attractive opportunity deposit their tokens to Mobius and earn trading fees proportional to their position.

### Fee Structure <a id="2ce1"></a>

LPs on Mobius are incentivized with 0.15% trading fees. Through running various simulations, we have determined that this gives us the best balance of liquidity provider returns with offering the best price to swappers. Volume on a stable swap exchange is expected to be much higher and make up for the lower fees. Additionally, pairs with low exchange rate volatility offer a much lower risk of impermanent loss than traditional trading pairs.

## Cross-chain capabilities. <a id="7906"></a>

As an AMM designed to handle swaps between stable assets, we anticipate the surge in foreign stablecoin volume from other chains to skyrocket once an [Optics](https://medium.com/celoorg/announcing-optics-a-gas-efficient-interoperability-standard-for-cross-chain-communication-e597163b2) token bridge goes live. However, no bridge has officially been built yet, and as such, to accelerate the pace we will unveil a full functional custodial bridge to Ethereum and vice versa. This bridge will support a wide variety of ERC-20 token transfers to Celo and should reduce friction for users looking to move their Ethereum liquidity to Celo. That being said, we believe in the future of trustless bridges, namely their security advantages for large transfer sizes. It is why we are especially excited for a token bridge on Optics to launch soon. Once an Optics bridge goes live, we will move fast to integrate and support even more asset transfer from a variety of chains.![](https://miro.medium.com/max/30/0*xo3oDBeXphOIll-6?q=20)![](https://miro.medium.com/max/700/0*xo3oDBeXphOIll-6)

### Bridge to Ethereum <a id="39c5"></a>

A niche advantage for Mobius users is the interface component that will allow anyone on Celo or Ethereum to interact with the bridge and transfer their assets between the two chains. Thereby, we see Mobius as a platform for cross-chain capital migration as well. Enticing liquidity from other chains with high yields on stablecoins and pollinating other chains with Celo’s assortment of stablecoins.

## Our Roadmap <a id="78ac"></a>

![](https://miro.medium.com/max/30/0*XNLJYCqYFk3xIgIA?q=20)![](https://miro.medium.com/max/700/0*XNLJYCqYFk3xIgIA)

## Why launch Mobius on Celo? <a id="7b30"></a>

Celo, being an ultra-light client EVM blockchain with [address mapping to phone numbers](https://twitter.com/CeloOrg/status/1379560095609147397?s=20) and a highly integrated [mobile wallet](https://valoraapp.com/), is perfectly suited to be the go-to layer one for peer to peer payments. In fact, Celo has quickly grown into one of the most used blockchains for P2P payments, processing more transactions than Polkadot and Near [combined](https://twitter.com/CeloOrg/status/1379560095609147397?s=20). Celo is one of the few blockchains that has natively integrated stablecoins with a variety of pegged assets, and we see Mobius playing a critical role in this ecology of value.

## Join the Mobius community! <a id="cd81"></a>

Be sure to join our [Discord](http://discord.gg/arU5TJ8K), follow us on [Twitter](https://twitter.com/MobiusMoney), and check out our [website](https://mobius.money/). Updates will be sent through all three channels in the coming weeks, so stay tuned!

