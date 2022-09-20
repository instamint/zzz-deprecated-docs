Disburse
===================================

The Disburse functionality is used to manage royalties, auctions and settlement of token trades. Settlement is currently in USD and USDC. The API requires an API key and has an endpoint of https://api.instamint.com/disburse/v1/. 


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
| /disburse/v1/auction/bid                  | Bid on asset                                                                                        |
+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
| /disburse/v1/auction/acceptbid            | Seller accepts the best bid                                                                         |
+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
| /disburse/v1/auction/trade/info           | Get info for a trade executed as a result of an auction                                             |
+-------------------------------------------+-----------------------------------------------------------------------------------------------------+
