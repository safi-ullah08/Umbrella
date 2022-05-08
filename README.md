# Umbrella (A cross chain NFT protocol ) 

## Introduction

Cross chain **interoperability** for NFTs is an important problem that needs addressing. This solution is an alternative from the cross chain bridge approach. The goal is to deploy contracts across multiple chains. These contracts will be referred to as rainDrops. Each rainDrop will have other siblings on other blockchains(EVM compliant for now). 

Each rainDrop will share a singleton state. This state will be updated by the Orcal on a new event being triggered. All the other rainDrops will then  receive this update by the dispatcher from a hot-wallet (a wallet that lives on the server).

The Dispatcher will either make transactions or keep them in the Vault for later depending on network traffic or gas fee.

The Vault will keep all the transaction data until the dispatcher is ready to release them 


## Why

One immediate use case for this are games on the blockchain. This allows for games to communicate cross-chain. Game devs can just use the APIs we will provide (in the future) and build their games and not worry about integrating multiple blockchains. This can also allow users the freedom to earn cross chain.


## Architecture

  1. Smart contracts(ERC-721s,ERC-721A and ERC-1155s)/ rainDrops that will deployed on testnets (Mumbai (Polygon), Rinkeby(Ethereum) and Fuji(Avalanche))
  2. Orcal (Probably either a Node.js or Rust App) that will listen to changes on these smart contracts
  3. Dispatcher will dispatch transactions when network fees are low on all network 
  4. Vault will hold updates for "SYNCED'' smart contracts until the dispatcher is ready


## Arena (Future Goals)
  A framework of APIs that allows for game developers to focus on building games and all blockchain and in game economics are handled by Arena 

