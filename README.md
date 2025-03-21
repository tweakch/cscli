# cscli

## Goals
A cross-platform CLI for building and interacting with [Cardano](https://developers.cardano.org/) data structures using .NET cryptographic and serialisation primitives from [CardanoSharp](https://github.com/CardanoSharp/cardanosharp-wallet) (i.e. not just a wrapper over cardano-cli). 

It provides additional functionality on top of [cardano-cli](https://github.com/input-output-hk/cardano-node/blob/master/doc/reference/cardano-node-cli-reference.md/) to randomly generate [mnemonic phrases](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki), to [derive Hierarchical Deterministic (HD) wallet keys and addresses](https://github.com/bitcoin/bips/blob/master/bip-0044.mediawiki) based on the mnemonic and even building signed transactions including certificates + metadata with multi-asset support.

## Usage

```bash
cscli --help

> cscli v0.0.1
> A .NET Cross Platform Tool for generating Cardano keys, addresses and transactions.
> 
> USAGE: cscli (OPTION | COMMAND)
> 
> Available options:
>     -v, --version   Show the cscli version
>     -h, --help      Show this help text
> 
> Available commands:
>     wallethd mnemonic gen --size (9|12|15|18|21|24) --language (English|ChineseSimplified|ChineseTraditional|French|Italian|Japanese|Korean|Spanish|Czech|Portuguese)
>     (WIP) wallethd key payment derive --mnemonic ""$MNEMONIC"" --account-index ACCT_IX --address-index ADDR_IX --verification-key-file VKEY --signing-key-file SKEY --output-format (HEX|CBOR|BECH32|JSON)
>     (WIP) wallethd key stake derive --mnemonic ""$MNEMONIC"" --account-index ACCT_IX --address-index ADDR_IX --verification-key-file VKEY --signing-key-file SKEY --output-format (HEX|CBOR|BECH32|JSON)
>     (WIP) wallethd address payment derive --mnemonic ""$MNEMONIC"" --account-index ACCT_IX --address-index ADDR_IX --output-format (HEX|CBOR|BECH32|JSON)
>     (WIP) wallethd address stake derive --mnemonic ""$MNEMONIC"" --account-index ACCT_IX --address-index ADDR_IX --output-format (HEX|CBOR|BECH32|JSON)
```
### Generate Mnemonics
```bash
cscli wallethd mnemonic gen --size 24 --language English
```

### Derive Payment Key
```bash
cscli wallethd key payment derive --mnemonic "$mnemonic" --address-index 0
```

### Derive Payment Address
```bash
cscli wallethd address payment derive --mnemonic "$mnemonic" --address-index 0
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
cd Bin/Release/net5.0
./Cscli.ConsoleTool.exe --help
```
Directly running with `dotnet run`
```bash
cd Src/ConsoleTool
dotnet run --version
```

## Contributing
Please see [CONTRIBUTING.md](./CONTRIBUTING.md)