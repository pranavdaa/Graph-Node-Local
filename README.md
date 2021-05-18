# Graph-Node-Local
docker-compose.yml is the only file required to run a graph node locally

## Steps to run graph-node locally
1. git clone repo
2. docker-compose up

## Deploy Subgraph on the local graph node deployment
1. graph create git_user_name/subgraph_name --node http://127.0.0.1:8020
2. graph deploy git_user_name/subgraph_name --debug --ipfs http://localhost:5001 --node http://127.0.0.1:8020
