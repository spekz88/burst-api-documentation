# Account Operations

## Get Account


```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getAccount" \
  -d "account=BURST-6E5U-CJQY-NUR3-ASNBA"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getAccount",
  "account": "BURST-5L3W-BVF5-EE7N-3QX2C"
}

r = requests.get(url, params)

print r.json()

```

> The above request returns JSON structured like this:

```json
{
    "unconfirmedBalanceNQT": "100000000",
    "guaranteedBalanceNQT": "100000000",
    "effectiveBalanceNXT": 100000000,
    "accountRS": "BURST-6E5U-CJQY-NUR3-ASNBA",
    "name": "Genxt Web Development",
    "forgedBalanceNQT": "0",
    "balanceNQT": "100000000",
    "publicKey": "eed0e9faa1e9ff9e91c341c23f1033ea32c48e85440113ecc6e26e178dc10207",
    "requestProcessingTime": 0,
    "account": "9522465949435965562"
}
```

Get account information given an account ID.

### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getAccount`
account | string | Required | `account` is the burst account ID

### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
unconfirmedBalanceNQT | string | is `balanceNQT` less unconfirmed outgoing transactions, the balance displayed in the client
guaranteedBalanceNQT | string | is the balance (in NQT) of the account with at least 1440 confirmations
effectiveBalanceNXT | numeric | is the balance (in BURST) of the account available for forging: the unleased `guaranteedBalance` of this account plus the leased `guaranteedBalance` of all lessors to this account
accountRS | string | is the Reed-Solomon address of the account
name | string | is the name associated with the account, if applicable
forgedBalanceNQT | string | is the balance (in NQT) that the account has forged
balanceNQT | string | is the minimally confirmed basic balance (in NQT) of the account
publicKey | string | is the public key of the account
requestProcessingTime | numeric | is the API request processing time (in millisec)
account | string | is the account number




## List AT


```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getAccountATs" \
  -d "account=BURST-5F5X-6F69-HTZP-4TEH6"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getAccountATs",
  "account": "BURST-5F5X-6F69-HTZP-4TEH6"
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getAccountATs",
  "account": "BURST-5F5X-6F69-HTZP-4TEH6"
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```



> The above request returns JSON structured like this:

```json
{
    "ats": [
        {
            "atVersion": 1,
            "creator": "2467296547687216253",
            "creatorRS": "BURST-5F5X-6F69-HTZP-4TEH6",
            "stopped": false,
            "machineCode": "35000300000000250100000035000402000000210...",
            "description": "I will be porting ChainCountDown to Burst...",
            "machineData": "00000000364d0300b013000000000000800b9ffbs...",
            "frozen": true,
            "finished": false,
            "dead": false,
            "balanceNQT": "50000000",
            "nextBlock": 221414,
            "minActivation": "700000000",
            "running": true,
            "at": "18378841777071640386",
            "name": "ChainCountDown",
            "atRS": "BURST-FMU4-94AR-7WFJ-H5Q5Y",
            "prevBalanceNQT": "50000000",
            "creationBlock": 216368
        },
        {
            "atVersion": 1,
            "creator": "2467296547687216253",
            "creatorRS": "BURST-5F5X-6F69-HTZP-4TEH6",
            "stopped": false,
            "machineCode": "35000300000000250100000035000402000000210...",
            "description": "I will be porting ChainCountDown to Burst...",
            "machineData": "00000000364d0300b013000000000000800b9ffb2...",
            "frozen": true,
            "finished": false,
            "dead": false,
            "balanceNQT": "50000000",
            "nextBlock": 221414,
            "minActivation": "700000000",
            "running": true,
            "at": "18378841777071640386",
            "name": "ChainCountDown",
            "atRS": "BURST-FMU4-94AR-7WFJ-H5Q5Y",
            "prevBalanceNQT": "50000000",
            "creationBlock": 216368
        }
    ],
    "requestProcessingTime": 0
}
```

Get list of all AT smart contracts created by `account`


### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getAccountATs`
account | string | Required | account is an account ID (either RS address or number)

### Response Parameters

Parameter | Type | Description
--------- | ------ | -----------
ats | array | is a list of AT contracts [see AT Details](#get-at-details)
requestProcessingTime | numeric | is the API request processing time (in millisec)
