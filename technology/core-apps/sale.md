---
description: An overview of the sales process on Unit Network.
---

# 🛍 Sale

## Similar&#x20;

## Overview

SaleHow to and Why to launch a token for a project, idea, or startup

## Overview

If you’re new to the world of crypto, figuring out how to buy Bitcoin, Ethereum and other cryptocurrencies can be confusing at first. Thankfully, it’s pretty simple to learn the ropes and we've done our best at Unit Network to make the the process even easier and more secure.



&#x20;

### Step 3: Manage your token growth

* Funds from the token sale goes directly to that tokens “operational bank” which is viewable to investors, both current and potential. These funds are accessible to the token creator for operational expenses and growth.
* If you generate revenue then it is your direct responsibility to move funds to the bank. This encourages new investment and keeps current investors happy that their stake is on its way to growing.
* Any funds not needed directly for operational expenses can and should be added to your treasury.
  * To set a floor price. This creates the underlying value for the asset. For example: if total supply is 1million tokens and $1million in revenues/raised funds is added from the Bank to the Treasury, the minimum price someone is willing to sell/buy for 1 token is $1. However if that $1million was in the Bank only then technically it can be spent.&#x20;
  * Increase confidence. Stakeholders now have confidence in their investment knowing there is a minimum price their stake is worth. This will encourage many to invest further.

## Technical Overview

The sales feature enables users to sell a specified quantity of tokens at a fixed price. Selling tokens is an effective way for token creators to generate revenue for operational expenses and growth. There are several extrinsic functions exposed to the creator of a token for staging sales and updating aspects of a sale. There is a buy extrinsic for any user who wishes to buy a token using any token native to the Unit network.

{% hint style="info" %}
All operations require a signed account as the origin.

The ownership of the sale asset is checked in multiple functions.

Various checks ensure that certain values like price, quantity and bonuses are within acceptable thresholds.

Some operations require the user to have a registered profile.

Any asset listed for sale should be registered in the oracle pallet.
{% endhint %}

## Creating a sale stage

“Sale stage” is the term used to describe an asset for sale, or in other words, an asset staged for sale. The only user that can create a sale stage for an asset is the creator of the asset. A stage sale specifies a quantity of token for sale at a set price, and in order to be created, the token’s bank must have enough balance to cover the quantity being sold. Each sale stage is saved to storage and can be identified by a number id which is incremented with every sale stage creation. Once a sale stage is successfully created, an event is signaled to the blockchain. There are separate extrinsic functions exposed to the creator of a sale stage to update the sale price and quantity. A sale stage is considered “active” if it has not been bought or closed by the sale creator. If a sale has been bought or closed, it is saved to storage as “completed”. A sale creator has the ability to close a sale before a purchase using the close\_sale extrinsic function.

## Buying a sale

When a buy succeeds, the bought asset is transferred from its bank to the buyer’s wallet, and the asset used to purchase is transferred from buyer to bank. If the sale stage creator configured bonus allocations, then bonuses would be subtracted from the amount paid to the bank, and the amount paid to the buyer. Joining the Unit network requires an invitation from a current user. The inviter of the buyer could receive a portion from both the crypto being used to purchase the asset, and receive a portion of the asset being bought, depending on the role of the inviter and how the sale creator configured the bonuses.

## Setting bonuses

There are six possible bonuses to be set, and will be paid out depending on the role of the inviter. The inviter can be registered as either a core team member, an advisor or a community member. The following bonuses are initially set to zero when a sale stage is created, but afterwards, can be set as percentages by the sale creator using the set\_bonuses extrinsic function.&#x20;

**Core team cash bonus:** If the inviter is a core team member then they could receive this bonus percentage, which would be subtracted from the asset amount used to buy.

**Core team token bonus:** In addition to the “core team cash bonus”, a core team member could receive a percentage of the asset being bought.

**Advisor cash bonus:** If the inviter is an advisor then they could receive this bonus percentage, which would be subtracted from the asset amount used to buy.

**Advisor token bonus:**  In addition to the “advisor cash bonus”, an advisor could receive a percentage of the asset being bought.

**Community cash bonus:**  If the inviter is a community member then they could receive this bonus percentage, which would be subtracted from the asset amount used to buy.

**Community token bonus:** In addition to the “community cash bonus”, a community member could receive a percentage of the asset being bought.

\


\
