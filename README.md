# eos-contracts-best-practices
EOSIO contracts references, examples and best-practices

# Examples
## Deleting table rows without declaring tables
```cpp
  void clear_secondary_idx256(name TableName, uint8_t index_num, uint64_t scope){
    uint64_t primary = 0;

    auto key = eosio::key256();
    auto it2 = eosio::_multi_index_detail::secondary_index_db_functions<key256>::db_idx_lowerbound(
      _self.value, 
      scope, 
      (static_cast<uint64_t>(TableName.value) & 0xFFFFFFFFFFFFFFF0ULL)
                                    | (index_num & 0x000000000000000FULL), 
      key, 
      primary);
    while (it2 >= 0) {
        auto del = it2;
        uint64_t dummy;
        it2 = db_idx256_next(it2, &dummy);
        db_idx256_remove(del);
    }
  }
  void clear_primary(name TableName, uint64_t scope){
    auto it = db_lowerbound_i64(_self.value, scope, TableName.value, 0);
    while (it >= 0) {
        auto del = it;
        uint64_t dummy;
        it = db_next_i64(it, &dummy);
        db_remove_i64(del);
    }
  }

  ACTION clearpkgs(){
    require_auth(_self);
    clear_primary("package"_n, _self.value);
    clear_secondary_idx256("package"_n, 0, _self.value);
    clear_secondary_idx256("package"_n, 1, _self.value);
  }
```

# References
## Security best-practices
https://github.com/slowmist/eos-smart-contract-security-best-practices/blob/master/README_EN.md

https://github.com/NoneAge/EOS_dApp_Security_Incident_Analysis

## Performance best-practices:
https://medium.com/@bytemaster/developing-efficient-contracts-8a8e62011c6d

## More References:

* Transfer/Action intercepting contract - https://github.com/GetScatter/RIDL-Contracts/blob/master/scatterfunds/scatterfunds.cpp#L167 
* Protecting against intecepting unstaked/refunded tokens by mistake - https://github.com/GetScatter/RIDL-Contracts/commit/1b9480983579de5b5d55837364bb374ef87e5c83
* Random numbers - https://github.com/bada-studio/knights_contract/blob/master/knights/contract/player_control.hpp#L187 - ?
* Events - https://github.com/bancorprotocol/contracts_eos/blob/master/contracts/eos/BancorConverter/BancorConverter.cpp#L98
* Deferred transaction - https://github.com/eosdac/dacservice/blob/master/dacservice.cpp#L53
* Transfer memo as parameter - https://github.com/eosdac/dacservice/blob/master/dacservice.cpp#L25
* Migrate tables - https://github.com/nsjames/EOSIO-Migration-Tutorial/blob/master/migrate.cpp
* Customized token contract example and best practices. - *TODO*
* Permissions/Authorizations examples - *TODO*
* Protecting from RAM theft - *TODO*
* Contract examples using the security best practices from above - *TODO*
* Submarine Operations (commit/reveal) - *TODO*
* Atomically erasing an entire table (by replacing pointers) - *TODO*
* Using asserts efficiently - *TODO*
* Always-false asserts - *TODO*
* Context-free actions - *TODO*
* Ricardian contracts - *TODO*
* Construct bounds and query secondary index from eosjs - *TODO*  - https://github.com/greymass/eos-voter/blob/c003a04a6bd8937c416e61ad005824fe83c9f517/app/shared/actions/governance/proposals.js#L94

# Reviewed by:
