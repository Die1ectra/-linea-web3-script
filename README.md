# linea-web3-script 
This script empowers Web3 users in Linea by leveraging blockchain technology for decentralized and transparent community interactions
from Blockchain import Blockchain
from datetime import datetime

class LineaWeb3Blockchain:
    def __init__(self):
        self.blockchain = Blockchain()
        self.create_genesis_block()

    def create_genesis_block(self):
        # Create the first block (genesis block)
        genesis_data = {"message": "Welcome to Linea Web3 Blockchain!", "timestamp": str(datetime.now())}
        self.blockchain.add_block(genesis_data)

    def add_message(self, message, sender):
        # Add a new block to the blockchain with user-generated message
        new_data = {"message": message, "sender": sender, "timestamp": str(datetime.now())}
        self.blockchain.add_block(new_data)

    def display_messages(self):
        # Display messages stored in the blockchain
        for block in self.blockchain.chain:
            print(f"{block.data['timestamp']} - {block.data['sender']}: {block.data['message']}")

# Example Usage
linea_web3_blockchain = LineaWeb3Blockchain()

# Add messages to the blockchain
linea_web3_blockchain.add_message("Excited to be part of Linea's Web3 journey!", "Alice")
linea_web3_blockchain.add_message("Let's build a decentralized future together.", "Bob")

# Display all messages in the blockchain
linea_web3_blockchain.display_messages()
