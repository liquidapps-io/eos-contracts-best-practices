# eos-contracts-best-practices
EOSIO contracts references, examples and best-practices

## Security best-practices
https://github.com/slowmist/eos-smart-contract-security-best-practices/blob/master/README_EN.md

https://github.com/NoneAge/EOS_dApp_Security_Incident_Analysis

## Performance best-practices:
https://medium.com/@bytemaster/developing-efficient-contracts-8a8e62011c6d

## TODO:

* Customized token contract example and best practices.
* Transfer/Action intercepting contract - https://github.com/cc32d9/dappscatalog/blob/master/contracts/dappscatalog.cpp#L71
* Permissions/Authorizations examples
* Random numbers - https://github.com/bada-studio/knights_contract/blob/master/knights/contract/player_control.hpp#L187 - ?
* Protecting from RAM theft
* Contract examples using the security best practices from above
* Submarine Operations (commit/reveal)
* Atomically erasing an entire table (by replacing pointers)
* Deleting table rows without types (primary index only) - https://gist.github.com/tbfleming/805cd85eb21970633c4a617c56d22159#file-main-cpp-L70 - same can be done for known secondary indexes using "db_##IDX##_lowerbound" and "db_##IDX##_remove"
* Using asserts efficiently
* Events - https://github.com/bancorprotocol/contracts_eos/blob/master/contracts/eos/BancorConverter/BancorConverter.cpp#L98
* Ricardian contracts
* Deferred transaction - https://github.com/eosdac/dacservice/blob/master/dacservice.cpp#L53
* Context-free actions
* Transfer memo as parameter - https://github.com/eosdac/dacservice/blob/master/dacservice.cpp#L25
* Always-false asserts


# Reviewed by:
