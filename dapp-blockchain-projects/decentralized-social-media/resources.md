# Resources for Decentralized Social Media

## 📺 Video Tutorials
- **[Full Stack Lens Protocol V2 Tutorial](https://www.youtube.com/watch?v=yYyT_2Gf2lI)** - Nader Dabit: Building modern social applications with Lens and React
- **[Build a Decentralized Social Media App with Farcaster](https://www.youtube.com/watch?v=R5xJpZf3Yg0)** - Alchemy: Implementing decentralized social features on Farcaster
- **[Decentralized Social Graph Architecture](https://www.youtube.com/watch?v=mD_3L0965wY)** - Lens Protocol: Deep dive into on-chain social relationships and state
- **[IPFS & Web3.Storage for Content](https://www.youtube.com/watch?v=fD0973XF700)** - Protocol Labs: Storing and retrieving social media assets via IPFS

## 📚 Written Tutorials
- **[Lens Protocol Developer Guide](https://docs.lens.xyz/)** - Official documentation for building apps on the Lens social graph
- **[Building on Farcaster with Neynar](https://docs.neynar.com/docs/getting-started)** - Comprehensive guide to social data indexing and wallet integration
- **[Understanding Decentralized Identity (DID)](https://ethereum.org/en/developers/docs/identity/)** - Ethereum Foundation: Guide to identity standards for social DApps
- **[IPFS Best Practices for Social Content](https://docs.ipfs.tech/concepts/usage-case-social-media/)** - Official documentation on handling media and metadata on IPFS

## 🔧 Tools & Libraries
- **[Lens Protocol](https://www.lens.xyz/)** - Composable social graph infrastructure for builders
- **[Farcaster Protocol](https://www.farcaster.xyz/)** - Decentralized social network protocol with focus on high-fidelity identity
- **[IPFS](https://ipfs.tech/)** - The industry standard for decentralized content and media storage
- **[Ceramic Network](https://ceramic.network/)** - Decentralized data network for managing dynamic, mutable social content
- **[Livepeer](https://livepeer.org/)** - Decentralized video infrastructure for social streaming and uploads

## 💻 GitHub Repositories
- **[Lens Protocol Hub](https://github.com/lens-protocol/core)** - The core smart contracts for the Lens social graph ecosystem
- **[Farcaster Monorepo](https://github.com/farcasterxyz/hub-monorepo)** - Core protocol and hub implementation for Farcaster nodes
- **[Nostr Protocol Specification](https://github.com/nostr-protocol/nips)** - The architectural standard for the Nostr decentralized social protocol
- **[CyberConnect Contracts](https://github.com/cyberconnecthq/cyberconnect-v3-core)** - Reference for multi-chain social graph smart contract logic

## 📖 Learning Resources
- **[Web3 Social Roadmap](https://roadmap.sh/blockchain)** - Visual path to mastering decentralized architecture and social graphs
- **[Designing Web3 Social Games & Apps](https://mirror.xyz/0x6854593E9E2a74cE24F75E0f39D54C2216694600)** - High-quality research on incentive design and decentralized retention
- **[ActivityPub Protocol Standard](https://www.w3.org/TR/activitypub/)** - W3C specification for federated social networking protocols

## 🚀 Sample Social Contract
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract SocialMedia is Ownable {
    IERC20 public rewardToken;

    struct Post {
        uint256 id;
        address author;
        string ipfsHash; // CID of content on IPFS
        uint256 timestamp;
        uint256 likes;
        bool isDeleted;
    }

    struct User {
        address wallet;
        string username;
        string ipfsProfile; // CID of profile metadata
        uint256 followersCount;
        uint256 followingCount;
    }

    mapping(uint256 => Post) public posts;
    mapping(address => User) public users;
    mapping(uint256 => mapping(address => bool)) public hasLiked;
    mapping(address => address[]) public followers;

    uint256 public postCount;

    event PostCreated(uint256 indexed postId, address indexed author, string contentHash);
    event PostLiked(uint256 indexed postId, address indexed liker);
    event UserCreated(address indexed userAddress, string username);

    constructor(address _rewardToken) Ownable(msg.sender) {
        rewardToken = IERC20(_rewardToken);
    }

    function createUser(string memory _username, string memory _ipfsProfile) public {
        require(bytes(_username).length > 0, "Username required");
        users[msg.sender] = User(msg.sender, _username, _ipfsProfile, 0, 0);
        emit UserCreated(msg.sender, _username);
    }

    function createPost(string memory _ipfsHash) public {
        uint256 currentId = postCount++;
        posts[currentId] = Post(currentId, msg.sender, _ipfsHash, block.timestamp, 0, false);
        
        emit PostCreated(currentId, msg.sender, _ipfsHash);
        
        // Reward author for creating content (if contract is funded)
        if(rewardToken.balanceOf(address(this)) >= 100e18) {
            rewardToken.transfer(msg.sender, 100e18);
        }
    }

    function likePost(uint256 _postId) public {
        require(!hasLiked[_postId][msg.sender], "Post already liked");
        require(_postId < postCount, "Post does not exist");

        posts[_postId].likes++;
        hasLiked[_postId][msg.sender] = true;

        emit PostLiked(_postId, msg.sender);
    }

    function followUser(address _userToFollow) public {
        require(_userToFollow != msg.sender, "Cannot follow yourself");
        users[msg.sender].followingCount++;
        users[_userToFollow].followersCount++;
        followers[_userToFollow].push(msg.sender);
    }
}
