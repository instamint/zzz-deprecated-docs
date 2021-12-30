Meta
===================================

The **Meta** API is used to mint NFTs or *assets*. The API requires an API key and has an endpoint of https://api.meta.instamint.com/meta/v1/. 

Instamint clients mint and manage NFTs. Requests to mint via Meta by clients are asynchronous and operate like jobs. When a request to mint an asset is made, a new unique asset identifier is return and the minting status of that asset is tracked. The client is able to pass in a arbitrary identifier that is then returned back on subsequent status checks, providing the client the ability to correlate the asset with their internal systems.

An asset is associated with four parties - Partner, Issuer or Creator, Owner and Custodian. Each role is filled by one or more Parties, where each Party has a unique identifier assigned by Instamint. Clients register parties by submitting a string name, and optionally, a wallet address. The Partner role is usually the Instamint client making the API call. The issuer or creator is the party that originates the asset, say a bank or artist, the owner is the current owner of the asset, usually the issuer or creator initially and the custodian is Instamint by default.

Thus, Meta has API endpoints that handle the creation of parties and their association with NFTs.


+-----------+----------------------------------------------------------------------------------------------+
| Endpoint       | Purpose                                                                                 |
+===========+==============================================================================================+
| /meta/v1/party/create      | Creates new parties and returns an identifier                               |
+-----------+----------------------------------------------------------------------------------------------+
| /meta/v1/party/lookup  | Lookup a party by name and retrieve                          |
+-----------+----------------------------------------------------------------------------------------------+
| Yield     | NFT DeFi                                                                                     |
+-----------+----------------------------------------------------------------------------------------------+

.. code-block:: json
{
    "instamintCreatorID":"0f9B3cCD7a8E491EA84D0655E37207a3",
    "partnerID":"F84D6fa6FADA44638AB8a1F907093263",
    "partnerRole": "producer",
    "environ":"testnet",
    "targetChain": "eth",
    "waitTolerance": "86400",
    "contractType" : "erc1155",
    "assetType": "multimedia",
    "description":"Sendjoy Test mint",
    "b2bCrossReferenceID":"3456789",
    "mintStrategy": ["real"],
    "assets":{
      "image":"https://nft-test-bucket-sendjoy.s3.ap-southeast-1.amazonaws.com/test2/test1.mp4"},
    "metadata":{
        "name":"The Man Lim Speaks",
        "description":"Lim Test NFT!",
        "creator":"Lim Liang Chun 林良淳",
        "fromTo":"Commissioned by Kong",
        "created":"05/05/2021",
        "title":"Shout out to Vitamint",
        "creator_url":"www.sendjoynow.com/liang-chun",
        "id":"14442"
   }
}



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
