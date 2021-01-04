# Note
Always refer to the official documentation [here](https://docs.blockstack.org/start-mining). This is not a complete guide.

# Pre-requisite

- `docker`
- `docker-compose`
- Once your bitcoind is all synced up, you will also have to import your address using command `docker exec blockstack-mining-challenge-2_bitcoind_1 /bitcoin-0.20.1/bin/bitcoin-cli bitcoin-cli -rpcport=18332 -rpcuser=rpc -rpcpassword=rpc importaddress <btcAddress from JSON>`
- If you are running this first time, you will have to restart your stack-node after your bitcoind is all synced up. Use the following command (should be run from the this project direction)
`docker-compose restart blockstack`

# Setup

- Open `blockstack/testnet-miner-conf.toml`
- Replace `<Enter your private key here>` with your private key
- Open `docker-compose.yml`
- Replace `./bitcoind-data` with where you want to store bitcoin data. if you do not change this value, it is going to store in `<cwd>/bitcoind-data`
- Run following command to build and deploy

    `docker-compose build && docker-compose up -d`
