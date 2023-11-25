# NFT Lend & Borrow

## Overview

`nft_lend_borrow` is a Solana smart contract developed with Anchor, designed for creating a marketplace for lending and borrowing against NFTs. This contract enables users to create pools for NFT collections, offer loans, borrow against NFTs, and handle repayments and liquidations.

## Key Features

- **Create Pool:** Allows users to create lending pools for specific NFT collections.
- **Offer Loan:** Enables lenders to offer loans within a pool.
- **Withdraw Offer:** Lenders can withdraw their loan offers.
- **Borrow:** Borrowers can take loans against their NFTs.
- **Repay:** Enables borrowers to repay their loans.
- **Liquidate:** Handles the liquidation process for overdue loans.

## Installation

To use this smart contract:

1. Clone the repository:
    ```bash
    git clone https://github.com/thestriver/NFT-Lending-and-Borrowing
    ```

2. Navigate to the project directory:
    ```bash
    cd nft_lend_borrow
    ```

3. Install dependencies:
    ```bash
    anchor build
    ```

## Usage

### Deploying the Contract

Deploy the contract to the Solana Devnet network using Anchor:

```bash
anchor deploy --provider.cluster devnet
```

Make sure you edit Anchor.toml accordingly
```
[programs.localnet]
nft_lend_borrow = "<Address>"

[programs.devnet]
nft_lend_borrow = "<Address>"

[provider]
cluster = "Devnet"
```

### Interacting with the Contract
Use the provided client script or integrate with your frontend application.

## Contract Functions
- create_pool(collection_id: Pubkey, duration: i64): Create a new lending pool.
- offer_loan(offer_amount: u64): Offer a loan in a pool.
- withdraw_offer(minimum_balance_for_rent_exemption: u64): Withdraw a loan offer.
- borrow(minimum_balance_for_rent_exemption: u64): Borrow against an NFT.
- repay(): Repay an outstanding loan.
- liquidate(): Liquidate an overdue loan.

### Testing
Run the test suite to ensure everything is working correctly:

```bash
anchor test
```