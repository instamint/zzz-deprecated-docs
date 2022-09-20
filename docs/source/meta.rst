Meta
===================================

The **Meta** API is used to mint NFTs or *assets*. The API requires an API key and has an endpoint of https://api.meta.instamint.com/meta/v1/. 

Instamint clients mint and manage NFTs. Requests to mint via Meta by clients are asynchronous and operate like jobs. When a request to mint an asset is made, a new unique asset identifier is returned and the minting status of that asset is tracked. The client is able to pass in a arbitrary identifier that is then returned back on subsequent status checks, providing the client the ability to correlate the asset with their internal systems.

An asset is associated with four parties - Partner, Issuer or Creator, Owner and Custodian. Each role is filled by one or more Parties, where each Party has a unique identifier assigned by Instamint. Clients register parties by submitting a string name, and optionally, a wallet address. The Partner role is usually the Instamint client making the API call. The issuer or creator is the party that originates the asset, say a bank or artist, the owner is the current owner of the asset, usually the issuer or creator initially and the custodian is Instamint by default.

Thus, Meta has API endpoints that handle the creation of parties and their association with NFTs.

Party Management
-------------------

+----------------------------+-----------------------------------------------------------------------------+
| Endpoint                   | Purpose                                                                     |
+============================+=============================================================================+
| /v1/meta/party/create      | Creates new parties and returns an identifier                               |
+----------------------------+-----------------------------------------------------------------------------+
| /v1/meta/party/lookup      | Lookup a party by name and retrieve                                         |
+----------------------------+-----------------------------------------------------------------------------+

Asset Management
---------------------

+----------------------------+-----------------------------------------------------------------------------+
| Endpoint                   | Purpose                                                                     |
+============================+=============================================================================+
| /v1/meta/asset/mint        | Request an asset be minted, see JSON payload below                          |
+----------------------------+-----------------------------------------------------------------------------+
| /v1/meta/asset/status      | Get status of an asset to determine if it has been minted or not            |
+----------------------------+-----------------------------------------------------------------------------+
| /v1/meta/asset/my          | Get all assets I own                                                        |
+----------------------------+-----------------------------------------------------------------------------+


Minting
---------------

The endpoint to mint an asset is /meta/v1/asset/mint. A JSON POST request includes the following parameters that can be supplied.

+--------------------------+---------------------------------------------------------------------------------------------+
| Parameter                | Purpose                                                                                     |
+==========================+=============================================================================================+
| chain                    | Chain to mint to, currently: ethereum-mainnet, ethereum-goerli, algorand-testnet            |
+--------------------------+---------------------------------------------------------------------------------------------+
| contractType             | Causes a contract to be deployed and minted to, currently: erc721, erc1155 and arc3         |
+--------------------------+---------------------------------------------------------------------------------------------+
| assetType                | The type of asset, either pre-defined or designed by Designer                               |
+--------------------------+---------------------------------------------------------------------------------------------+
| contract                 | Moniker of an existing smart contract, i.e. INSTA1, INSTA2                                  |
+--------------------------+---------------------------------------------------------------------------------------------+
| mintStrategy             | Lazy mint or on-chain                                                                       |
+--------------------------+---------------------------------------------------------------------------------------------+
| asset                    | A hierarchy of parameters, schemas are pre-built or designed in Designer                    |
+--------------------------+---------------------------------------------------------------------------------------------+
| store                    | Where to store metadata, currently: ipfs (arweave coming soon)                              |
+--------------------------+---------------------------------------------------------------------------------------------+
| assetDescription         | Description of asset, not publicly displayed                                                |
+--------------------------+---------------------------------------------------------------------------------------------+
| note                     | A note added to the asset's notebook                                                        |
+--------------------------+---------------------------------------------------------------------------------------------+
| fractionalization        | Fractionalization of assets (in 1, 10, 100, 1000 only)                                      |
+--------------------------+---------------------------------------------------------------------------------------------+
| royaltiesBasisPoint      | Basis of royalties to go to issuer                                                          |
+--------------------------+---------------------------------------------------------------------------------------------+
| contractSpecific         | Parameters specific to selected contract or contractType                                    |
+--------------------------+---------------------------------------------------------------------------------------------+
| chainSpecific            | Parameters specific to selected chain                                                       |
+--------------------------+---------------------------------------------------------------------------------------------+

Instamint is multichain, meaning that tokens can be minted across a number of blockchains. Additional chains are planned to be supported and come online over the coming quarters.

+-----------+-----------------------------------------------------------------------------------------------------------+
| Chain     | Support Level                                                                                             |
+===========+===========================================================================================================+
| Ethereum  | Supported - ERC721, ERC1155                                                                               |
+-----------+-----------------------------------------------------------------------------------------------------------+
| Polygon   | Supported - ERC721, ERC1155                                                                               |
+-----------+-----------------------------------------------------------------------------------------------------------+
| Algorand  | Supported - ARC3                                                                                          |
+-----------+-----------------------------------------------------------------------------------------------------------+


When an asset is minted, any file assets, like an image or video, is uploaded to IPFS. The IPFS URLs of the digital assets are then aggregated into as single JSON metadata file and also uploaded to IPFS and is regarded as the token metadata. The metadata is cached by Instamint and accessible via the token URI.

Smart Contracts
-----------------

Instamint manages a growing library of token smart contracts. For example, an ERC1155 exists on Ethereum mainnet at address 0xa993749323E2A8B18f7D4Ef541D6A1a89Cd92888 and Instamint uses this to mint NFTs. Depending on client needs, additional ERC1155 contracts may be required and created. To manage this, each contract is assigned a short name. In the provided contract address example, the short name for this contract is INSTA2. INSTA1 refers to an ERC721 and INSTA3 does not currently exist.

In the future, clients will be able to not only mint NFTs but *mint smart contracts* and create self-custody these smart contracts. For example, an artist may wish to have their own ERC721 smart contract and Instamint will provide the ability to do that with an API. As such, each instance of a smart contract will be given a short name to track. This is simplifies the need to retrieve metadata via a single URI scheme. The URI scheme for Instamint across any smart contract on any chain is:

Scheme: /meta/v1/uri/contract/*CONTRACT_SHORT_NAME*/token/*TOKEN_ID*

In the above scheme, *CONTRACT_SHORT_NAME* would be replaced by *INSTA1*, *INSTA2* or any other smart contract minted through Instamint.

.. note::

   Due to the expanding and complex nature of blockchain, the Instamint APIs are constantly being improved.
