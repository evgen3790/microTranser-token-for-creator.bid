# **Token Buyer Program**

## **Overview**
This program automatically buys a specified token created on the **Creator.bid** platform at regular intervals. It helps tokens remain at the top of the **bump order list** on **Creator.bid** by generating frequent, small transactions. Even if a token has migrated to a DEX like Uniswap, the program will still recognize and interact with it. The program is designed to simulate a live market, which improves visibility and engagement for tokens.

## **Features**
- **Automatic** purchase of specified tokens at set intervals.
- Supports tokens created on **Creator.bid**, including those migrated to **DEXs**.
- **Configurable** purchase frequency and amount.
- Logs transaction details, including transaction hash and purchase amount.
- Every **10th transaction** automatically deducts **$1** for program usage.

## **Prerequisites**
Before using the program, ensure you have the following:
- A **WebSocket (WSS)** node URL for Ethereum blockchain transactions.
- A valid **agent key** from **Creator.bid**.
- The **private key** of the wallet to be used for making purchases.
- The amount of **ETH** to swap for token purchases.

## **Configuration**
The program reads configuration details from the `config.json` file. Below is an example of the file structure:

json
```
{
    "node": [
        "YOUR_NODE"
    ],
    "agent_key": "YOUR_AGENT_KEY",
    "private_key": "YOUR_PRIVATE_KEY",
    "eth_to_swap": "0.0000001",
    "wait": 30
}
```
