Ethereum Network Intelligence API
============
[![Build Status][travis-image]][travis-url] [![dependency status][dep-image]][dep-url]

This is the backend service which runs along with ethereum and tracks the network status, fetches information through JSON-RPC and connects through WebSockets to [eth-netstats](https://github.com/cubedro/eth-netstats) to feed information. For full install instructions please read the [wiki](https://github.com/ethereum/wiki/wiki/Network-Status).


## Prerequisite
* eth, geth or pyethapp
* node
* npm


## Installation from source 
```bash
git clone https://github.com/ecroxchain/eth-net-intelligence-api.git
```

## Configuration
Configure the app modifying [processes.json](/eth-net-intelligence-api/blob/master/app1.json). Note that you have to modify the backup app1.json file located in `./app1.json` (to allow you to set your env vars without being rewritten when updating).

```json
"env":
	{
		"NODE_ENV"        : "production", // tell the client we're in production environment
		"RPC_HOST"        : "localhost", // eth JSON-RPC host
		"RPC_PORT"        : "8545", // eth JSON-RPC port
		"LISTENING_PORT"  : "30303", // eth listening port (only used for display)
		"INSTANCE_NAME"   : "", // whatever you wish to name your node
		"CONTACT_DETAILS" : "", // add your contact details here if you wish (email/skype)
		"WS_SERVER"       : "https://status.ecroxscan.com", // path to eth-netstats WebSockets api server
		"WS_SECRET"       : "", // WebSockets API server secret used for login. You need to ask the owner of the chain.
		"VERBOSITY"       : 2 // Set the verbosity (0 = silent, 1 = error, warn, 2 = error, warn, info, success, 3 = all logs)
	}
```
## Run
Run it using pm2:

```bash
cd ~/eth-net-intelligence-api
pm2 start app1.json
```

