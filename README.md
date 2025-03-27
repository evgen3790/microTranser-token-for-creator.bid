
__Overview__
__This program automatically buys a specified token created on the Creator.bid platform at regular intervals. It helps tokens remain at the top of the bump order list on Creator.bid by generating frequent, small transactions. Even if a token has migrated to a DEX like Uniswap, the program will still recognize and interact with it. The program is designed to simulate a live market, which improves visibility and engagement for tokens.__

Features
Automatic purchase of specified tokens at set intervals.

Supports tokens created on Creator.bid, including those migrated to DEXs.

Configurable purchase frequency and amount.

Logs transaction details, including transaction hash and purchase amount.

Every 10th transaction automatically deducts $1 for program usage.

Prerequisites
Before using the program, ensure you have the following:

A WebSocket (WSS) node URL for Ethereum blockchain transactions.

A valid agent key from Creator.bid.

The private key of the wallet to be used for making purchases.

The amount of ETH to swap for token purchases.

Configuration
The program reads configuration details from the config.json file. Below is an example of the file structure:

json
Копировать
Редактировать
{
    "node": [
        "YOUR_NODE"
    ],
    "agent_key": "YOUR_AGENT_KEY",
    "private_key": "YOUR_PRIVATE_KEY",
    "eth_to_swap": "0.0000001",
    "wait": 30
}
Configuration Details
node:

Description: A list of Ethereum nodes (WSS endpoint). The node is necessary to facilitate transactions.

Example: "wss://your-ethereum-node-url"

Note: Make sure you provide a valid WebSocket URL for connecting to the Ethereum network.

agent_key:

Description: The agent key from your token's Creator.bid page. You can obtain it by visiting the link:
https://creator.bid/agents/<AGENT_KEY>.

Example: "67b3a05779391e7456ec766b"

Note: Replace <AGENT_KEY> with your actual agent key.

private_key:

Description: The private key of the wallet from which token purchases will be made.

Example: "your_private_key_here"

Note: Do not include the 0x prefix.

eth_to_swap:

Description: The amount of ETH to use for purchasing the token in each transaction.

Example: "0.0000001"

Note: Specify the amount of ETH you wish to swap for each purchase.

wait:

Description: The time in seconds to wait between each token purchase.

Example: "30"

Note: The minimum wait time is 30 seconds, as per the Creator.bid service limits. You can set longer intervals (e.g., 500 seconds) if needed.

How to Use
Prepare the Configuration File
Edit the config.json file with your own values for the node URL, agent key, private key, amount of ETH to swap, and wait time between transactions.

Run the Program
Place the config.json file and the microTranser.exe executable in the same directory. To start the program, simply run the microTranser.exe file. This will open a console window that logs the following:

Timestamp of each purchase.

The amount of ETH spent on each token purchase.

The transaction hash for each transaction.

Program Operation
The program will purchase the specified token at regular intervals based on the values set in config.json. The purchases will continue until you stop the program. Each 10th transaction will trigger an automatic $1 fee deduction for program usage.

Transaction Logs
The console will display detailed logs of the transaction history, including:

Purchase time

Token purchase amount

Transaction hash (with a link to the transaction in the explorer)

Fee Structure
Every 10th transaction will trigger an automatic $1 fee for using the program. This fee is deducted from the balance of the wallet executing the transactions. The fee is charged once every 10 purchases.

Example Log Output
bash
Копировать
Редактировать
[2025-03-27 12:34:01] - Purchase: 0.0000001 ETH for Token TBUSTER
[2025-03-27 12:34:31] - Purchase: 0.0000001 ETH for Token TBUSTER
[2025-03-27 12:35:01] - Purchase: 0.0000001 ETH for Token TBUSTER
[2025-03-27 12:35:31] - Transaction Hash: [Link to Explorer]
...
[2025-03-27 12:40:01] - Transaction fee of $1 has been deducted after 10 purchases.
Important Notes
Security: Ensure that you keep your private key secure and never share it with others. The program interacts directly with your wallet and can perform transactions on your behalf.

Service Limitations: The program respects the 30-second minimum delay between purchases, as required by Creator.bid.

Node Connection: Ensure that your Ethereum node is accessible and operational to facilitate transactions.

License
This program is licensed under the MIT License. See the LICENSE file for more information.
