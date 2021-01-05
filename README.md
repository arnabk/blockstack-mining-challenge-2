# Note
Always refer to the official documentation [here](https://docs.blockstack.org/start-mining). This is not a complete guide.

# Pre-requisite

- `docker`
- `docker-compose`
- Once your bitcoind is all synced up, you will also have to import your address using command `docker exec <bitcoind-container-id> /bitcoin-0.20.1/bin/bitcoin-cli bitcoin-cli -rpcport=18332 -rpcuser=rpc -rpcpassword=rpc importaddress <btcAddress from JSON>`
- If you are running this first time, you will have to restart your stack-node after your bitcoind is all synced up. Use the following command (should be run from the this project direction)
`docker-compose restart blockstack`

# Setup

- Open `blockstack/testnet-miner-conf.toml`
- Replace `<Enter your private key here>` with your private key
- Open `docker-compose.yml`
- Replace `./bitcoind-data` with where you want to store bitcoin data. if you do not change this value, it is going to store in `<cwd>/bitcoind-data`
- Run following command to build and deploy

    `docker-compose build && docker-compose up -d`

# Other useful commands
- If you want to check your bitcoind progress, run `docker logs <bitcoind-container-id>` and check `progress=`. If it shows `progress=1.0`, then your bitcoin node is all synced up
- If you want to check your local stack tip, run `curl http://localhost:20443/v2/info | jq`. This command assumes you have `curl` and `jq` installed in your system
