# Utilities Operations

## Long Convert


```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=longConvert" \
  -d "id=9522465949435965562"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "longConvert",
  "id": 9522465949435965562
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "longConvert",
  "id": 9522465949435965562
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```



> The above request returns JSON structured like this:

```json
{
 "stringId": "15323192282528158131",
 "requestProcessingTime": 0,
 "longId": "-3123551791181393485"
}
```

Converts an ID to the signed long integer representation used internally.

### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `longConvert`
id | numeric | Required | `id` is a numerical ID, in decimal form but equivalent to an 8-byte unsigned integer as produced by SHA-256 hashing

### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
stringId | string | is `balanceNQT` less unconfirmed outgoing transactions, the balance displayed in the client
requestProcessingTime | numeric | is the API request processing time (in millisec)
longId | string | is the signed long integer (8-bytes) representation of the ID used internally, returned as a string







## RS Convert


```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=rsConvert" \
  -d "account=BURST-6E5U-CJQY-NUR3-ASNBA"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "rsConvert",
  "account": "BURST-6E5U-CJQY-NUR3-ASNBA"
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "rsConvert",
  "account": "BURST-6E5U-CJQY-NUR3-ASNBA"
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```


> The above request returns JSON structured like this:

```json
{
 "accountRS": "BURST-6E5U-CJQY-NUR3-ASNBA",
 "requestProcessingTime": 0,
 "account": "9522465949435965562"
}
```

Get both the Reed-Solomon account address and the account number given an account ID.

### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `longConvert`
account | string | Required | account is an account ID (either RS address or number)

### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
accountRS | string | is the Reed-Solomon address of the account
requestProcessingTime | numeric | is the API request processing time (in millisec)
account | string | is the account number

