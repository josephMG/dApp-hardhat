## DApp-Hardhat-Solidity
This project is a DApp hardhat solidity development environment template, and whole DApp contains a [golang backend](https://github.com/josephMG/dApp-backend), a [nextjs frontend](https://github.com/josephMG/dApp-frontend), and a [harthat solidity development environment](https://github.com/josephMG/dApp-hardhat). You can see the whole structure is over [here](https://github.com/josephMG/dApp-structure).

### How to use:
> Please see hardhat docker [usage](./HARDHAT_DOCKER_USAGE.md) first.

##### Build:
`docker-compose build`

##### Run:
`docker-compose up`

##### Export ABI:
`docker-compose run --rm hardhat yarn run hardhat export-abi --no-compile`

### Related projects:
- [Hardhat docker template](https://github.com/garethfuller/hardhat-template.git)
- [NextJS Frontend](https://github.com/josephMG/dApp-frontend)
- [Golang Backend](https://github.com/josephMG/dApp-backend)
