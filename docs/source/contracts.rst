Smart Contracts
===================================

Instamint maintains a library of smart contracts that serve different purposes. This includes ERC721 and ERC1155 contracts and variations of them. Each smart contract is identified by a name and the name is identified during API calls. All smart contracts can be found at https://github.com/instamint/smartcontracts/

+-------------+------------------------------------------------+--------------------------------------------------------+
| Moniker     | Description                                    | Location                                               |
+=============+================================================+========================================================+
| INSTA1      | Clean OpenZeppelin 4.4.1 ERC721                | ../ethereum/contracts/Instamint721.sol                 |
+-------------+------------------------------------------------+--------------------------------------------------------+
| INSTA2      | Clean OpenZeppelin 4.4.1 ERC1155               | ../ethereum/contracts/Instamint1155.sol                |
+-------------+------------------------------------------------+--------------------------------------------------------+
| INSTA3      | On-chain metadata URL OZ 4.5.0 ERC1155         | tbd                                                    |
+-------------+------------------------------------------------+--------------------------------------------------------+

Smart contracts can be deployed or minted to. When deployed, a smart contract type is specified. For example, deploying a new ERC721 or ERC115 and assigning it a moniker. If minting to an existing smart contract, as is the case with an ERC721 or ERC1155, a moniker is used in lieu of a contract address. For Algorand ASA's, a token and smart contract are identical and therefore specifiying a contract type of ARC3 both deploys and mints the asset.


+----------+----------------------------------------------------------+-----------------------------------------------------------------------+
| Type     | Description                                              | Reference                                                             |
+===========+=========================================================+=======================================================================+
| ERC721   | Deploys the latest version of OpenZeppelin 4.4.1 ERC721  | https://docs.openzeppelin.com/contracts/2.x/api/token/erc721          |
+----------+----------------------------------------------------------+-----------------------------------------------------------------------+
| INSTA2   | Deploys the latest version of OpenZeppelin 4.4.1 ERC1155 | https://docs.openzeppelin.com/contracts/3.x/erc1155                   |
+----------+----------------------------------------------------------+-----------------------------------------------------------------------+
| ARC3     | Deploys and mints an Algorand Asset                      | https://github.com/algorandfoundation/ARCs/blob/main/ARCs/arc-0003.md |
+----------+----------------------------------------------------------+-----------------------------------------------------------------------+
