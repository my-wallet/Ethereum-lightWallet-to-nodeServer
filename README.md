# Ethereum tx watch:

Spec:
- Hash this document `./filetohash.txt`: done
- Create eth tx with hash as data: done
- Watch that tx in blocks and get back the info: done
- How user can create a key, signed a tx and send the output to server which pays the fee for transmission on eth:
  - Local client (with no ether setup) creates a raw tx and will send the raw output to the nodejs server which will execute it (and pay the fees) 
  - How to create an ethereum private, based on a simple password (ex: myetherwallet style)


## Prerequisit

## How to use:

- Run Geth on localhost:8544 with an unlocked account holding ether
   - Geneva devchain blockchain
   - Or testrpc
   - Do not run any prod node or the ETHER WILL BE LOST!

- Edit `ethtx.hmtl` with var: `data`, and `gethNode`
- Open in a browser `ethtx.hmtl`
- Send some ether and check the result


## Annexes 

### Hash the file
- Hash file: `sha256sum filetohash.txt`
- result: `645d74b98bad73e062c1227a5dbfbfde87fb747390f04dd34cec6e5b7695c564  filetohash.txt`

### Create eth tx
- Check geth status: `curl -X POST --data '{"jsonrpc":"2.0","method":"eth_syncing","params":[],"id":1}' localhost:8544`
- Check balance: `curl -X POST --data '{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x99b77b612d43ba830d9db1eda0d0d23600db6874", "latest"],"id":1}' localhost:8544`

- Send a tx: `curl -X POST --data '{"jsonrpc":"2.0","method":"eth_syncing","params":[],"id":1}' localhost:8544`

curl -X POST --data '{"jsonrpc":"2.0","method":"eth_sendTransaction","params":[{see above}],"id":1}' localhost:8544


