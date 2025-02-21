# Distributed Shopping Platform

This project implements a distributed shopping platform using gRPC for communication between clients (sellers and buyers) and a central market server. The system is designed to be deployed on multiple virtual machines hosted on Google Cloud.

## Key Components

### 1. Market (Central Platform)
- Serves as the central hub, acting as an intermediary between sellers and buyers.
- Maintains seller accounts, listings, transactions, reviews, and notifications.
- Runs on a Google Cloud VM with a publicly accessible IP address.

### 2. Seller (Client)
- Provides the ability to manage product listings and interact with the Market node.
- Each seller:
  - Registers with the Market.
  - Adds, updates, deletes, and views items.
  - Receives notifications from the Market.
  - Has a unique address (`ip:port`) where their notification server is hosted.
  - Generates and maintains a secure UUID, sent to the Market with each interaction.

### 3. Buyer (Client)
- Provides the ability to search for products and place orders.
- Each buyer:
  - Interacts with the Market to search, buy, and rate products.
  - Maintains a wish list to receive targeted notifications.
  - Has a unique address (`ip:port`) where their notification server is hosted.

## Deployment
- Deploy the Market node on a Google Cloud VM with a public IP.
- Deploy seller and buyer clients on separate machines, ensuring gRPC communication is correctly configured.

## License
This project is licensed under the MIT License.

