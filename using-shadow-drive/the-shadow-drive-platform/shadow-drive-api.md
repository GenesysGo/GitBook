---
description: >-
  Shadow Drive exposes an API that you can interact directly without the need of
  the CLI or SDK. You may build on top of these methods.
---

# Shadow Drive API

Mainnet-Beta API Base URL: https://shadow-storage.genesysgo.net

<details>

<summary>POST /storage-account - Creates a new storage account</summary>

Request content type: application/json

Parameters:

1. transaction: Serialized create storage account transaction that's partially signed by the storage account owner

Response:

```json
{
    "shdw_bucket": String,
    "transaction_signature": String
}
```

</details>

<details>

<summary>POST /storage-account-info - Gets on-chain and Shadow Drive Network data about a storage account</summary>

Request content type: application/json

Parameters:

1. storage\_account: Publickey of the storage account you want to get information for

Response for V1 Storage Account:

```
{
  storage_account: PublicKey,
  reserved_bytes: Number,
  current_usage: Number,
  immutable: Boolean,
  to_be_deleted: Boolean,
  delete_request_epoch: Number,
  owner1: PublicKey,
  owner2: PublicKey,
  accountCoutnerSeed: Number,
  creation_time: Number,
  creation_epoch: Number,
  last_fee_epoch: Number,
  identifier: String
  version: "V1"
}
```

Response for V2 Storage Account

```
{
  storage_account: PublicKey,
  reserved_bytes: Number,
  current_usage: Number,
  immutable: Boolean,
  to_be_deleted: Boolean,
  delete_request_epoch: Number,
  owner1: PublicKey,
  accountCoutnerSeed: Number,
  creation_time: Number,
  creation_epoch: Number,
  last_fee_epoch: Number,
  identifier: String,
  version: "V2"
}
```

</details>

<details>

<summary>POST /upload - Uploads a single file or multiple files at once</summary>

Request content type: multipart/form-data

Parameters (FormData fields):

1. file: The file you want to upload. You may add up to 5 files each with a field name of `file`.
2. message: Base58 message signature.&#x20;
3. signer: Publickey of the signer of the message signature and owner of the storage account
4. storage\_account: Key of the storage account you want to upload to

Example implementation: [https://gist.github.com/tracy-codes/608d8a6e5d917cfff86167250812ebe4](https://gist.github.com/tracy-codes/608d8a6e5d917cfff86167250812ebe4)

Response:

```json
{
    "finalized_locations": [String],
    "message": String
    "upload_errors": [{file: String, storage_account: String, error: String}] or [] if no errors
}
```

</details>

<details>

<summary>POST /edit - Edits an existing file</summary>

Request content type: multipart/form-data

Parameters (FormData fields):

1. file: The file you want to upload. You may add up to 5 files each with a field name of `file`.
2. message: Base58 message signature.&#x20;
3. signer: Publickey of the signer of the message signature and owner of the storage account
4. storage\_account: Key of the storage account you want to upload to

Example implementation: [https://gist.github.com/tracy-codes/3aab96f4c23086d6124835436d4ca6f4](https://gist.github.com/tracy-codes/3aab96f4c23086d6124835436d4ca6f4)

Response:

```
{
    "finalized_location": String,
    "error": String or not provided if no error
}
```

</details>

<details>

<summary>POST /list-objects - Get a list of all files associated with a storage account</summary>

Request content type: application/json

Parameters:

1. storageAccount: String version of the storage account PublicKey that you want to get a list of files for

Response:

```
{
    "keys": [String]
}
```

</details>

<details>

<summary>POST /get-object-data - Get information about an object</summary>

Request content type: application/json

Parameters:

1. Location: URL of the file you want to get information for

Response: JSON object of the file's metadata in the Shadow Drive Network or an error

</details>

<details>

<summary>POST /delete-file - Deletes a file from a given Storage Account</summary>

Request content type: application/json

Parameters:

1. message: Base58 message signature.&#x20;
2. signer: Publickey of the signer of the message signature and owner of the storage account
3. location: URL of the file you want to delete

Example implementation: [https://gist.github.com/tracy-codes/e4597e6fb71733b93e540ef4c14431c9](https://gist.github.com/tracy-codes/e4597e6fb71733b93e540ef4c14431c9)

Response:

```
{
    "message": String,
    "error": String or not passed if no error
}
```

</details>

<details>

<summary>POST /add-storage</summary>

Request content type: application/json

Parameters:

1. transaction - Serialized add storage transaction that is partially signed by the shadow drive network

Response:

```
{
    message: String,
    transaction_signature: String,
    error: String or not provided if no error
}
```

</details>

<details>

<summary>POST /reduce-storage</summary>

Request content type: application/json

Parameters:

1. transaction - Serialized reduce storage transaction that is partially signed by the shadow drive network

Response:

```
{
    message: String,
    transaction_signature: String,
    error: String or not provided if no error
}
```

</details>

<details>

<summary>POST /make-immutable</summary>

Request content type: application/json

Parameters:

1. transaction - Serialized make immutable transaction that is partially signed by the shadow drive network

Response:

```
{
    message: String,
    transaction_signature: String,
    error: String or not provided if no error
}
```

</details>
