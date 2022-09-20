GraphQL
===================================
A preliminary GraphQL API for assets is available at https://q.instamint.network. Currently, the service searches through staging data only and will point to production data soon.

Asset Query & Schema
-------------------
type asset {
  xref: String
  instamint_asset_hashid: String
  algorand_assetid: Int
  explorerurl: String
  created_at: String
  mint_completed_status: Boolean
  mint_requestjson: String
  senderpk: String
  clawbackpk: String
  managerpk: String
  freezepk: String
  asset_name: String
  unit_name: String
  default_frozen: Boolean
  total: String
  parties: party
}

type party {
  owner: String
  client: String
  custodian: String
  issuer: String
}

type Query {
  allAssets: [asset]
  asset(hashid: String): asset
}

enum CacheControlScope {
  PUBLIC
  PRIVATE
}


