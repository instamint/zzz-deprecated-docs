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
| /meta/v1/party/create      | Creates new parties and returns an identifier                               |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/party/lookup      | Lookup a party by name and retrieve                                         |
+----------------------------+-----------------------------------------------------------------------------+

Asset Management
---------------------

+----------------------------+-----------------------------------------------------------------------------+
| Endpoint                   | Purpose                                                                     |
+============================+=============================================================================+
| /meta/v1/asset/mint        | Request an asset be minted                                                  |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/asset/mintBatch   | Request a batch of assets be minted                                         |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/asset/status      | Get status of an asset                                                      |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/asset/my          | Get all assets of my (partner) assets                                       |
+----------------------------+-----------------------------------------------------------------------------+
| /meta/v1/asset/search      | Coming soon - the ability to search for assets using GraphQL                |
+----------------------------+-----------------------------------------------------------------------------+

Minting
---------------

The endpoint to mint an asset is /meta/v1/asset/mint. A JSON POST request includes the following parameters that can be supplied.

+------------------+---------------------------------------------------------------------------------------+
| Parameter        | Purpose                                                                               |
+==================+=======================================================================================+
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

Smart Contracts
-----------------

Instamint manages a growing library of token smart contracts. For example, an ERC1155 exists on Ethereum mainnet at address 0xa993749323E2A8B18f7D4Ef541D6A1a89Cd92888. Depending on client needs, additional ERC1155 contracts may be created. To manage this, each contract is assigned a short name. In the provided example, the short name for this contract is INSTA2. INSTA1 refers to an ERC721 and INSTA3 does not exist.

In the future, clients will be able to not only mint NFTs but create self-custodied smart contracts. For example, an artist may wish to have their own ERC721 smart contract and Instamint will provide the ability to do that with an API. Each instance of a smart contract will be given a short name to track. This is also for retrieving metadata via a single URI scheme. The URI scheme for Instamint across any smart contract on any chain is:

...../meta/v1/uri/contract/CONTRACT_SHORT_NAME/token/TOKEN_ID

In the above scheme, CONTRACT_SHORT_NAME would be replaced by INSTA1, INSTA2 or any other registered smart contract


+-----------+----------------------------------------------------------------------------------------------+
| Smart Contract             | Chain | Contract Address                                                                     |
+===========+==============================================================================================+
| ERC721        | Ethereum |                                                   |
+-----------+----------------------------------------------------------------------------------------------+
| /meta/v1/asset/mintBatch   | Request a batch of assets be minted                                         |
+-----------+----------------------------------------------------------------------------------------------+
| /meta/v1/asset/status      | Get status of an asset                                                      |



.. note::

   Due to the expanding and complex nature of blockchain, the Instamint APIs are constantly being improved.
