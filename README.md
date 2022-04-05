# 🌊 Printer: Risk-Free Passive Income for NFT Owners
Print your NFTs and sell them in the metaverse!

## How to print your NFTs

The Printer contract is located at [0xF810d0268F6E7f2c893f0dd5Dd1eA6797db40cEC](https://etherscan.io/address/0xf810d0268f6e7f2c893f0dd5dd1ea6797db40cec).
Please interact with the contract from the Etherscan interface.

### 1. Deposit an NFT

Depositing means transferring an NFT to the Printer contract.
You must own the NFT in order to deposit it into the Printer contract.
The NFT must conform to the ERC-721 standard (e.g. CryptoPunks is not ERC-721).
Use the ERC-721's `safeTransferFrom` method and set `_to` to the address of the Printer contract.
The `onERC721Received` method of the Printer contract is invoked by the NFT contract when you use the `safeTransferFrom` method.
If you ever use the ERC-721's `transferFrom` method, you will lose the NFT forever.
`onERC721Received` is intended to be used by smart contracts, so you should never touch it.
When you deposit an NFT, the ownership is temporarily transferred to the Printer contract, but you can withdraw the NFT at any time.
Unlike [Fractional](https://fractional.art/), Printer allows you to trade an NFT for fungible tokens without losing ownership of it.

### 2. Print the NFT

The amount of prints is equal to the seconds that passed since the last deposit or the last print (whichever is later).
You can submit print transactions as many times as you like.
For example, if you deposit an NFT at 2020-01-01 00:00:00 and print it at 2020-01-01 00:00:10, you will receive 10 prints of the NFT.
If you print it again at 2020-01-01 00:00:30, you will receive another 20 prints, totaling 30 prints.
The longer you deposit, the more you can print.
It is impossible to accelerate the printing speed.
Prints are an ERC-20 token and the number of decimals is set to 18, meaning that a single print can be divided into 10<sup>18</sup> pieces.
The contract determines the depositing and printing time based on the block's timestamp.
In Fractional, the total supply of fractions is fixed, whereas in Printer the total supply of prints grows (almost) linearly over time like Dogecoin.

### 3. Withdraw the NFT

By withdrawing the NFT, you can retrieve the ownership of the NFT.
Withdrawing the NFT automatically prints the NFT.
Once you have withdrawn the NFT, you can no longer print the NFT.
If you want to print it, deposit it again.

Follow me on Twitter [@sharimot](https://twitter.com/sharimot) for up-to-date information on Printer!
