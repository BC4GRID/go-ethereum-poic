

## Go Ethereum with Time-Memory-Data Trade-Off Based Consensus Protocol

This repository hosts the integration of a Time-Memory-Data Trade-Off (TMD-TO) based consensus protocol into the official Go Ethereum implementation (Details regarding the protocol can be found in the following [publication](https://doi.org/10.1109/ACCESS.2020.3013199). This protocol introduces a unique puzzle, centered around inverting a one-way function, solved using the TMD-TO approach. This paradigm shift allows for reduced energy consumption, leveraging memory to solve computational puzzles efficiently.

## Building the Source

To build `geth`, you'll need Go (version 1.19 or newer) and a C compiler. These can be installed via your preferred package manager. After setting up the prerequisites, build the project with the following command:

```shell
make geth
```

## Executables

The go-ethereum project includes several executables located in the `cmd` directory.

|  Command   | Description                                                                                                  |
|------------|--------------------------------------------------------------------------------------------------------------|
| **`geth`** | The primary Ethereum CLI client featuring the new consensus protocol. For command line options, use `geth --help` and refer to the [CLI documentation](https://geth.ethereum.org/docs/fundamentals/command-line-options). |

## Running `geth`

An exhaustive list of command line flags is beyond the scope of this document. For detailed information, consult the [CLI Wiki page](https://geth.ethereum.org/docs/fundamentals/command-line-options). Additionally, a comprehensive tutorial on setting up a private Ethereum network can be found [here](https://geth.ethereum.org/docs/fundamentals/private-network). To customize the size of the TMD-TO table used by the miner, add a `dimension.txt` file in the same folder where the `geth` executable is, which contains two numbers: table width and table height.

## Genesis block

The file that defines genesis block for the private network that uses the new consensus protocol can be found [here](./consensus/misanu/genesis/genesis.json). The `tableSize` parameter defines the difficulty of the consensus, while `miniPowDiff` defines the difficulty of the mini PoW used in the protocol.

## License

The go-ethereum library (i.e., all code outside of the `cmd` directory) is licensed under the [GNU Lesser General Public License v3.0](https://www.gnu.org/licenses/lgpl-3.0.en.html), as included in the `COPYING.LESSER` file in our repository.

The go-ethereum binaries (i.e., all code inside the `cmd` directory) are licensed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html), as included in the `COPYING` file in our repository.
