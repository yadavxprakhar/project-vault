# Resources for Supply Chain Tracker

## 📺 Video Tutorials
- **[Build a Blockchain Supply Chain App](https://www.youtube.com/watch?v=zZgVAn-Pqo8)** - Dapp University: Comprehensive guide on tracking products with Solidity and React
- **[IoT & Blockchain for Supply Chain Tracking](https://www.youtube.com/watch?v=mG7SreVdY5I)** - Engineering University: Deep dive into hardware and ledger integration
- **[Smart Contracts for Logistics](https://www.youtube.com/watch?v=rX_Hps_p0Rk)** - EatTheBlocks: Building a supply chain tracking system with different actor roles
- **[Supply Chain Frontend Dashboard](https://www.youtube.com/watch?v=vV77m6u5Irs)** - JavaScript Mastery: Creating a modern dashboard for blockchain-based tracking data

## 📚 Written Tutorials
- **[Build a Supply Chain Tracker on Ethereum](https://www.freecodecamp.org/news/how-to-build-a-supply-chain-tracker-using-ethereum-solidity-and-react/)** - freeCodeCamp: Full stack guide using modern Solidity
- **[Supply Chain Management with Solidity](https://docs.alchemy.com/docs/how-to-build-a-supply-chain-smart-contract)** - Alchemy: Technical walkthrough of state transitions in tracking
- **[Integrating IoT and Blockchain](https://blog.logrocket.com/iot-blockchain-overview-use-cases/)** - LogRocket: Architecting systems for real-time sensor data on the ledger

## 🔧 Tools & Libraries
- **[Hyperledger Fabric](https://www.hyperledger.org/use/fabric)** - The enterprise-standard modular blockchain framework for supply chain
- **[Hardhat](https://hardhat.org/)** - Modern Ethereum development environment for testing and deploying tracking contracts
- **[ethers.js](https://docs.ethers.org/)** - Lightweight and secure library for interacting with blockchain tracking nodes
- **[Johnny-Five](http://johnny-five.io/)** - The JavaScript Robotics & IoT platform for integrating physical tracking hardware

## 💻 GitHub Repositories
- **[Hyperledger Fabric Samples](https://github.com/hyperledger/fabric-samples)** - Official enterprise-grade implementations including supply chain and asset transfer
- **[Blockchain Supply Chain Topic](https://github.com/topics/supply-chain-blockchain)** - Curated list of high-quality open-source supply chain tracking projects
- **[Solidity Tracking Reference](https://github.com/shubham-kumar-2000/Supply-Chain-Management-on-Blockchain)** - Well-structured repository for multi-stage tracking contracts

## 📖 Learning Resources
- **[GS1 Standards for Blockchain](https://www.gs1.org/standards/blockchain)** - Official global standards for identification and data exchange in supply chains
- **[Supply Chain Management 101](https://www.investopedia.com/terms/s/supplychainmanagement.asp)** - Essential industry terminology and workflow concepts
- **[Chainlink Functions (IoT Data)](https://docs.chain.link/chainlink-functions)** - How to pull off-chain sensor and logistics data into smart contracts

## 🚀 Sample Supply Chain Contract
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract SupplyChain {
    enum State { Created, Shipped, Delivered, Cancelled }

    struct Product {
        string id;
        string name;
        address owner;
        State state;
        uint256 lastUpdated;
        bool exists;
    }

    struct TrackingEvent {
        string location;
        uint256 timestamp;
        address recordedBy;
        string details;
    }

    mapping(string => Product) public products;
    mapping(string => TrackingEvent[]) public productHistory;

    event ProductStatusChanged(string indexed productId, State state, address actor);

    function createProduct(string memory _id, string memory _name) public {
        require(!products[_id].exists, "Product already exists");

        products[_id] = Product({
            id: _id,
            name: _name,
            owner: msg.sender,
            state: State.Created,
            lastUpdated: block.timestamp,
            exists: true
        });

        _recordEvent(_id, "Manufacturing Plant", "Product initialized in system");
        emit ProductStatusChanged(_id, State.Created, msg.sender);
    }

    function updateStatus(string memory _id, State _newState, string memory _loc, string memory _details) public {
        require(products[_id].exists, "Product not found");
        
        Product storage product = products[_id];
        product.state = _newState;
        product.lastUpdated = block.timestamp;
        product.owner = msg.sender;

        _recordEvent(_id, _loc, _details);
        emit ProductStatusChanged(_id, _newState, msg.sender);
    }

    function _recordEvent(string memory _id, string memory _loc, string memory _det) internal {
        productHistory[_id].push(TrackingEvent({
            location: _loc,
            timestamp: block.timestamp,
            recordedBy: msg.sender,
            details: _det
        }));
    }

    function getHistory(string memory _id) public view returns (TrackingEvent[] memory) {
        return productHistory[_id];
    }
}
