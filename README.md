# Decentralized Casino Smart Contract

This Solidity smart contract enables the creation of a decentralized casino on the Ethereum blockchain. Players can participate in a simple game where they stand a chance to double their wager based on a random outcome. The contract is designed to maintain transparency and fairness in the gaming process.

## Features

### Game Participation
- Allows users to participate in the game by sending a wager (in Wei) to the contract.

### Random Outcome Generation
- Utilizes Ethereum's block properties to generate a random outcome for the game.

### Winnings Distribution
- Players who win the game receive twice their wagered amount.

### Tracking Last Winners
- The contract keeps a record of the last three winners in the game.

## Functionalities

### playGame
- Players call this function to participate in the game.
- On the first call, the contract records the player's wager and sets a future block number for determining the game's outcome.
- On subsequent calls (after the specified block number), the game outcome is determined.
- The game uses a pseudo-random number generated from Ethereum's blockchain data to decide the win or loss.

### Automated Game Entry via receive Function
- The contract includes a `receive` function allowing it to accept incoming ETH transactions and automatically trigger the `playGame` function.

### Handling Winnings and Updating Winners
- If the player wins, the contract sends them twice the amount of their original wager.
- The contract updates the list of the last three winners after each game round.

## Getting Started

To interact with this contract:

1. Deploy the contract to an Ethereum blockchain environment (testnet or mainnet).
2. Send a transaction with ETH to the contract address to play the game.
3. Check the transaction's outcome and the list of recent winners after the required number of blocks have passed.

## Prerequisites

- Basic understanding of Ethereum transactions and smart contracts.
