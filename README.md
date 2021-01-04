# Pre-requisite

- docker
- docker-compose

# Setup

- Open blockstack/testnet-miner-conf.toml
- Replace **<Enter your private key here>** with your private key
- Open docker-compose.yml
- Replace ./bitcoind-data with where you want to store bitcoin data. if you do not change this value, it is going to store in <cwd>/bitcoind-data
- Run following command to build and deploy

    docker-compose build && docker-compose up -d
