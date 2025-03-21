# Light Node Setup Guide

## Step 1: Clone the Light Node Repository
```
git clone https://github.com/Layer-Edge/light-node.git && cd light-node
```
## Step 2: Install Required Dependencies
```
curl -L https://risczero.com/install | bash && rzup install
```
```
rzup show
```
## Step 3: Configure Environment Variables
```
nano .env
```
### * Replace 'cli-node-private-key' with the actual private key
```
GRPC_URL=grpc.testnet.layeredge.io:9090
CONTRACT_ADDR=cosmos1ufs3tlq4umljk0qfe8k5ya0x6hpavn897u2cnf9k0en9jr7qarqqt56709
ZK_PROVER_URL=http://127.0.0.1:3001
# Alternatively:
ZK_PROVER_URL=https://layeredge.mintair.xyz/
API_REQUEST_TIMEOUT=100
POINTS_API=https://light-node.layeredge.io
PRIVATE_KEY='cli-node-private-key'
```
## Step 4: Start the Merkle Service
```
cd risc0-merkle-service && cargo build
```
```
screen -dmS risc0-service cargo run
```
## Step 5: Build and Run the LayerEdge Light Node
```
cd $HOME/light-node/ && screen -S lightnode
```
```
go build && ./light-node
```
##          Done!







