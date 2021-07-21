# cscli

## Goals
A cross-platform CLI for building and interacting with [Cardano](https://developers.cardano.org/) data structures using .NET cryptographic and serialisation primitives from [CardanoSharp](https://github.com/CardanoSharp/cardanosharp-wallet) (i.e. not just a wrapper over cardano-cli). 

It provides additional functionality on top of [cardano-cli](https://github.com/input-output-hk/cardano-node/blob/master/doc/reference/cardano-node-cli-reference.md/) to randomly generate [mnemonic phrases](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki), to [derive Hierarchical Deterministic (HD) wallet keys and addresses](https://github.com/bitcoin/bips/blob/master/bip-0044.mediawiki) based on the mnemonic and even building signed transactions including certificates + metadata with multi-asset support.

## Usage

```bash
cscli --help
> OUTPUT LINE 1  HERE
> OUTPUT LINE .. HERE
> OUTPUT LINE n  HERE
```
### Generate Mnemonics
```bash
cscli wallethd mnemonic generate --count 24
```
### Derive Payment Key
```bash
cscli wallethd key payment derive --mnemonic $mnemonic --address-index 0
```

### Derive Payment Address
```bash
cscli wallethd address payment derive --mnemonic $mnemonic --address-index 0
```
## Installation

### Pre-requisites
The [.NET 5 SDK](https://dotnet.microsoft.com/download/dotnet/5.0) is required to install the global tool or to build from the source directly.

### .NET Global Tool

```bash
dotnet install --global cscli
cscli --help
```

### From Source
Building and running compiled binary
```bash
cd Src/ConsoleTool
dotnet build -c Release
cd Bin/Release
./Cscli.ConsoleTool --help
```
Directly running with `dotnet run`
```bash
cd Src/ConsoleTool
dotnet run --help
```

## Contributing
Please see [CONTRIBUTING.md](./CONTRIBUTING.md)