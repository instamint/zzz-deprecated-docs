Meta
===================================

The **Meta** API is used to mint NFTs
.. code-block:: json
   :caption: A cool example
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


+-----------+----------------------------------------------------------------------------------------------+
| API       | Description                                                                                  |
+===========+==============================================================================================+
| Meta      | Mint, premint, transfer multi-asset cross-chain NFTs                                         |
|           | and manage custodial and non-custodial accounts                                              |
+-----------+----------------------------------------------------------------------------------------------+
| Disburse  | Royalties, fractionalization, payment settlement and auction engine                          |
+-----------+----------------------------------------------------------------------------------------------+
| Yield     | NFT DeFi                                                                                     |
+-----------+----------------------------------------------------------------------------------------------+

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
