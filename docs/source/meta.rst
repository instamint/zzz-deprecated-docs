Meta Overview
===================================

The **Meta** API is used to mint NFTs or *assets*. The API requires an API key and has an endpoint of https://api.meta.instamint.com/meta/v1/. 

Instamint clients mint and manage NFTs. Requests to mint via Meta by clients are asynchronous and operate like jobs. When a request to mint an asset is made, a new unique asset identifier is return and the minting status of that asset is tracked. The client is able to pass in a arbitrary identifier that is then returned back on subsequent status checks, providing the client the ability to correlate the asset with their internal systems.

An asset is associated with four parties - Partner, Issuer or Creator, Owner and Custodian. Each role is filled by one or more Parties, where each Party has a unique identifier assigned by Instamint. Clients register parties by submitting a string name, and optionally, a wallet address. The Partner role is usually the Instamint client making the API call. The issuer or creator is the party that originates the asset, say a bank or artist, the owner is the current owner of the asset, usually the issuer or creator initially and the custodian is Instamint by default.

Thus, Meta has API endpoints that handle the creation of parties and their association with NFTs.

+----------------------------+-----------------------------------------------------------------------------+
| Endpoint                   | Purpose                                                                     |
+============================+=============================================================================+
| /meta/v1/party/create      | Creates new parties and returns an identifier                               |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/party/lookup      | Lookup a party by name and retrieve                                         |
+----------------------------+-----------------------------------------------------------------------------+

+----------------------------+-----------------------------------------------------------------------------+
| Endpoint                   | Purpose                                                                     |
+===========+==============================================================================================+
| /meta/v1/asset/mint        | Request an asset be minted                                                  |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/asset/mintBatch   | Request a batch of assets be minted                                         |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/asset/status      | Get status of an asset                                                      |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/asset/my          | Get all assets of a partner                                                 |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/asset/my          | Get all assets of a partner                                                 |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/asset/search      | Coming soon - the ability to search for assets using GraphQL                |
+----------------------------+-----------------------------------------------------------------------------+

Minting
========

+-----------+----------------------------------------------------------------------------------------------+
| Smart Contract             | Chain | Contract Address                                                                     |
+===========+==============================================================================================+
| ERC721        | Ethereum |               0xa993749323E2A8B18f7D4Ef541D6A1a89Cd92888                                    |
+-----------+----------------------------------------------------------------------------------------------+
| /meta/v1/asset/mintBatch   | Request a batch of assets be minted                                         |
+-----------+----------------------------------------------------------------------------------------------+
| /meta/v1/asset/status      | Get status of an asset                                                      |


The endpoint to mint an asset is /meta/v1/asset/mint. A JSON POST request includes the following parameters that can be supplied.

+------------------+---------------------------------------------------------------------------------------+
| Parameter        | Purpose                                                                               |
+===========+==============================================================================================+
| partnerID        | The ID of the client                                                                  |
+------------------+---------------------------------------------------------------------------------------+
| issuerID         | The ID of the creator or issuer of the asset, typically the client's customer         |
+------------------+---------------------------------------------------------------------------------------+
| environment      | Testnet or mainnet                                                                    |
+------------------+---------------------------------------------------------------------------------------+
| chain            | Ethereum, Polygon or others                                                           |
+------------------+---------------------------------------------------------------------------------------+
| waitTolerance    | How much time client can wait to mint for batching and gas savings                    |
+------------------+---------------------------------------------------------------------------------------+
| assetType        | The type of asset: media, municipal bond, POA, badge, etc.                            |
+------------------+---------------------------------------------------------------------------------------+
| contractType     | Where applicable, the target smart contract type, i.e. 721, 1155, etc.                |
+------------------+---------------------------------------------------------------------------------------+
| mintStrategy     | Lazy mint or on-chain                                                                 |
+------------------+---------------------------------------------------------------------------------------+
| assets           | A dictionary of asset URLs, as defined by the client                                  |
+------------------+---------------------------------------------------------------------------------------+
| metadata         | A dictionary of metadata, as defined by the client                                    |
+------------------+---------------------------------------------------------------------------------------+


Instamint is multichain, meaning that tokens can be minted across a number of blockchains. Additional chains are planned to be supported and come online over the coming quarters.

+-----------+-----------------------------------------------------------------------------------------------------------+
| Chain     | Support Level                                                                                             |
+===========+===========================================================================================================+
| Ethereum  | Supported - ERC721, ERC1155                                                                               |
+-----------+-----------------------------------------------------------------------------------------------------------+
| Polygon   | Supported - ERC721, ERC1155                                                                               |
+-----------+-----------------------------------------------------------------------------------------------------------+
| Algorand  | Q1 2022                                                                                                   |
+-----------+-----------------------------------------------------------------------------------------------------------+
| Avalance  | Q2 2022                                                                                                   |
+-----------+-----------------------------------------------------------------------------------------------------------+
| Hedera    | Q2 2022                                                                                                   |
+-----------+-----------------------------------------------------------------------------------------------------------+

It pulls data from the `Open Food Facts database <https://world.openfoodfacts.org/>`_
and offers a *simple* and *intuitive* API.

Check out the :doc:`usage` section for further information, including
how to :ref:`installation` the project.

.. note::

   Due to the expanding and complex nature of blockchain, the Instamint APIs are constantly being improved.
