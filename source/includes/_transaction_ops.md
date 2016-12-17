# Transaction Operations

## Broadcast Transaction

```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=broadcastTransaction" \
  -d "transactionBytes=001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143..."
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "broadcastTransaction",
  "transactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143..."
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "broadcastTransaction",
  "transactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143..."
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```



> The above request returns JSON structured like this:

```json
{
 "requestProcessingTime": 4,
 "fullHash": "3a304584f20cf3d2cbbdd9698ff9a166427005ab98fbe9ca4ad6253651ee81f1",
 "transaction": "15200507403046301754"
}
```

Broadcast a transaction to the network. POST only.

### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `broadcastTransaction`
transactionBytes | string | Required | `transactionBytes` is the bytecode of a signed transaction (optional)
transactionJSON | object | Optional | `transactionJSON` is the transaction object (optional if transactionBytes provided)


### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
transaction | string | is the transaction ID
fullHash | string | is the full hash of the signed transaction
requestProcessingTime | numeric | is the API request processing time (in millisec)




















## Calculate Full Hash

```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=calculateFullHash" \
  -d "unsignedTransactionBytes=001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f2..." \
  -d "signatureHash=b35eae7d2f01639810d37694138aa0a86fbbf8a9bf58c2be4f2a5b8f0f30b3f7"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "calculateFullHash",
  "unsignedTransactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f2...",
  "signatureHash": "b35eae7d2f01639810d37694138aa0a86fbbf8a9bf58c2be4f2a5b8f0f30b3f7"
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "calculateFullHash",
  "unsignedTransactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f2...",
  "signatureHash": "b35eae7d2f01639810d37694138aa0a86fbbf8a9bf58c2be4f2a5b8f0f30b3f7"
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```



> The above request returns JSON structured like this:

```json
{
 "requestProcessingTime": 1,
 "fullHash": "3a304584f20cf3d2cbbdd9698ff9a166427005ab98fbe9ca4ad6253651ee81f1"
}
```

Calculate the full hash of a transaction.


### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `calculateFullHash`
transactionBytes | string | Required | `unsignedTransactionBytes` are the unsigned bytes of a transaction (optional if unsignedTransactionJSON is provided)
unsignedTransactionJSON | object | Optional | `unsignedTransactionJSON` is the unsigned transaction JSON object

### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
fullHash | string | is the full hash of the signed transaction
requestProcessingTime | numeric | is the API request processing time (in millisec)












## Escrow Sign

More information needed


















## Get Transaction

```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getTransaction" \
  -d "transaction=15200507403046301754"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getTransaction",
  "transaction": "15200507403046301754"
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getTransaction",
  "transaction": "15200507403046301754"
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```



> The above request returns JSON structured like this:

```json
{
 "senderPublicKey": "57fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143b473beec228f79ff93c",
 "signature": "5f0378b7390ff5a815eadd1354de533eef682f139362b153576e2207320a6...",
 "feeNQT": "100000000",
 "transactionIndex": 2,
 "requestProcessingTime": 2842,
 "type": 0,
 "confirmations": 849,
 "fullHash": "3a304584f20cf3d2cbbdd9698ff9a166427005ab98fbe9ca4ad6253651ee81f1",
 "version": 1,
 "ecBlockId": "17321329645912574173",
 "signatureHash": "b35eae7d2f01639810d37694138aa0a86fbbf8a9bf58c2be4f2a5b8f0f30b3f7",
 "senderRS": "BURST-L6FM-89WK-VK8P-FCRBB",
 "subtype": 0,
 "amountNQT": "100000000",
 "sender": "15323192282528158131",
 "recipientRS": "BURST-4VNQ-RWZC-4WWQ-GVM8S",
 "recipient": "17013046603665206934",
 "ecBlockHeight": 275727,
 "block": "8455642159445842600",
 "blockTimestamp": 29797208,
 "deadline": 60,
 "transaction": "15200507403046301754",
 "timestamp": 29796934,
 "height": 275730
}
```

Get a transaction object given a transaction ID.

### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getTransaction`
transaction | string | Required | `transaction` is the transaction ID (optional)
fullHash | string | Optional | `fullHash` is the full hash of the transaction (optional if transaction ID is provided)
includePhasingResult | string | Optional | `includePhasingResult` is true to retrieve execution status of each phased transaction (optional)
requireBlock | string | Optional | `requireBlock` is the block ID of a block that must be present in the blockchain during execution (optional)
requireLastBlock | string | Optional | `requireLastBlock` is the block ID of a block that must be last in the blockchain during execution (optional)



### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
ender | string | is the account ID of the sender
senderRS | string | is the Reed-Solomon address of the sender
feeNQT | string | is the fee (in NQT) of the transaction
amountNQT | string | is the amount (in NQT) of the transaction
transactionIndex | numeric | is a zero-based index giving the order of the transaction in its block
timestamp | numeric | is the time (in seconds since the genesis block) of the transaction
referencedTransactionFullHash | string | is the full hash of a transaction referenced by this one, omitted if no previous transaction is referenced
confirmations | numeric | is the number of transaction confirmations
subtype | numeric | is the transaction subtype (refer to Get Constants for a current list of subtypes)
block | string | is the ID of the block containing the transaction
blockTimestamp | numeric | is the timestamp (in seconds since the genesis block) of the block
height | numeric | is the height of the block in the blockchain
senderPublicKey | string | is the public key of the sending account for the transaction
type | numeric | is the transaction type (refer to Get Constants for a current list of types)
deadline | numeric | is the deadline (in minutes) for the transaction to be confirmed
signature | string | is the digital signature of the transaction
recipient | string | is the account number of the recipient, if applicable
recipientRS | string | is the Reed-Solomon address of the recipient, if applicable
fullHash | string | is the full hash of the signed transaction
signatureHash | string | is a SHA-256 hash of the transaction signature
approved | boolean | is a boolean indicating if the transaction is approved (only included when includePhasingResult is true and the transaction is phased)
result | string | is a string containing the result of the transaction (only included when includePhasingResult is true and the transaction is phased)
executionHeight | numeric | is the height the transaction was executed (only included when includePhasingResult is true and the transaction is phased)
transaction | string | is the transaction ID
version | numeric | is the transaction version number
phased | boolean | is true if the transaction is phased, false otherwise
ecBlockId | numeric | is the economic clustering block ID
ecBlockHeight | numeric | is the economic clustering block height
attachment | object | is an object containing any additional data needed for the transaction, if applicable
lastBlock | string | is the last block ID on the blockchain (applies if requireBlock is provided but not requireLastBlock)
requestProcessingTime | numeric | is the API request processing time (in millisec)


<aside class="notice">
  The block, blockTimestamp and confirmations fields are omitted for unconfirmed transactions. Double-spending transactions are not retrieved.
</aside>













## Get Transaction Bytes


```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getTransactionBytes" \
  -d "transaction=15200507403046301754"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getTransactionBytes",
  "transaction": "15200507403046301754"
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getTransactionBytes",
  "transaction": "15200507403046301754"
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```


> The above request returns JSON structured like this:

```json
{
 "unsignedTransactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143b473...",
 "requestProcessingTime": 66,
 "confirmations": 1019,
 "transactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143b473..."
}
```

Get the bytecode of a transaction.


### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getTransactionBytes`
transaction | string | Required | transaction is a transaction ID
requireBlock | string | optional | requireBlock is the block ID of a block that must be present in the blockchain during execution (optional)
requireLastBlock | string | optional | requireLastBlock is the block ID of a block that must be last in the blockchain during execution (optional)




### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
confirmations | numeric | is the number of transaction confirmations
transactionBytes | string | `transactionBytes` are the bytes contained in the transaction
unsignedTransactionBytes | object | `unsignedTransactionBytes` are the unsigned bytes contained in the transaction
prunableAttachmentJSON | string | is the prunable attachment JSON object, if applicable, because transactionBytes never includes prunable data
lastBlock | string | is the last block ID on the blockchain (applies if requireBlock is provided but not requireLastBlock)
requestProcessingTime | numeric | is the API request processing time (in millisec)




















## Get Unconfirmed Transaction Ids


```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getUnconfirmedTransactionIds" \
  -d "account=NXT-L6FM-89WK-VK8P-FCRBB"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getUnconfirmedTransactionIds",
  "account": "NXT-L6FM-89WK-VK8P-FCRBB"
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getUnconfirmedTransactionIds",
  "account": "NXT-L6FM-89WK-VK8P-FCRBB"
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```


> The above request returns JSON structured like this:

```json
{
 "requestProcessingTime": 1,
 "unconfirmedTransactionIds": []
}
```

Get a list of unconfirmed transaction IDs associated with an account.



### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getUnconfirmedTransactionIds`
account | string | optional | account is one account ID
requireBlock | string | optional | requireBlock is the block ID of a block that must be present in the blockchain during execution
requireLastBlock | string | optional | requireLastBlock is the block ID of a block that must be last in the blockchain during execution




### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
unconfirmedTransactionIds | array | is an array of unconfirmed transaction IDs
lastBlock | string | is the last block ID on the blockchain (applies if requireBlock is provided but not requireLastBlock)
requestProcessingTime | numeric | is the API request processing time (in millisec)




















## Get Unconfirmed Transactions



```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=getUnconfirmedTransactions" \
  -d "account=NXT-L6FM-89WK-VK8P-FCRBB"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getUnconfirmedTransactions",
  "account": "NXT-L6FM-89WK-VK8P-FCRBB"
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "getUnconfirmedTransactions",
  "account": "NXT-L6FM-89WK-VK8P-FCRBB"
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```


> The above request returns JSON structured like this:

```json
{
 "unconfirmedTransactions": [],
 "requestProcessingTime": 1
}
```

Get a list of unconfirmed transactions associated with an account.


### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `getUnconfirmedTransactions`
account | string | optional | account is one account ID
requireBlock | string | optional | requireBlock is the block ID of a block that must be present in the blockchain during execution
requireLastBlock | string | optional | requireLastBlock is the block ID of a block that must be last in the blockchain during execution




### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
unconfirmedTransactionIds | array | is an array of unconfirmed transaction IDs
lastBlock | string | is the last block ID on the blockchain (applies if requireBlock is provided but not requireLastBlock)
requestProcessingTime | numeric | is the API request processing time (in millisec)








## Parse Transaction



```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=parseTransaction" \
  -d "transactionBytes=001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143..."
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "parseTransaction",
  "transactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143..."
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "parseTransaction",
  "transactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143..."
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```


> The above request returns JSON structured like this:

```json
{
 "senderPublicKey": "57fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143b473beec228f79ff93c",
 "signature": "5f0378b7390ff5a815eadd1354de533eef682f139362b153576e2207320a6...",
 "feeNQT": "100000000",
 "requestProcessingTime": 2,
 "type": 0,
 "fullHash": "3a304584f20cf3d2cbbdd9698ff9a166427005ab98fbe9ca4ad6253651ee81f1",
 "version": 1,
 "ecBlockId": "17321329645912574173",
 "signatureHash": "b35eae7d2f01639810d37694138aa0a86fbbf8a9bf58c2be4f2a5b8f0f30b3f7",
 "senderRS": "BURST-L6FM-89WK-VK8P-FCRBB",
 "subtype": 0,
 "amountNQT": "100000000",
 "sender": "15323192282528158131",
 "recipientRS": "BURST-4VNQ-RWZC-4WWQ-GVM8S",
 "recipient": "17013046603665206934",
 "ecBlockHeight": 275727,
 "verify": true,
 "deadline": 60,
 "transaction": "15200507403046301754",
 "timestamp": 29796934,
 "height": 2147483647
}
```

Get a transaction object given a (signed or unsigned) transaction bytecode, or re-parse a transaction object. Verify the signature.


### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `parseTransaction`
transactionBytes | string | optional | is the transaction object (optional if transactionBytes is included)
transactionJSON | string | optional | requireBlock is the block ID of a block that must be present in the blockchain during execution
requireBlock | string | optional | is the block ID of a block that must be present in the blockchain during execution (optional)
requireLastBlock | string | optional | is the block ID of a block that must be last in the blockchain during execution (optional)




### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
verify | boolean | is true if the signature is verified, false otherwise

<aside class="notice">
  Refer to [Get Transaction](#get-transaction) for additional fields.
</aside>










## Send Money Escrow

<aside class="notice">
  more information needed
</aside>


## Send Money Subscription

<aside class="notice">
  more information needed
</aside>

















## Sign Transaction


```shell
curl https://wallet.burst-team.us:8125/burst \
  -d "requestType=signTransaction" \
  -d "unsignedTransactionBytes=001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143..." \
  -d "secretPhrase=SecretPhrase"
```

```python
import requests

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "signTransaction",
  "unsignedTransactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143...",
  "secretPhrase": "SecretPhrase"
}

r = requests.get(url, params)

print r.json()

```

```ruby
require 'unirest'

url = "https://wallet.burst-team.us:8125/burst"

params = {
  "requestType": "signTransaction",
  "unsignedTransactionBytes": "001046aac6013c0057fb6f3a958e320bb49c4e81b4c2cf28b9f25d086c143...",
  "secretPhrase": "SecretPhrase"
}

r = Unirest.get(url, parameters: params)

print r.raw_body

```


> The above request returns JSON structured like this:

```json
{
 "signatureHash": "3f4830bf28f105d5075f5e084c36e4582a156e713abfe0bc6ee51cbf8b20f2d2",
 "transactionJSON": {
  "senderPublicKey": "10f09c34f225d425306e5be55a4946908156072afbead4d574a512d7e086ef5c",
  "signature": "24513e93029688100c5a04183ffddc49812fd7a137a15fb3a2545aa9a2bcb5004a3...",
  "feeNQT": "100000000",
  "type": 0,
  "fullHash": "c34af8f1509e3be79c4562e24125ff2a8f026871fdd1a0366ad315bf8fab76b9",
  "version": 1,
  "phased": false,
  "ecBlockId": "15869644242181198665",
  "signatureHash": "3f4830bf28f105d5075f5e084c36e4582a156e713abfe0bc6ee51cbf8b20f2d2",
  "attachment": {
   "version.OrdinaryPayment": 0
  },
  "senderRS": "BURST-4VDY-LNVT-LMAY-FMCKA",
  "subtype": 0,
  "amountNQT": "1000000000",
  "sender": "15295723609781267838",
  "recipientRS": "BURST-BMUV-8QQR-47VK-CR7F3",
  "recipient": "11580081983047651163",
  "ecBlockHeight": 382777,
  "deadline": 1440,
  "transaction": "16662085316881435331",
  "timestamp": 54328076,
  "height": 2147483647
 },
 "verify": true,
 "requestProcessingTime": 5,
 "transactionBytes": "00100cfb3c03a00510f09c34f225d425306e5be55a4946908156072afbead4...",
 "fullHash": "c34af8f1509e3be79c4562e24125ff2a8f026871fdd1a0366ad315bf8fab76b9",
 "transaction": "16662085316881435331"
}
```

Calculates the full hash, signature hash, and transaction ID of an unsigned transaction.


### Request Parameters

Parameter | Type | Required | Description
--------- | --------- | --------- | -----------
requestType | string | Required | `requestType` is `signTransaction`
unsignedTransactionJSON | string | optional | is the transactionJSON field of the transaction, without a signature subfield
unsignedTransactionBytes | string | Required | is the unsignedTransactionBytes field of the transaction (optional, if unsignedTransactionJSON provided)
requireBlock | string | optional | is the block ID of a block that must be present in the blockchain during execution (optional)
requireLastBlock | string | optional | is the block ID of a block that must be last in the blockchain during execution (optional)
prunableAttachmentJSON | string | optional | is a prunable attachment JSON object, if applicable, because unsignedTransactionBytes never includes prunable data (optional if the transaction has already been broadcast and the prunable message can still be retrieved from the database)
secretPhrase | string | Required | secretPhrase is the secret passphrase of the signing account
validate | string | optional | is false to skip validation of the transaction bytes being signed (useful on nodes where the full blockchain is not downloaded)



### Response Parameters

Parameter | Type | Description
--------- | ------- | -----------
signatureHash | string | is a SHA-256 hash of the transaction signature, used in escrow transactions
verify | boolean | is true the signature is verified, false if not
transactionJSON | object | is the signed transaction JSON object
transactionBytes | string | are the signed transaction bytes
fullHash | string | is the full hash of the signed transaction
prunableAttachmentJSON | object | is the prunable attachment JSON object, if applicable, because transactionBytes never includes prunable data
transaction | string | is the transaction ID, derived from the fullHash
lastBlock | string | is the last block ID on the blockchain (applies if requireBlock is provided but not requireLastBlock)
requestProcessingTime | numeric | is the API request processing time (in millisec)




## Subscription Cancel

<aside class="notice">
  need more information
</aside>