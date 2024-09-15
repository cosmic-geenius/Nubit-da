# Nubit-da

## 1. Sync State of the Header

Endpoint: <YOUR_NODE_ENDPOINT>

Method: POST

Request:

```
curl -X POST -H "Content-Type: application/json" -H "Authorization: Bearer <YOUR_API_KEY>" -d '{"id": 1, "jsonrpc": "2.0", "method": "header.SyncState", "params": []}' <YOUR_NODE_ENDPOINT>
```
Description: Retrieves the sync state of the node's header.

## 2. Get Blob by Commitment

Method: blob.Get

Description: Retrieves a blob by its KZG commitment under a given namespace and height.

Request:

```
{
  "jsonrpc": "2.0",
  "method": "blob.Get",
  "params": [
    42,
    "AAAAAAAAAAAAAAAAAAAAAAAAAAECAwQFBgcICRA=",
    "Bw=="
  ],
  "id": 0
}
```
## 3. Get All Blobs

Method: blob.GetAll

Description: Retrieves all blobs under a given namespace at a specific height.

Request:

```
{
  "jsonrpc": "2.0",
  "method": "blob.GetAll",
  "params": [
    42,
    [
      "AAAAAAAAAAAAAAAAAAAAAAAAAAECAwQFBgcICRA="
    ]
  ],
  "id": 0
}
```
## 4. Get Proof for Blob

Method: blob.GetProof

Description: Retrieves the proof of a blob by commitment under a given namespace and height.

Request:

```
{
  "jsonrpc": "2.0",
  "method": "blob.GetProof",
  "params": [
    42,
    "AAAAAAAAAAAAAAAAAAAAAAAAAAECAwQFBgcICRA=",
    "Bw=="
  ],
  "id": 0
}
```
## 5. Submit Blobs

Method: blob.Submit

Description: Sends blobs and reports the block height where they were included.

Request:

```
{
  "jsonrpc": "2.0",
  "method": "blob.Submit",
  "params": [
    [
      {
        "commitment": "20qrISWy41i+3YG4pGbmtw3BbsK875MrcRX8bTgJOMk=",
        "data": "VGhpcyBpcyBhbiBleGFtcGxlIG9mIHNvbWUgYmxvYiBkYXRh",
        "index": -1,
        "namespace": "AAAAAAAAAAAAAAAAAAAAAAAAAAECAwQFBgcICRA=",
        "share_version": 0
      }
    ],
    0.002
  ],
  "id": 0
}
```
## 6. Sampling Stats

Method: das.SamplingStats

Description: Retrieves current statistics from the data availability sampling process.

Request:

```
{
  "jsonrpc": "2.0",
  "method": "das.SamplingStats",
  "params": null,
  "id": 0
}
```
## 7. Get Local Header

Method: header.LocalHead

Description: Returns the current local chain head (the latest block header the node has processed).

Request:

```
{
  "jsonrpc": "2.0",
  "method": "header.LocalHead",
  "params": null,
  "id": 0
}
```
## 8. Network Head

Method: header.NetworkHead

Description: Returns the Syncer’s view of the current network head.

Request:
```
{
  "jsonrpc": "2.0",
  "method": "header.NetworkHead",
  "params": null,
  "id": 0
}
```

These APIs use JSON-RPC protocol and require a POST request to the node endpoint with appropriate parameters and authentication. Each API method returns structured responses in JSON format.

Make sure to replace placeholders like <YOUR_API_KEY> and <YOUR_NODE_ENDPOINT> with actual values for your setup.
