# AT Operations

## Create AT

more information need

## Get AT

```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getAT" \
  -d "at=9192603983782913483"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getAT",
  "at": 9192603983782913483
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getAT",
  "at": 9192603983782913483
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```



> The above request returns JSON structured like this:

```json
{
    "atVersion": 1,
    "creator": "15780098437841714406",
    "creatorRS": "BURST-2Z98-XJU6-A2UA-FDKZP",
    "stopped": false,
    "machineCode": "1e000000004c010100000000d0ed902e000000350103000000000...",
    "description": "Approx. every week 1 winner will receive the total wo...",
    "machineData": "0000000091d5030000d0ed902e000000020000002dcf030000a0d...",
    "frozen": true,
    "finished": true,
    "dead": false,
    "balanceNQT": "9864170030301",
    "nextBlock": 249660,
    "requestProcessingTime": 0,
    "minActivation": "1500000000",
    "running": false,
    "at": "9192603983782913483",
    "name": "LuckyAT",
    "atRS": "BURST-KBGD-MTM5-F3RF-9JP6Z",
    "prevBalanceNQT": "9864170030301",
    "creationBlock": 59761
}
```

Get AT smart contract details

### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getAT`
at | numeric | Required | `at` is the contract id

### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
atVersion | numeric | is the AT contract version
creator | string | is creator of the AT contract



















## Get AT Details

```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getATDetails" \
  -d "at=9192603983782913483"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getATDetails",
  "at": 9192603983782913483
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getATDetails",
  "at": 9192603983782913483
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```



> The above request returns JSON structured like this:

```json
{
    "atVersion": 1,
    "creator": "15780098437841714406",
    "creatorRS": "BURST-2Z98-XJU6-A2UA-FDKZP",
    "stopped": false,
    "machineCode": "1e000000004c010100000000d0ed902e000000350103000000000...",
    "description": "Approx. every week 1 winner will receive the total wo...",
    "machineData": "0000000091d5030000d0ed902e000000020000002dcf030000a0d...",
    "frozen": true,
    "finished": true,
    "dead": false,
    "balanceNQT": "9864170030301",
    "nextBlock": 249660,
    "requestProcessingTime": 0,
    "minActivation": "1500000000",
    "running": false,
    "at": "9192603983782913483",
    "name": "LuckyAT",
    "atRS": "BURST-KBGD-MTM5-F3RF-9JP6Z",
    "prevBalanceNQT": "9864170030301",
    "creationBlock": 59761
}
```

Get AT smart contract details, same as [Get AT](#get-at)

### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getATDetails`
at | numeric | Required | `at` is the contract id

### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
atVersion | numeric | is the AT contract version
creator | string | is creator of the AT contract




























## List AT Contracts

```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getATIds"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getATIds"
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getATIds",
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```

> The above request returns JSON structured like this:

```json
{
    "atIds": [
        "9192603983782913483",
        "4569261685979410777",
        "5080866903808682902",
        "7438451232804004876",
        "575775830774922757",
        "7410359864690133399",
        "10179754792140291018",
        "5385967310100409105",
        "7543289557548699616",
        "12431445788240948576",
        "4722687283147421361",
        "4318400438025577783",
        "6579249049307385965",
        "14300713972699400308"
    ],
    "requestProcessingTime": 0
}
```

Get list of all AT smart contract id's on the blockchain

### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getATIds`

### Response Parameters

Parameter | Type | Description
--------- | ------ | -----------
atIds | Array | is a list of AT smart contract ID's
requestProcessingTime | numeric | is the API request processing time (in millisec)
















## Get AT long

```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getATLong" \
  -d "hexString=616263"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getATLong",
  "hexString": "616263",
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getATLong",
  "hexString": "616263",
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```


> The above request returns JSON structured like this:

```json
{
    "hex2long": "6513249",
    "requestProcessingTime": 0
}
```

Converts Hexadecimal to Decimal, Hex is a base 16 number and decimal is a base 10 number

### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getATLong`
hexString | string | Required | `hexString` is a hex value

### Response Parameters

Parameter | Type | Description
--------- | ------ | -----------
hex2long | string | is decimal base 10 number
requestProcessingTime | numeric | is the API request processing time (in millisec)




















## Get Account AT's

```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getAccountATs" \
  -d "account=BURST-2Z98-XJU6-A2UA-FDKZP"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getAccountATs",
  "account": "BURST-2Z98-XJU6-A2UA-FDKZP",
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getAccountATs",
  "account": "BURST-2Z98-XJU6-A2UA-FDKZP",
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
            "creator": "15780098437841714406",
            "creatorRS": "BURST-2Z98-XJU6-A2UA-FDKZP",
            "stopped": false,
            "machineCode": "1e000000004c010100000000d0ed902e0000003501030000000002...",
            "description": "Approx. every week 1 winner will receive the total wor...",
            "machineData": "0000000091d5030000d0ed902e000000020000002dcf030000a0db...",
            "frozen": true,
            "finished": true,
            "dead": false,
            "balanceNQT": "9864170030301",
            "nextBlock": 249660,
            "minActivation": "1500000000",
            "running": false,
            "at": "9192603983782913483",
            "name": "LuckyAT",
            "atRS": "BURST-KBGD-MTM5-F3RF-9JP6Z",
            "prevBalanceNQT": "9864170030301",
            "creationBlock": 59761
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

