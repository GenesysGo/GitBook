# Shadow Drive SDK

The Shadow Drive SDK is written to provide Solana developers with all the tools they need in order to build on top of Shadow Drive.



[https://www.npmjs.com/package/@shadow-drive/sdk\

](https://www.npmjs.com/package/@shadow-drive/sdkhttps://www.npmjs.com/package/@shadow-drive/cli)

[https://genesysgo.github.io/shadow-drive/](https://genesysgo.github.io/shadow-drive/)

## Quick Setup

### Install

Install these dependencies:

```shell
yarn add @shadow-drive/sdk
```

### Setup (React)
```tsx
import React, { useEffect } from "react";
import * as anchor from "@project-serum/anchor";
import {ShdwDrive} from "@shadow-drive/sdk";
import { AnchorWallet, useAnchorWallet, useConnection } from "@solana/wallet-adapter-react";
export default function Drive() {
	const { connection } = useConnection();
	const wallet = useAnchorWallet();
	useEffect(() => {
		(async () => {
			if (wallet?.publicKey) {
				const drive = await new ShdwDrive(connection, wallet).init();
			}
		})();
	}, [wallet?.publicKey])
	return (
		<div></div>
	)
}
```

### Setup (NodeJS)
```js
import {ShdwDrive} from "@shadow-drive/sdk";
const drive = await new ShdwDrive(connection, wallet).init();
```


### Get all storage accounts
```js
const accounts = await drive.getStorageAccounts();
```

### Get storage account with public key
```js
const account = await drive.getStorageAccount(new anchor.web3.PublicKey("your public key"));
```

### Create a storage account

Specify the storage unit, currently only KB, MB and GB is supported
```js
const account = await drive.createStorageAccount('your account name-doesnt need to be unique', '1MB');
```
