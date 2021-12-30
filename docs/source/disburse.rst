Disburse
===================================

The Disburse API is used to manage royalties, auctions and settlement of NFT trades. The API requires an API key and has an endpoint of https://api.disburse.instamint.com/disburse/v1/. The API is currently in alpha and will be in beta Q2 2022.

Royalty Management
-------------------
+-------------------------------------------+--------------------------------------------------------------+
| Endpoint                                  | Purpose                                                      |
+===========================================+==============================================================+
| /disburse/v1/royalty/ASSET_ID/set         | Set royalty structure and events                             |
+-------------------------------------------+--------------------------------------------------------------+
| /disburse/v1/royalty/ASSET_ID/history     | Retrieve royalty payout history                              |
+-------------------------------------------+--------------------------------------------------------------+


Auction Management
-------------------

+-------------------------------------------+--------------------------------------------------------------+
| Endpoint                                  | Purpose                                                      |
+===========================================+==============================================================+
| /disburse/v1/auction/ID/ASSET_ID/bid      | Set bid price for an asset                                   |
+-------------------------------------------+--------------------------------------------------------------+
| /disburse/v1/auction/ID/ASSET_ID/ask      | Set ask price for an asset, -1 removes from auction          |
+-------------------------------------------+--------------------------------------------------------------+
| /disburse/v1/auction/ID/ASSET_ID/book     | Get top 10 bids and single ask                               |
+-------------------------------------------+--------------------------------------------------------------+
