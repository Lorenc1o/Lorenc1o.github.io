---
title: "Market Microstructure"
date: 2025-07-07
image: /assets/images/microstructure/microstructure.png
categories: [Finance, Trading]
author: "Jose Antonio Lorencio Abril"
lang: en
permalink: "/posts/en/Microstructure/"
toc:
    - 
        title: "Introduction"
        url: "#introduction"
    - 
        title: "Fundamentals"
        url: "#fundamentals"
    - 
        title: "Market Structure"
        url: "#structure"
    -
        title: "Trading Mechanism Research"
        url: "#mechanisms"
    -
        title: "Transaction Costs"
        url: "#costs"
    -
        title: "Conclusions"
        url: "#conclusions"
---

_This post is based on Chapter 2 of the book "Algorithmic Trading and DMA: An Introduction to High-Frequency Trading" by Barry Johnson._

## Introduction {#introduction}

**Market microstructure** deals with the processes and outcomes of exchanging assets under specific trading rules. It analyzes how specific mechanisms affect both observed prices and traded volumes.

Market microstructure can be divided into three main areas:
1. Market structure and design
2. Trading mechanism research
3. Transaction costs measurement and analysis

## Fundamentals {#fundamentals}

**Market function**: to bring buyers and sellers together to accommodate trades. A **primary market** is where new assets/securities are issued, and the subsequent trading occurs in the **secondary market**.

<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  <b>Example</b>: for equities, the primary market is concerned with initial public offerings (IPOs), while the secondary market involves trading existing shares on stock exchanges, such as the NYSE or NASDAQ, and other venues like ECNs (Electronic Communication Networks) or ATSs (Alternative Trading Systems).
</div>

**Market participants**, from the perspective of microstructure, are categorized (i) based on the information they possess:
- **Informed traders**: have private information that allows them to determine the true value of an asset.
- **Liquidity traders**: trade for reasons unrelated to information, such as hedging or portfolio.

and (ii) based on the trading style:
- **Active traders**: demand immediate execution and push prices in the direction of their trades.
- **Passive traders**: provide liquidity by placing limit orders.

<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  Microstructure models show that:
    - Liquidity traders lose money to informed traders, in the long run.
    - Passive traders earn money from active traders, in the long run.
    - Informed traders are vulnerable to information leakage, which can lead to adverse selection. So, they aim to trade quickly and discreetly.
</div>

In the following table, we map the different types of traders to the traditional market participants:

| Microstructure Type | Traditional Market Participant |
|---------------------|-------------------------------|
| Informed Trader     | Hedge Fund, Investment Bank    |
| Liquidity and Active Traders | Retail Trader, High-Frequency Trader, Speculator |
| Passive Trader     | Market Maker, Liquidity Provider |

**Liquidity** refers to the cost of converting an asset into cash and vice versa. The price of an asset is closely related to its liquidity. 

A **liquid market** has lower cost for immediacy and higher trading volumes. The liquidity of a market can be characterized by:
- **Depth**: quantity of buy and sell orders available for the asset, close to the equilibrium price.
<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  Implication: a deep market can absorb large trades without significantly moving the price.
</div>
- **Tightness**: the bid-ask spread, which is the difference between the highest price a buyer is willing to pay and the lowest price a seller is willing to accept.
<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  Implication: a tight spread indicates a liquid market, where traders can enter and exit positions with minimal cost.
</div>
- **Resiliency**: how quickly the market recovers from a shock, such as a large trade or news event. A resilient market returns to its equilibrium price quickly after a disturbance.
<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  Implication: a resilient market can absorb shocks without significant price changes, maintaining stability.
</div>
- **Diversity**: the variety of opinions and information among market participants. A diverse market has a wide range of views, which can lead to more efficient price discovery.
<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  Implication: a diverse market can better reflect the true value of an asset, as it incorporates different perspectives and information.
</div>

## Market Structure {#structure}
The design of markets must accommodate the needs of institutional and individual investors, dealers, and speculators, allowing investors to trade when they want, and minimizing the costs of trading orders, while still allowing dealers to make a profit.

### Types of Markets
Markets can be classified based on their trading mechanism and the trading frequency. The **trading mechanism** can be:
- **Quote-driven**: traders must transact with a dealer who quotes prices for buying and selling.
- **Order-driven**: traders can place orders on an order book, and trades occur when buy and sell orders match.
- **Hybrid**: combines elements of both quote-driven and order-driven markets.
<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  Negotiation is a key difference between order-driven and quote-driven markets. In quote-driven markets, traders negotiate with dealers to agree on a price, while in order-driven markets, trades occur automatically when orders match.
</div>

**Trading Frequency**: markets can also be classified based on the frequency of trades:
- **Continuous**: trades can occur at any time, with prices continuously updated.
- **Periodic**: trades occur at specific intervals, with prices updated at those times.
- **Request-driven**: trades occur when a trader requests a quote from a dealer, who then provides a price for the trade.

Continuous markets based on hybrid mechanisms, with call auctions to determine the opening and closing prices, are the most common in modern financial markets.

### Types of Orders
An order is an instruction to buy or sell a specific quantity of an asset at a specified price or better. The most common types of orders are:
- **Market Order**: an order to buy or sell at the best available price. It is executed immediately at the current market price. -> Demand liquidity and risk execution price slippage.
- **Limit Order**: an order to buy or sell at a specified price or better. It is not executed immediately, but rather added to the order book until it can be matched with a market order. -> Supply liquidity and risk not being executed.
<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  There are hybrid orders, such as **market-to-limit** orders, which are executed as market orders until a specified price is reached, at which point they become limit orders. For example, a **stop order** is a type of market order that is triggered when the price reaches a specified level, allowing traders to limit their losses or protect profits.
</div>

### Trading Protocols
The set of rules that govern how trades are executed in a market. They cover different aspects of trading:
- **Order precedence**: specifies how incoming orders are matched with existing orders in the order book.
- **Minimum quantity**: defines the minimum size of an order.
- **Minimum tick size**: the smallest price increment allowed for an asset.
- **Opening/closing procedures**: rules about how and when the market opens and closes, and how the opening and closing prices are determined.
- **Trading halts and circuit breakers**: mechanisms to pause trading in response to extreme price movements or volatility, allowing the market to stabilize.

### Transparency

Refers to the amount of market information available before and after trades. **Pre-trade information** corresponds to the prices and sizes of orders in the order book, while **post-trade information** relates to actual trade execution details, such as the time, the size, and the price.

Order-driven markets tend to be more transparent than quote-driven markets. However, total transparency is also not always desirable, as it can lead to information leakage and adverse selection. A common solution is to make the order book anonymous.

<div style="border:1px solid black; padding:10px; background-color:rgb(56, 242, 236);">
    Concept: <b>Adverse Selection</b>
    <br>
    - Occurs when one party in a transaction has more information than the other, leading to an imbalance in the transaction. <br>
    - In trading, it can happen when informed traders exploit their knowledge to trade against less informed traders, resulting in losses for the latter. <br>
    - Example: If a trader knows that a stock is about to rise due to positive news, they can buy it before the news is public, leaving other traders unaware of the impending price increase.
</div>

### After-Hours and Off-Market Trading
After-hours trading refers to the ability to trade assets outside of regular market hours, and it is particularly useful for cross-border trading. Price changes in after-hours trading can act as an indicator of next-day opening prices.

Off-market trading takes two main forms:
- The same asset is trading on a range of venues in the same country.
- New assets may be created to permit dual listing in foreign markets.

<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  <b>Centralization VS Fragmentation</b>:
  <br>
  - Centralized markets have a single venue where all trades occur, providing transparency and efficiency.<br>
  - Fragmented markets have multiple venues, which can lead to price discrepancies and inefficiencies, but can provide more transparency and competition among venues.
</div>

## Trading Mechanism Research {#mechanisms}

The trading process can be divided into three main stages:
1. **Price formation**: investors have different views on the value of an asset, and they place orders based on these views. Price formation is based on supply and demand conditions, affected by the market mechanisms.

**Information-based models** work under the assumption that some participants have information advantage over others. The bid-ask spread represents the cost for which the market makers are willing to trade, and should be large enough to compensate for the risk of holding subpar information.

**Inventory-based models** focus on the dealer's inventory management. The inventory level needs to be sufficient to service any incoming orders, so the bid-ask spread increases when the position moves away from the dealer's target inventory level.
<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  <b>Example</b>: If a dealer's inventory is low, they may widen the bid-ask spread to reduce the risk of holding an asset that may decrease in value. The mid-point of the bid-ask spread is skewed upwards. These two effects should (i) compensate the risk of having a small inventory, and (ii) encourage traders to sell to the dealer, allowing them to replenish their inventory.
</div>

In order-driven markets, the price formation is based on the order book. The price is determined by the best bid and ask prices, and the transparency of the order book affects the price formation process. When the highest bid and lowest ask coincide, the market is **locked**. When they surpass each other, the market is **crossed**. In these cases, the market needs to have mechanisms in place to resolve these situations and return to a normal state.

2. **Price discovery / trade execution**: occurs when supply and demand requirements cross. The price at which the trade occurs is determined by the discovery mechanism. There are three main mechanisms for price discovery:
- **Bilateral trading**: represents one-to-one trading mechanisms. Thus, it is used on quote-driven and negotiation-based markets. The price is determined by the negotiation between the buyer and seller, and the trade occurs when they agree on a price.
- **Continuous auction**: consistently applies the matching rules each time an order is added, modified, or cancelled. It needs a queueing mechanism to determine the order of execution. For each order, the system:
      1. Adds the order instruction to the order book.
      2. Trade matching rules are used to see if the order can be matched with existing orders.
      3. The order book is updated to reflect any changes.
      4. Execution notifications are sent for any trades that occurred.
Typically, the priority is based on price, and secondarily on time of arrival and pro-rata (each order is allocated based on its proportion of the total volume available at the price).

- **Call auction**: trades are executed at specific times, with all orders being matched at once. This mechanism is often used for opening and closing prices, and it allows for a more orderly price discovery process, especially in illiquid markets.

3. **Reporting, clearing, and settlement**:
   
   3.1. **Reporting**: one a trade is executed, detailed confirmations are reported to the associated parties and the market authorities.
   
   3.2. **Clearing**: involves validating the trade and settlement details, and ensuring that the buyer and seller have the required funds and assets to complete the trade. This process is crucial for managing counterparty risk and ensuring that trades are settled correctly.

   3.3. **Settlement**: the actual transfer of assets and funds between the seller and buyer. This process is handled by security depositories or dedicated custodians, which also manage any associated interest or dividends.

Clearing and settlement are nowadays very automated. Straight-Through Processing (STP) is a common practice that allows for the automatic processing of trades from execution to settlement, minimizing manual intervention and reducing errors.

Execution venues act as a Central Counterparty (CCP) to the trade, which means that the buyer actually buys from the CCP, and the seller sells to the CCP. This reduces counterparty risk, as the CCP guarantees the trade, even if one of the parties defaults. The parties only need to provide sufficient collateral to cover their trades.

## Transaction Costs {#costs}
Transaction costs are the costs associated with trading assets, and they can significantly impact the profitability of trading.

<div style="border:1px solid black; padding:10px; background-color: #f2a138;">
  <b>Implication</b>: increased cost -> reduced profitability -> investors seek higher returns -> less trading opportunities -> less trading volume -> less liquidity
</div>

### Cost Measurement
Cost measurement focuses on spreads and benchmark prices, which are easy to measure and provide meaningful information about the cost of trading. The most common measures of transaction costs are:
- **Spreads**:
   - Quoted spread: difference between best bid and best ask prices in the order book. Measures market quality.
   - Effective spread: difference between trade price and quote mid-point when order was placed. Measures the execution cost of a trade.
   - Realized spread: difference between trade price and quote mid-point 5 minutes after the trade. Measures the profits of the intermediary (market maker) from the trade.
  <div style="border:1px solid black; padding:10px; background-color: #f2a138;">
    <b>Example</b>: At t=0, the best bid is 100 and the best ask is 102. The trade occurs at 101.1. At t=5, the best bid is 101 and the best ask is 102.
    - Quoted spread = 102 - 100 = 2
    - Effective spread = 101.1 - (100 + 102)/2 = 101.1 - 101 = 0.1
    - Realized spread = 101.1 - (101 + 102)/2 = 101.1 - 101.5 = -0.4
  </div>
- **Benchmark prices**: used to compare the trade price with a reference price, they are a key factor in measuring transaction costs. There are many difference benchmarks, such as:
   - Opening price
   - Closing price
   - Volume weighted average price (VWAP): $$\frac{\sum_{i=1}^{n} p_i \cdot v_i}{\sum_{i=1}^{n} v_i}$$, where $$p_i$$ is the price of the asset at time $$i$$ and $$v_i$$ is the volume traded at time $$i$$.
   - Open High Low Close (OHLC) price: the average of the opening, high, low, and closing prices of the asset over a period of time.
   - Time-weighted average price (TWAP): the average price of the asset over a period of time, weighted by the time spent at each price level.

These benchmarks are classified into:
   - **Pre-trade benchmarks**: based on the order book and market conditions before the trade is executed. Available before the trade.
   - **Post-trade benchmarks**: based on the actual trade execution and market conditions after the trade is executed. Available after the trade.
   - **Intraday benchmarks**: based on the market conditions during the market conditions. They are approximated during the day, and the real value is only known at the end of the day.

### Analyzing the components of transaction costs
- **Explicit costs**: these are the direct costs of trading, such as commissions, fees, and taxes. They are easy to measure and can be directly attributed to a specific trade.
- **Implicit costs**: these are the indirect costs of trading, such as timing cost, delay cost, market impact, and opportunity cost. They are harder to measure as they are not directly observable. Implicit costs are also more variable, while impacting the performance more significantly.

The costs are:
- Commissions: broker's compensation for providing the trading service.
- Fees: costs associated with executing the trade, such as exchange fees, clearing fees, and settlement fees. Usually embedded in the commission.
- Taxes: government-imposed taxes on gains from trading, such as capital gains tax or transaction tax.
- Spread cost: compensates the market maker for providing liquidity and taking on risk.
- Delay cost: the risk of any price change from when the decision is made to when the trade is executed.
- Market impact: how much effect the order has on the asset's price.
- Timing cost: reflects uncertainty about the asset's price and liquidity in the future.
- Opportunity cost: the cost of not being able to trade at the desired price due to market conditions or other factors.

## Conclusions {#conclusions}
We have seen how the different agents in the market interact with each other, under the market set of rules, to form prices and execute trades. Market microstructure tries to understand how these interactions take place, and how they affect the prices and volumes of trades.