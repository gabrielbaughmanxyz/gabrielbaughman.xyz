---
title: "Blockchains And How They Work"
date: 2021-11-23T18:50:15-05:00
author: "Gabriel"
description: "Blockchain is a technology that could be the future in decentralized computer networks."
tags: ["Tech", "Blockchain"]
ShowReadingTime: true
ShowToc: true
TocOpen: true
cover:
    image: "/posts/11-21/images/blockchain-cover.jpg" # image path/url
    alt: "blockchain cover image" # alt text
    caption: "" # display caption under cover
    relative: true # when using page bundles set this to true
    hidden: false # only hide on current single page
draft: false
---

# What Is A blockchain?
A blockchain is an online database that keeps a record of transactions of assets that is circulated throughout the nodes of a computer network. The blockchain can serve assets tangible or non-tangible. Blockchain technology has been around for a while. However, it wasn’t until 2009 that Satoshi Nakamoto released the whitepaper of [Bitcoin](https://bitcoin.org/bitcoin.pdf). It is a monetary system that utilized a public ledger of transactions on a blockchain. The idea that a decentralized monetary system that could be sent without people knowing who you are and validate any transaction made on the public ledger was revolutionary. Now, we have popular cryptocurrencies that utilize this technology and are improving on it such as Ethereum, Monero, Polkadot, and more.

# How Does It Work?
The blockchain holds a digital record of a database that is saved and maintained by various computers, or nodes. One of the unique things of the blockchain is how it saves data. The data it stores are in pieces that have sets of information, also called **blocks**, that have a unique hash (function that is used to generate a value) identifying itself, and the *hash* of the previous **block** forming a chain. Another feature of blockchain technology is that they are imputable; they cannot be overwritten or removed. This ensures that any data on the blockchain will not be removed or changed. This is a huge benefit if the technology is used as a system of money, or supply chains making sure products don’t go missing.

# How Are They Secured?
The first blockchains that came into existence, and some modern ones, are secured by PoW (Proof-of-Work). However, some of the more modern blockchains use PoS (Proof-of-Stake) and FBA (Federated Byzantine Agreement). The purpose of these systems is to reach a consensus that all validators in the network agree on new **blocks** that are made and the data that is in it is valid. The most important aspect of these systems is that there is no single entity that has say over the network and tries to validate malicious **blocks**. However, there are ways albeit expensive to launch an attack on these systems. 

## Proof-of-Work
PoW is used in Bitcoin and many others. It is a system that requires there to be *miners* that solve puzzles by using computing power. If a *miner* finds the solution, there is a **block reward** that is given to the *miner*. It is a race for all of the *miners* to find the solution by guessing randomly until the correct value is found. Although, there is development of [PoWU](https://eprint.iacr.org/2017/203.pdf) (Proof-of-Useful-Work), which instead of solving random puzzles *miners* will fold proteins or train artificial intelligence. This helps incentivize these *miners* to keep securing the network. Their computing power is determined by *hash rate*. However, there are some downsides to PoW. PoW is hard to scale economically, some PoW algorithms can have an ASIC (application-specific integrated circuit) made which companies can centralize the *hash rate* to entities with big pockets, and mining pools (collective of *miners* that combine *hash rate* to find **blocks**) with a lot of the network’s *hash rate* can go rogue and validate malicious **blocks** resulting in a 51% attack. A 51% attack is when an attacker controls the majority of the network and tries to validate **blocks** that has wrong data.

## Proof-of-Stake
PoS is a relatively new consensus mechanism that most cryptocurrencies are trying to implement. Instead of PoW, the *miners* can validate new **blocks** by how many of a coin/token a *miner* holds. Instead of a *miner* gaining power by *hash rate*, they gain power by holding more of a blockchains coin/token. This makes the energy consumption of PoS much lower to PoW, and scales much better than PoW. Instead of buying computing power hoping to find a **block**, PoS validators have to have a minimum number of coins to become one and people will “stake” their coins/tokens to validators. Validators are chosen at random to validate a **block**. Once a validator is chosen to validate a **block** and all other validators vote on the legitimacy of it, the **block** will be added to the chain and the validator will receive a reward and the people who staked their coin/token. This will end up with people who stake their coins having an APR on their assest. While the PoS system is susceptible in a 51% attack by having 51% of all of the network’s coin/token, it is not in the best interest to attack the network you hold the majority share in. 

## Federated Byzantine Agreement
The FBA is mainly used by the cryptocurrencies XRP (Ripple) and XLM (Stellar). The nodes in an FBA system do not have to be known, or verified in advanced. The nodes can choose what sources to trust when a consensus is made. The ability to join is easily available, and the control is decentralized. The number of nodes required to come to an agreement are called *quorums*. However, in the FBA it utilizes *quorum slices*, which is a subset of a *quorum*. These *quorum slices* can convince certain nodes to agree. Nodes in an FBA can rely on multiple *quorum slices*, and the decisions it makes can depend on external criteria. A person running a node can configure it to depend on a *quorum slice* if they believe it to be trustworthy. The FBA does not have **block rewards** like PoW and PoS. The FBA is very robust in the fact that individual nodes can trust whom they want, nodes can be apart of multiple *quorum slices*, and the ability to create a node is very low cost.

# The Future of Blockchain-Based Technology
Blockchain is being seen as a new way of supply chain tracking, voting systems, trading platforms, governance systems, and reward systems. The question is now what are companies and other organizations waiting for? Well, instead of bankers being liable for issues regarding money, developers that are maintaining a blockchain used for financial services can also be under the same situation. Not to mention, the power of blockchain can put centralized systems out of business, so it might not be in their best interest to incorporate blockchain. However, systems like Bitcoin, and newer ones like Ethereum showing the power of blockchain handling billions of dollars a day, the future looks bright for blockchain.

-----------------------------------
# Sources
* https://www.investopedia.com/terms/b/blockchain.asp
* https://www.fxempire.com/education/article/fundamental-differences-banking-system-private-blockchain-509525
* https://tokens-economy.gitbook.io/consensus/chain-based-pbft-and-bft-based-proof-of-stake/federated-byzantine-agreement
* https://www.investopedia.com/terms/p/proof-work.asp
* https://www.investopedia.com/terms/a/asic.asp
* https://www.investopedia.com/terms/p/proof-stake-pos.asp
* https://towardsdatascience.com/federated-byzantine-agreement-24ec57bf36e0
* https://tokens-economy.gitbook.io/consensus/chain-based-pbft-and-bft-based-proof-of-stake/federated-byzantine-agreement
* https://www.ibm.com/blogs/blockchain/2020/04/the-future-of-blockchain/
* https://eprint.iacr.org/2017/203.pdf

