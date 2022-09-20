Instamint
===================================

**Instamint** is a platform for enterprise (think companies and organizations) minting, managing, auctioning, staking, fractionalizing and trading digital business assets with each other in a B2B fashion. The platform is unbiased, works with multiple chains and has a growing library of types of assets it can handle. It is a B2B platform, and thus a platform to/for other platforms. It combines off-chain capabilities with on-chain tokens.


Overview
---------

Currently, Instamint consists of three sets of APIs, each serving a specific purpose for clients. They are:

+-----------+----------------------------------------------------------------------------------------------+
| API       | Description                                                                                  |
+===========+==============================================================================================+
| Meta      | Manage multi-asset cross-chain NFTs and accounts                                             |
+-----------+----------------------------------------------------------------------------------------------+
| Disburse  | Royalties, fractionalization, payment settlement and auction engine                          |
+-----------+----------------------------------------------------------------------------------------------+
| Yield     | Staking NFTs in best-of-breed DeFi protocols                                                 |
+-----------+----------------------------------------------------------------------------------------------+

**Console** is the dashboard applications where clients and delegated users can track their inventory of assets, manage API keys and view analytics. Console includes an emerging feature called *Designer*. Designer allows the visual construction of asset metadata using taxonomies like ACTUS and others, allowing business analysts to create new asset types with no technical background prerequisite.

The Instamint *asset library* is a library of the types and templates of assets that can be turnkey minted. For example, a municipal bond may be in the asset library and any entity in the US that wishes to mint a municipal bond can simply use the template if it meets their requirements.

Key Concepts
------------

An NFT is a token that represents a business *asset*. Each NFT has a unique *token identifier* and typically points to rich data that describes and defines that asset. The asset may be an image, a video, a municipal bond, shipping container or an award badge. Instamint provides the tools to manage these type of assets via an API. Each asset also has a unique identifier and is correlated with the token identifier. An Instamint *client* is a B2B user of the Instamint platform that requires such services.


User Model
----------

A *client* is an enterprise user of Instamint that typically has multiple delegated users. For example, ABC Corp. would be a client and John Smith in the accounting department of ABC is tasked with tokenizing and factoring invoices while Rita Khan in legal uses Instamint to mint DAOs to hold assets, much like LLCs are done today. John and Rita would be *delegated users* of Instamint, delegated usage rights by the client ABC Corp.

Instamint *parties* are entities, human or corporate, that have relationships with business assets. The four type of parties typically associated with an asset are *clients*, *issuers* or creators, *owners* and *custodians*. Parties are created and registered in Instamint as simply a named entity with an Ethereum and Algorand address generated for them. When a new client account is created, an associated party entity is created. The same is for delegated users, each delegated user is also a party that can hold and trade assets.

Each party has a unique party ID and each party can be associated with one or more blockchain accounts or wallets and each party is associated with a B2B reference ID meaningful only to the partner or client. An NFT has at least four parties associated with it - the client that created it, the issuer, current owner and custodian.

API Charges via Ops
-------------------

Usage of the API is metered via consumption of *ops*, a point system that is weighted against the amount of effort it takes to execute the call. Clients purchase ops and consume them when consuming APIs. Clients can allocate ops to their delegated users and reload their accounts with more ops.

Multichain
-----------

Instamint is multichain, meaning that tokens can be minted across a number of blockchains, currently Ethereum and Algorand (testing). Additional chains are planned to be supported and come online over the coming quarters.

+-----------+-----------------------------------------------------------------------------------------------------------+
| Chain     | Support Level                                                                                             |
+===========+===========================================================================================================+
| Ethereum  | ERC721, ERC1155                                                                               |
+-----------+-----------------------------------------------------------------------------------------------------------+
| Algorand  | ARC3                                                                                                      |
+-----------+-----------------------------------------------------------------------------------------------------------+
| Polygon   | Q2 2023                                                                                                   |
+-----------+-----------------------------------------------------------------------------------------------------------+

.. note::

   Due to the expanding and complex nature of blockchain, the Instamint APIs are constantly being improved.

Contents
--------

.. toctree::
   meta
   disburse
   yield
   console
   designer
   contracts
   assets
   gql
   websocket

