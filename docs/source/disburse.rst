Disburse
===================================

The Disburse functionality is used to manage royalties, auctions and settlement of token trades. Settlement is currently in USD and USDC. The API requires an API key and has an endpoint of https://api.instamint.com/disburse/v1/. This API needs to be enabled by the admin of a client. Fractionalization and royalties featured are accessible via the Meta API and only if Disburse is enabled.


Auction Management
-------------------

+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
| Endpoint                                  | Purpose                                                                                             |
+===========================================+=====================================================================================================+
| /v1/disburse/auction/create               | Create an auction for a specific asset, specifiying ask, reserve and currency                       |
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
