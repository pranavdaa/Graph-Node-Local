# Graph-Node-Local
docker-compose.yml is the only file required to run a graph node locally

## Steps to run graph-node locally
1. git clone repo
2. docker-compose up

## Deploy Subgraph on the local graph node deployment
1. graph create git_user_name/subgraph_name --node http://127.0.0.1:8020
2. graph deploy git_user_name/subgraph_name --debug --ipfs http://localhost:5001 --node http://127.0.0.1:8020

## Connecting the LocalGraph Node with Local Blockchain Instance(Ganache)
1. Run Ganache -  ganache-cli -h 0.0.0.0

### If you are using Mac operating system

2.1 In Docker compose file 'mainnet:http://host.docker.internal:8545' 
Note this only works if you are using mac

### In are using linux operating system
2.2 Find the server \
2.2.1 docker container ls | grep graph-node | cut -d' ' -f1 -> Will give u a container name \
2.2.2 docker exec {Result of step 3.1} /bin/bash -c 'apt install -y iproute2 && ip route' | awk '/^default via /{print $3}' \
2.3.Use the server in docker compose file EG - ethereum: 'mainnet:http://172.19.0.1:8020'


## Note 
Run only archive node of the EVM-Blockchain you are trying to index 
