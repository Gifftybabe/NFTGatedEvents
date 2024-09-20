# NFT Gated Event Manager

## Overview
This project consists of a smart contract for managing events gated by NFT ownership. Users must own a specific NFT to register for events, which have limited capacities and a specified date. Additionally, this project includes a simple NFT contract that allows users to mint NFTs, which can serve as access tokens for gated events.

## Features
1. **NFT Minting:**
   - The `MyNFT` contract allows users to mint NFTs after paying a minting fee.
   - SVG images are used for the NFT art, which are encoded in Base64 format for storage.
   - Minting also generates a unique metadata URI using the token's SVG data.

2. **Event Management:**
   - The `NFTGatedEventManager` contract allows the creation and management of events that require ownership of a specific NFT for registration.
   - Events can be created by the owner of the contract and include a set date, maximum capacity, and an NFT requirement for entry.
   - Users can register for events if they meet the NFT ownership requirement and there is capacity available.

## Contracts
### 1. **Base64.sol**
A utility library for encoding bytes into Base64 strings, used for converting SVGs into a Base64-encoded format.

### 2. **MyNFT.sol**
This contract allows for:
   - Minting NFTs by paying a fixed fee.
   - Storing SVG data and converting it into Base64 format for the NFT image.
   - Updating the stored SVG data by the owner of the contract.
   - Withdrawing funds from the contract by the owner.

### 3. **NFTGatedEventManager.sol**
This contract enables:
   - Creating events that require a specific NFT for registration.
   - Registering users for events after verifying their NFT ownership.
   - Managing event details such as name, date, capacity, and active status.

## Functions
- **createEvent:** Allows the contract owner to create a new NFT-gated event.
- **registerForEvent:** Allows users to register for an event if they own the required NFT.
- **withdrawFunds:** Lets the contract owner withdraw all funds from the `MyNFT` contract.
- **updateSVG:** Allows the contract owner to update the SVG data for minted NFTs.

## Usage
1. Deploy the `MyNFT` contract with an initial SVG image.
2. Users can mint NFTs by sending the required mint price to the contract.
3. Deploy the `NFTGatedEventManager` contract and create events gated by the NFT minted earlier.
4. Users can register for events if they meet the NFT ownership requirement and the event has space available.
