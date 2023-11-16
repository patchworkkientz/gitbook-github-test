---
description: >-
  An overview of how the treasury works, use cases, conditions, how to send and
  redeem from the treasury, and additional FAQs.
---

# 💎 Treasury

**Similar**\
Book Value \
Bankruptcy/insolency Claims&#x20;

## Overview

In the Unit token economy, the Treasury is a transparent, immutable way by which value can be distributed to token holders.  Whatever assets are added to the Treasury become the reserve assets of the enterprise and give token holders ownership of those assets equal to their proportion of token holdings.

The value that backs a token through its treasury operates as a kind of reserve asset or “book value” that exists even if the market sours on the speculative value of the token trading on the market. If all else fails, token holders can remove value from the treasury in proportion to their ownership.  As a result, it is likely that the speculative value will generally remain at or above the value in the treasury.

## **Use**

**Every token created on Unit Network has access to its own treasury.**

* Once digital assets are transferred into a tokens' treasury they are only redeemable by the token holders, who can choose to sell their tokens back to the treasury and redeem whatever digital assets have been sent there.
* The Treasury is a mechanism by which any user can establish the floor price of a token and substantiate the tokens value with deflationary digital assets like Bitcoin.
* The Treasury is a transparent, immutable way by which value can be distributed to token holders. Whatever is added to the Treasury become the reserve assets of the enterprise and gives token holders ownership of those assets equal to their proportion of token holdings.

{% hint style="success" %}
**Keep an eye on token treasuries!** If there's nothing in the treasury, the token value is speculative with no clarity on downside risk and we would advise caution.
{% endhint %}

## Conditions

**The funds in the treasury are locked and can only be redeemed by token holders.** Not even the token creator is able to remove the crypto held unless they send their tokens back to the treasury to redeem their portion on the crypto held there. When redeeming blue chips from the treasury the tokens are 'burned'.&#x20;

There are two ways that digital assets are sent to a token’s treasury. &#x20;

1. The first is by the token creator, who can transfer funds from the token’s bank or their personal wallet.&#x20;
2. The second is during an exchange with the token’s liquidity pool, which automatically sends a 0.5% exchange fee to the token’s treasury.  Once digital assets are transferred into a token's treasury, they are only redeemable by token holders.

{% hint style="info" %}
Everyone can see the bank and treasury on the token page of any token on the Unit Network, including UNIT.
{% endhint %}

## How to send crypto to the Treasury

1. Click on the <mark style="color:purple;">Wallet</mark> page from the sidebar navigation
2. Select <mark style="color:purple;">Transfer</mark>
3. Click <mark style="color:purple;">To Treasury</mark> on the transfer module
4. Choose token and amount to be transferred
5. Click <mark style="color:purple;">Transfer</mark>

## How to redeem from the Treasury

1. Click on <mark style="color:purple;">Explore</mark> page from the sidebar navigation
2. Search for the token you wish to redeem from and select it
3. Click on the <mark style="color:purple;">Treasury</mark>
4. Click <mark style="color:purple;">Redeem</mark>
5. Select the token that you wish to redeem and enter the amount
6. Click <mark style="color:purple;">Redeem</mark>

## **Technical Overview**

Every token in the Unit network has a treasury and can hold other tokens. Treasuries allow users to lock and redeem tokens. The tokens a treasury holds are considered the underlying collateral for the treasury's token. Treasuries are like holding companies, the treasury token is an ownership share of the assets being held.

## Storage

The balance of each token a treasury holds can be accessed via a storage type defined by the treasury palette. Transaction details for every transfer to the treasury are also saved to storage; including origin of transfer, the treasuries identifying token, the token being transferred and a timestamp. Every transaction is identified by an incremented value.

## Transferring & Redeeming

There are several treasury extrinsic operations exposed to the user via the Unit app. There are three operations for transferring tokens to the treasury from either the user's wallet, from a token bank or from a liquidity pool. The treasury pallet will signal when such a transfer event occurs. If a user transfers tokens to its treasury, those tokens are burned, thus decreasing the total supply of that token. The only transfers that can be accomplished via the treasury pallet are transfers to a specified token treasury; no transfers out. If a user wants to regain some value transferred to a treasury, they must redeem that value using their holding of the treasury’s token. Redeeming tokens is an extrinsic operation exposed to any user by the treasury palette. To successfully redeem tokens from the treasury, there are several checks that must pass.

### Checks

1. The origin of the redeem operation must have a main account account and sub account.
2. The specified treasury token and the asset being transferred must exist and cannot be the same token, as redeeming the treasury token is not allowed.&#x20;
3. The token being redeemed must exist in the specified treasury.
4. The balance being redeemed cannot be zero.

### Calculations

1. After passing the validating checks, there are several calculations to be made.
2. The total value of all tokens held in the treasury is calculated, considering token prices from the price feed oracle or the token’s liquidity pool.
3. The lowest price of the token is calculated based on the treasuries balance. In other words, the lowest price of a token is the treasuries total value of that token divided by how many it has.
4. The total amount of tokens the user can receive based on the lowest price is calculated.
5. The price of the token is obtained from the oracle or liquidity pool.
6. The total amount of tokens to be redeemed is calculated.

### Finalize Redemption

After the user’s total amount of tokens to be redeemed is calculated, then a series of steps must succeed before this amount can be transferred to the user.

1. Transfer the calculated amount of treasury tokens from user to treasury.&#x20;
2. Increase balance of treasury token in treasury.
3. Decrease the supply of the transferred treasury token, as these are burned upon transfer to the treasury.&#x20;
4. Transfer redeemed tokens from treasury to user, and decrease the balance of that token within the treasury.
5. Emit an event about the redemption.&#x20;

{% hint style="info" %}
To accomplish transferring and redeeming, the treasury pallet interacts with several other pallets.

* For verifying, transferring and burning tokens the asset pallet is used.
* The pool pallet is used to manage liquidity pool balances.
* The oracle pallet is used to help determine token prices.
* The sub accounts pallet is used to access the user's main account.
{% endhint %}

## Treasury FAQ

<details>

<summary>What’s the most powerful thing about the Treasury?</summary>

The value that backs a token through its treasury operates as a kind of reserve asset or “book value” that exists even if the market sours on the speculative value of the token trading on the market. If all else fails, token holders can remove value from the treasury in proportion to their ownership. As a result, it is likely that the speculative value will generally remain at or above the value in the treasury.

</details>

<details>

<summary>How do digital assets get to the Treasury?</summary>

There are two ways that digital assets are sent to a token’s treasury. The first is by the token creator, who can transfer funds from the token’s bank or their personal wallet. The second is during an exchange with the token’s liquidity pool, which automatically sends a 0.5% exchange fee to the token’s treasury. Once digital assets are transferred into a token's treasury, they are only redeemable by token holders.

</details>

<details>

<summary>How does the Treasury help reveal a token’s intrinsic value?</summary>

All financial assets are typically valued based on an assessment of future income paid to the holder (bonds - interest, common and preferred stocks - dividends, real estate - rent, etc.), discounted to the present. Through the treasury, we now have a mechanism to establish the floor price of a token and substantiate its value with deflationary digital assets like Bitcoin.

A formula for token valuation: Token Valuation = NPV Treasury.

</details>

<details>

<summary>How is the floor price of a token calculated?</summary>

The treasury total amount divided by the token total maximum supply represents the floor price of the Token.

</details>

<details>

<summary>How are funds raised held as the underlying assets in the treasury?</summary>

They are held in the same assets that were transferred to the treasury. In other words, if all funds are collected in BTC, the intention is not to touch the funds by trading that could put token holders at risk.

</details>

<details>

<summary>Who is responsible for it?</summary>

Will be the responsibility of the token holders and core team to ensure the protocol is open and transparent. Governed by code.

</details>

<details>

<summary>How does one have visibility into the treasury?</summary>

Everyone can see the bank and treasury on the token page of any token on the Unit Network, including UNIT.

</details>

<details>

<summary>How is the treasury protected so that nothing will be withdrawn?</summary>

It is not technically possible to withdraw more than a token holder’s proportional share of the token supply, as no single user has access to the treasury. The funds can only be accessed by token holders in exchange for their tokens.

</details>

