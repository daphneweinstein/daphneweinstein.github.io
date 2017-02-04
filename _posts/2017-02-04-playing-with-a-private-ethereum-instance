---
layout: post
title:  "Playing With A Private Ethereum Instance"
date:   2017-02-04 04:05:04 -0400
categories: decentralization
---
This post isn't particularly original, but I wanted to put out my experience of the easiest way to instantiate a private version of Ethereum on which to experiment. With Casper now on the horizon, Ethereum is looking to be the most promising network for some time. There is still a somewhat high barrier to entry into the network. What I show here took me a while to figure out and I hope it might help others. 

After installing the [Go-Ethereum] [geth] (geth) interface to the Ethereum network. Once the geth console was installed, I instantiated an instance of the private network with this command: 

geth --dev --ipcpath ~/Library/Ethereum/geth.ipc

It is possible to attach a clean console that will not have all of the mining log output with this command (for clarity while you are scripting):

geth --dev attach

To begin to use the test network, you will need to instantiate accounts that can interact with each other:

personal.newAccount('masterpass')

To mine currency on an account:

miner.setEtherbase(eth.accounts[1])
miner.start()
miner.stop()

Now that the accounts are set up and loaded with currency, it is possible to begin loading contracts and transacting with them. An online compiler exists at: 

https://ethereum.github.io/browser-solidity/#version=soljson-v0.4.4

To load a compiled contract onto the network with geth, it is necessary to unlock the account that will transmit the contract to the network to be mined:

personal.unlockAccount(web3.eth.accounts[1], "masterpass")
loadScript("mycontract.js")

To call the contract, one can use the commands specified in the code. In this case, purchdata is a function I specify. 

personal.unlockAccount(web3.eth.accounts[2], "masterpass")
purchdata.bid.sendTransaction(50, {from: eth.accounts[2]})

This is the simplest and safest way of playing with contracts in Ethereum.

[geth]: https://github.com/ethereum/go-ethereum
