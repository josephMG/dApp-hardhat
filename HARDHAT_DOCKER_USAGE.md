# Hardhat Template
This hardhat template comes with some setup scripts, tasks and an example docker compose service to get contract development into your app quickly.

The idea is that it can be dropped into any frontend project using docker compose easily. Allowing you to quickly iterate on contract development and integration with your frontend.

## Getting started
Add the following service to your `docker-compose.yml`:
```yaml
hardhat:
  build:
    context: ./hardhat
    dockerfile: Dockerfile.dev
  restart: always
  command: yarn run dev
  volumes: 
    - ./hardhat:/app
    - /app/node_modules
  ports:
    - 8545:8545
```

Once the service has been started with `docker-compose up` you contracts will be deployed to the localhost:8545 RPC. When you save the contract files they will be redeployed.

## Deployment
First add your credentials to the `.env.example` file and rename to `.env`.

To deploy to networks other than localhost you can run commands like:
```bash
docker-compose run hardhat mainnet:deploy
```
For a full list of deployment commands for different networks see [package.json](/package.json).

## Tasks
There are a default tasks for interacting with the localhost network when it's up and running. 
```bash
docker-compose exec hardhat accounts # fetch list of default network accounts
docker-compose exec hardhat balance <address> # Get balance for an address
docker-compose exec hardhat send --from <address> --to <address> --amount 10 # Send ETH from one address to another
docker-compose exec hardhat blockNumber # Get the current blocknumber
