Instamint
===================================

**Instamint** is a platform for minting, managing, auctioning, staking, fractionalizing and trading digital business assets. The platform is unbiased, works with multiple chains and has a growing library of types of assets it can handle. It is a B2B platform, and thus a platform to/for other platforms.

Key Concepts
------------

An NFT is a token that represents a business asset. Each NFT has a unique token identifier and typically points to rich data that describes and defines that asset. The asset may be an image, a video, a municipal bond, shipping container or an award badge. Instamint provides the tools to manage these type of assets via an API. Each asset also has a unique identifier and is correlated with the token identifier. An Instamint client is a B2B user of the Instamint platform.

Instamint parties are entities, human or corporate, that have relationships with business assets. The four type of parties typically associated with an asset are partners, issuers or creators, owners and custodians. Parties are created and registered in Instamint. Each party can be associated with one or more blockchain accounts or wallets.

The Instamint asset library is a library of the types and templates of assets that can be turnkey minted. For example, a municipal bond may be in the asset library and any entity in the US that wishes to mint a municipal bond can simply use the template or design their own.


Overview
---------

Currently, Instamint is three sets of APIs, each serving a specific purpose for clients. They are:

+-----------+----------------------------------------------------------------------------------------------+
| API       | Description                                                                                  |
+===========+==============================================================================================+
| Meta      | Manage multi-asset cross-chain NFTs and accounts                                             |
+-----------+----------------------------------------------------------------------------------------------+
| Disburse  | Royalties, fractionalization, payment settlement and auction engine                          |
+-----------+----------------------------------------------------------------------------------------------+
| Yield     | Staking NFTs in best-of-breed DeFi protocols                                                 |
+-----------+----------------------------------------------------------------------------------------------+

In addition to the APIs, Instamint consists of two applications. **Console** is the dashboard applications where partners can track their inventory of assets, manage API keys and view analytics. Market is a B2C app that allows retails users to mint their Instagram photos and is used as a showcase and requirements driver for the suite of APIs.

Multichain
-----------

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


.. note::

   Due to the expanding and complex nature of blockchain, the Instamint APIs are constantly being improved.

Contents
--------

.. toctree::
   meta
   disburse
   yield

