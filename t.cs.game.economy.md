---
id: xfmhb8hisz8o6g2e0rv38g7
title: Economy
desc: ''
updated: 1707368775893
created: 1707368775893
---

## Best Practices

## Overview

Steam provides world class support for in game purchases, whether that is items, in-game currency, or anything else that you can think up, you can use the Steam Microtransaction APIs to provide customers with more choices.

If you are working to bring your title with in-game purchases to Steam, we've got a few suggestions, best practices, and resources to help you get started. Whether you have a Free to Play game, or a game that is purchased upfront, there are common elements with any game that has in-game purchases that are useful to consider when working toward your launch on Steam.

## In-Game Purchase Requirements

For any in-game purchases, you'll need to use the microtransaction API so Steam customers can only make purchases from the Steam Wallet. You can learn more about how to complete this integration in the [Microtransactions Implementation Guide](https://partner.steamgames.com/doc/features/microtransactions/implementation).

You can use the Steam Wallet to purchase individual items or to purchase your in-game currency.

## Anticipating Fraud

You run a risk of fraud any time you offer something of value that can be purchased. For your in-game store, Steam is providing services as a payment processor – Steam runs fraud checks, but the context in which a user makes a purchase in your game is something that only your game servers can understand.

Your game is especially vulnerable if the in-game purchases are part of an economy where virtual goods and services can be traded or gifted. If fraud is allowed to run rampant and unchecked, it can devalue the items in the economy or create game imbalance that ruins the gameplay experience of legitimate users.

Fraud often involves a user purchasing high-value currency and items with a stolen payment method (such as a credit card). The fraudsters’ goal is to move those virtual goods to other accounts, either owned by the fraudster or a player who is paying for those goods outside of the system. Alternatively, fraudsters may attempt to sell the entire account, again while being paid outside of the system.

Your team will need to find a balance within your economy that blocks bad users, yet does not impact your legitimate users. Here are some general suggestions as starting points for basic protection against easy forms of fraud:

1.  Use in-game knowledge of a user’s history to limit actions that can contribute to fraud. For example, if you know the player is really new, then it’s generally a good idea to limit purchase of high-value items or currency. It’s unlikely that a brand-new legitimate user is interested in buying $200 worth of items or currency. To accomplish this, it’s useful to incorporate a number of points of data about the user.  
    -   Has the user leveled up in your game to some minimum level?  
        
    -   Has the user made past purchases? Does their behavior look legitimate?  
        
    -   What are typical average purchase amounts across your game for a month? Is this transaction suspiciously far outside that range?  
        
    -   How many transactions do your typical paying customers make in a month? Is this user making a suspiciously large number of transactions?  
        
    -   Does this user have a history of trading that looks legitimate?  
        
2.  Use Steam’s knowledge of a user’s history to inform your concern about a specific transaction or user. You can get information from Steam to help you determine what actions a user should be allowed to perform. Call [GetUserInfo()](https://partner.steamgames.com/doc/webapi/ISteamMicroTxn) in the ISteamMicroTxn API to get information about the user. Three main responses may be useful in determining how much you trust the user:  
    -   Country – returns the country where the user is connecting from to make their purchase. By itself it isn’t very informative, but can be useful in conjunction with Currency.  
        
    -   Currency – returns the currency code of the user’s Steam Wallet. Commonly, this is used to determine what pricing information should be displayed to the user, but by checking the currency against the country where the request is coming from, you can see whether the currency matches what is expected for a user from that country. This doesn’t necessarily indicate fraud--users can login and make purchases while traveling, but performing this check gives you more information when looking for patterns in fraudulent activity.  
        
    -   Status – returns either ‘Active’, ‘Trusted’, or ‘Locked’.  
        1.  An account is Active by default.  
            
        2.  Trusted accounts have a transaction over 90 days old without any chargebacks associated with the Steam account. It is important to note that a Trusted account may still be hijacked or ‘baked’ with a low value purchase to appear legitimate. This status should not be the sole determining factor to accept or reject a purchase.  
            
        3.  A Locked account cannot make purchases in Steam because of fraud, chargeback, a hijack, or a violation of the Steam Terms of Service. This status is not always permanent, especially in the case of hijacking or accidental chargebacks by banks.
3.  Catching fraudulent transactions before they can impact the economy is important.  
    -   Steam catches most fraudulent transactions within 48 hours of the initial purchase. Call the [GetReport()](https://partner.steamgames.com/doc/webapi/ISteamMicroTxn#GetReport) API at least once each day to reconcile changes to transactions according to their updated [status](https://partner.steamgames.com/doc/features/microtransactions/implementation#status_values).  
        
    -   You should prevent trading or gifting of the newly purchased items for at least 72 hours from the time of purchase. This will not impact the majority of your players since most players will use funds and items purchased for themselves while fraudsters must move their fraudulent goods to profit.  
        
    -   When purchases are refunded, an automatic ‘claw-back’ system removing the funds and items purchased on the fraudulent account deters further behavior. Combined with the detection time and trade restriction, the fraudster will not have profited from the fraudulent account.
4.  Don't display a product key for in-game purchases that could be harvested for another account. There are Steam APIs for granting packages or unlocking content without needing to display a key to customers that can potentially be duplicated.  
    
5.  Don't allow users to change the linked accounts that are described in the next section: Linking Accounts.

Using the Steam Inventory Service incorporates many of these suggestions.

## Linking Accounts

Do you have your own account system? If so, we strongly encourage you to use Steamworks API to automatically create or link the Steam customer's account with your system, rather than requiring the customer to manually create an account through your game or website. Creating a new account through another service can be a huge hurdle for some customers, and can significantly impact your potential audience.

Linking a user’s Steam account to your own system can be done by retrieving and verifying a user’s SteamID, which is a unique identifier for a Steam account.

Ideally, it shouldn't be possible for a customer to disassociate their Steam account from your account system and then re-link another Steam account.

For more information on account linking, please see the "Account Linking" section in the [User Authentication and Ownership](https://partner.steamgames.com/doc/features/auth) documentation.

## Considerations for in-game economies and best practices

Steamworks provides a variety of opportunities to integrate microtransactions and in-game economies. There are a few things to consider on the topic.

Watch Kyle Davis’s presentation from Steam Dev Days for more detailed information.

![](https://img.youtube.com/vi/RHC-uGDbu7s/0.jpg)

YouTube™ Video: In-Game Economies in Team Fortress 2 and Dota 2 (Steam Dev Days 2014) 

Views: 102,767

A look at the multi-year history and development of the in-game economies and microtransaction systems in Team Fortress and Dota, including some of the surprises we encountered and some of the...

1.  #### Use your in-game economy to improve your product and make customers happier, not as a means to extract revenue from unhappy customers.
    
    Artificial barriers to progress and virtual currencies that obfuscate value tend to make customers regret their purchases over the long term. If you’re viewing in-game transactions as an opportunity to halt your customer’s enjoyment to ask for money, they’ll be inclined to abandon the product over time. Paying money to eliminate frustration is not a sustainable business model, and the marketplace is competitive enough that customers have lots of better alternatives for their time and money.  
    
2.  #### Build systems wherein customer purchases make your game better for other customers.
    
    Many free to play products, especially multiplayer games, rely on systems where the more money one player spends, the worse the game gets for the other players. Avoid building systems where players have the ability to negatively impact other players’ experiences, and focus instead on products and items that create positive externalities within your game. We cite specific examples in the Steam Dev Days presentation, but a good starting point is a product designed around a simple concept: "I celebrate when the player next to me makes a purchase." This is feasible for games of all genres and styles, and we encourage you to run experiments around such products in your own games.  
    
3.  #### Allow your users to create value for one another.
    
    The Steam Workshop consists of tools that allow your customers to create content and value for one another. Customers can create models, maps, mods, or other valuable components for your game. Depending on your product and your goals, you can choose between an open or curated Workshop. In either case, the creativity and passion of your customers can greatly expand the value of your product and provide you with a great source of additional content. Check out the [Steam Workshop](https://partner.steamgames.com/doc/features/workshop) documentation and [Steamworks Developer Discussions](http://steamcommunity.com/groups/steamworks/discussions/9/) for more information about the Steam Workshop.

Overall, being a slave to metrics like revenue-per-day or per-user can drive short-term decisions that harm your players and the longevity of your product. Watch the full Steam Dev Days talk above for specific examples and additional insights.

## Getting The Most From Updates

Updates are an important part of your product's lifecycle and a critical form of communication with customers. You'll need to make updates to fix bugs and address issues, but major updates are also a huge opportunity to add new content, new modes of play, or new features to help keep customers engaged and attract new audiences.

Check out [Best Practices, Marketing](https://partner.steamgames.com/doc/marketing/bestpractices) documentation for suggestions and best practices around getting the most from your product updates.


## References

- https://partner.steamgames.com/doc/features/microtransactions#4
- 