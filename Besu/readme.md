# Astor TestNet

1. Start full Astor node with local RPC enabled

```
docker run --name besu-astor-node -p 8545:8545 hyperledger/besu:develop --network=astor --sync-mode=FULL --rpc-http-enabled --rpc-ws-enabled --bootnodes=enode://b638fc3dca6181ae97fac2ea0157e8330f5ac8a20c0d4c63aa6f98dcbac4e35b4e023f656757b58c1da7a7b2be9ffad9342e0f769b8cf0f5e35ff73116ff7dfd@3.16.171.213:30303
```

2. Start full Astor node with local RPC and GPU mining enabled

```
docker run --name astor-node -p 8545:8545 hyperledger/besu:develop --data-path=/var/lib/besu --network=astor --sync-mode=FULL --rpc-http-enabled --rpc-ws-enabled --miner-enabled --miner-coinbase=<account-address> --miner-stratum-enabled --miner-stratum-host=0.0.0.0 --miner-stratum-port=8008 --miner-extra-data=<hexadecimal-value> --bootnodes=enode://b638fc3dca6181ae97fac2ea0157e8330f5ac8a20c0d4c63aa6f98dcbac4e35b4e023f656757b58c1da7a7b2be9ffad9342e0f769b8cf0f5e35ff73116ff7dfd@3.16.171.213:30303
```

https://eserialize.com/?input=string&output=hex to translate a string to hex value for the `--miner-extra-data=<hexadecimal-value>`. E.g.: `Metallica` > `0x4d6574616c6c696361`)


3. Start full Astor node with local RPC and CPU mining enabled
   
```
docker run --name astor-node -p 8545:8545 hyperledger/besu:develop --data-path=/var/lib/besu --network=astor --sync-mode=FULL --rpc-http-enabled --rpc-ws-enabled --miner-enabled --miner-coinbase=<account-address> --miner-extra-data=<hexadecimal-value> --bootnodes=enode://b638fc3dca6181ae97fac2ea0157e8330f5ac8a20c0d4c63aa6f98dcbac4e35b4e023f656757b58c1da7a7b2be9ffad9342e0f769b8cf0f5e35ff73116ff7dfd@3.16.171.213:30303
```