# eos-contracts-best-practices
EOSIO contracts references, examples and best-practices

## Security best-practices
https://github.com/slowmist/eos-smart-contract-security-best-practices/blob/master/README_EN.md

https://github.com/NoneAge/EOS_dApp_Security_Incident_Analysis

## Performance best-practices:
https://medium.com/@bytemaster/developing-efficient-contracts-8a8e62011c6d

## References:

* Transfer/Action intercepting contract - https://github.com/GetScatter/RIDL-Contracts/blob/master/scatterfunds/scatterfunds.cpp#L167 
* Protecting against intecepting unstaked/refunded tokens by mistake - https://github.com/GetScatter/RIDL-Contracts/commit/1b9480983579de5b5d55837364bb374ef87e5c83
* Random numbers - https://github.com/bada-studio/knights_contract/blob/master/knights/contract/player_control.hpp#L187 - ?
* Deleting table rows without types (primary index only) - https://gist.github.com/tbfleming/805cd85eb21970633c4a617c56d22159#file-main-cpp-L70 - same can be done for known secondary indexes using ```db_##IDX##_lowerbound``` and ```db_##IDX##_remove```
* Events - https://github.com/bancorprotocol/contracts_eos/blob/master/contracts/eos/BancorConverter/BancorConverter.cpp#L98
* Deferred transaction - https://github.com/eosdac/dacservice/blob/master/dacservice.cpp#L53
* Transfer memo as parameter - https://github.com/eosdac/dacservice/blob/master/dacservice.cpp#L25
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


# Reviewed by:
