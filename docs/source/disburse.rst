Disburse
===================================

The Disburse functionality is used to manage royalties, auctions and settlement of token trades. Settlement is currently in USD and USDC. The API requires an API key and has an endpoint of https://api.instamint.com/disburse/v1/. This API needs to be enabled by the admin of a client. Fractionalization and royalties featured are accessible via the Meta API and only if Disburse is enabled.

Auction Management
-------------------

An asset can be auctioned using one of several auction strategies. Currently, the only auction strategy available is *open ascending* where each bidder can only bid higher than the current best bid. If the bidder bids at or above the ask, a trade is effected. Conversely, a seller can accept the current best bid and effect a trade. Trades are settled with USD or USDC debited and credited accordingly.

Auctions are objects in Instamint, and an Asset can be associated with zero or one auction at any given moment. Once an auction is closed, either via expiration or a manual stop, the auction continues to exist and can be examined, despite not being live. An asset can again be part of a new auction. A new auction is by POSTing parameters including the Instamint asset hash ID, duration (in days), ask and reserve price.

Auction Management
-------------------

+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
| Endpoint                                  | Purpose                                                                                             |
+===========================================+=====================================================================================================+
| /v1/disburse/auction/create               | Create an auction for a specific asset, duration (days) specifiying ask, reserve and currency       |
+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
| /v1/disburse/auction/info                 | Get information for a current or historic auction                                                   |
+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
| /v1/disburse/auction/current              | Get the auction the asset is currently involved in, if one                                          |
+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
| /v1/disburse/auction/bid                  | Bid on asset                                                                                        |
+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
| /v1/disburse/auction/acceptbid            | Seller accepts the best bid                                                                         |
+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
| /v1/disburse/auction/trade/info           | Get info for a trade executed as a result of an auction                                             |
+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
