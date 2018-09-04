# Chainlink CryptoCompare External Adapter

Adapter for use on Google Cloud Platform or AWS Lambda. Upload Zip and use trigger URL as bridge endpoint.

## Install

```bash
npm install
```

Create zip:

```bash
zip -r cl-cc.zip .
```

Create a cloud function in GCP or Lambda, and set the handler function according to the platform you are using.

* GCP: `gcpservice`
* AWS: `handler`

## Test Cases (GCP test events)

Fail: 
```json
{
  "id": "278c97ffadb54a5bbb93cfec5f7b5503",
  "data": {}
}
```

```json
{
  "jobRunID":"278c97ffadb54a5bbb93cfec5f7b5503",
  "data": {
    "Response": "Error",
    "Message": "",
    "Type": 1,
    "Aggregated":
    false,
    "Data": [],
    "Path": "/data/",
    "ErrorsSummary": "Not implemented"
  }
}
```

Pass:
```json
{
  "id": "278c97ffadb54a5bbb93cfec5f7b5503",
  "data": {
    "endpoint": "price",
    "fsym": "ETH",
    "tsyms": "USD"
  }
}
```

```json
{
  "id": "278c97ffadb54a5bbb93cfec5f7b5503",
  "data": {
    "endpoint": "price",
    "fsym": "ETH",
    "tsyms": "USD,EUR,JPY"
  }
}
```

```json
{
  "id": "278c97ffadb54a5bbb93cfec5f7b5503",
  "data": {
    "endpoint": "pricemulti",
    "fsyms": "BTC,ETH",
    "tsyms": "USD,EUR"
  }
}
```

```json
{
  "id": "278c97ffadb54a5bbb93cfec5f7b5503",
  "data": {
    "endpoint": "pricemultifull",
    "fsyms": "BTC,ETH",
    "tsyms": "USD,EUR"
  }
}
```

```json
{
  "id": "278c97ffadb54a5bbb93cfec5f7b5503",
  "data": {
    "endpoint": "generateAvg",
    "fsym": "ETH",
    "tsym": "USD",
    "exchange": "Kraken"
  }
}
```
