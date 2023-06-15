# Running DaNetwork TestNet Node

## Runing sync Node
To download the TestNet project from GitHub, open a command line and execute the following command:
```
git clone https://github.com/DaNetworkTech/TestNet
```

Once downloaded, navigate to the TestNet directory and make the danetwork-linux-amd64 binary executable by running:
```
cd TestNet
chmod u+x danetwork-linux-amd64
```
After changing the permissions, run the test chain using the node.toml configuration file as a parameter. To start the test chain, enter the following command in the command line:
```
./danetwork-linux-amd64 --config node.toml
```
Note: Make sure you have installed the necessary dependencies and tools to build, run, and test the software successfully.

## Running DaNetwork TestNet Miner

1 Create an account for Node using the passwords: nodepwd1 .

```bash
./danetwork-linux-amd64 --config node.toml account new

Loading config file from node.toml
Please note that password is NOT RECOVERABLE.
Type password:  # type the password given above
Repeat password:  # type again
0xc974716fbfd96dea9327a4dd7b4d0262e0a4cde5
```
2 Create a file node.pwd containing the password "nodepwd1"

```bash
echo "nodepwd1" > node.pwd
```

3 Use this address and password file right away in our node.toml configuration file. Add and uncomment the address as engine_signer in the [mining] section and add the password file in the [account] section as follow:

```toml
[account]
password = ["node.pwd"]

[mining]
engine_signer = "0xc974716fbfd96dea9327a4dd7b4d0262e0a4cde5"
reseal_on_txs = "none"
force_sealing = true

```

4 Post the address 0xc974716fbfd96dea9327a4dd7b4d0262e0a4cde5 on the maintenance channel of danetwork's Slack node, and after joining the smart contract, this node can mine new block.


