# Resources for Token Staking Platform

## 📺 Video Tutorials
- **[Building a Staking Rewards DApp](https://www.youtube.com/watch?v=R_6y0sV4It8)** - EatTheBlocks: Comprehensive guide on implementing staking logic and frontend integration
- **[Synthetix Staking Rewards Explained](https://www.youtube.com/watch?v=6ZEp8fG_z9k)** - Smart Contract Programmer: In-depth breakdown of the industry-standard reward distribution algorithm
- **[Foundry Staking Contract Tutorial](https://www.youtube.com/watch?v=sas02qSFZ74)** - Cyfrin Updraft: Modern smart contract development using Foundry, including advanced testing patterns

## 📚 Written Tutorials
- **[Staking Rewards Algorithm Deep Dive](https://www.rareskills.io/post/staking-algorithm)** - RareSkills: Highly technical explanation of the math behind scalable DeFi reward systems
- **[How to Build a Staking DApp](https://docs.alchemy.com/docs/how-to-build-a-staking-dapp)** - Alchemy: Step-by-step walkthrough covering contract deployment and UI integration
- **[Time-Lock and Access Control Patterns](https://docs.openzeppelin.com/contracts/5.x/access-control)** - OpenZeppelin: Official documentation on securing contract functions with time-based logic

## 🔧 Tools & Libraries
- **[OpenZeppelin Contracts](https://docs.openzeppelin.com/contracts/5.x/)** - Standard library for secure ERC-20 tokens and reentrancy protection modules
- **[Foundry](https://book.getfoundry.sh/)** - High-speed Ethereum development framework essential for testing complex time-dependent staking logic
- **[Chainlink Data Feeds](https://docs.chain.link/data-feeds)** - Secure decentralized oracles for real-time price feeds used in APY and reward calculations

## 💻 GitHub Repositories
- **[Synthetix Staking Rewards](https://github.com/Synthetixio/synthetix/blob/develop/contracts/StakingRewards.sol)** - The original, battle-tested reference for most modern staking pool implementations
- **[Aave V3 Core](https://github.com/aave/aave-v3-core)** - Production-grade examples of incentive controllers and safety module staking
- **[Lido Liquid Staking](https://github.com/lidofinance/lido-dao)** - Reference for advanced liquid staking protocols and governance-controlled pools

## 📖 Learning Resources
- **[Proof of Stake & Staking Mechanics](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/)** - Ethereum Foundation: Official guide to consensus and protocol-level staking
- **[Smart Contract Security Best Practices](https://consensys.github.io/smart-contract-best-practices/)** - Essential patterns for securing user assets and avoiding common DeFi vulnerabilities

## 🚀 Sample Staking Contract
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
import "@openzeppelin/contracts/utils/ReentrancyGuard.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract StakingPlatform is ReentrancyGuard, Ownable {
    IERC20 public stakingToken;
    IERC20 public rewardToken;

    struct StakeInfo {
        uint256 amount;
        uint256 startTime;
        uint256 lockDuration;
        uint256 rewardDebt;
    }

    mapping(address => StakeInfo) public stakes;
    uint256 public rewardRate = 1e17; // 10% base representation
    uint256 public totalStaked;

    event Staked(address indexed user, uint256 amount, uint256 duration);
    event Unstaked(address indexed user, uint256 amount);
    event RewardsClaimed(address indexed user, uint256 amount);

    constructor(address _stakingToken, address _rewardToken) Ownable(msg.sender) {
        stakingToken = IERC20(_stakingToken);
        rewardToken = IERC20(_rewardToken);
    }

    function stake(uint256 _amount, uint256 _duration) public nonReentrant {
        require(_amount > 0, "Amount must be > 0");
        require(_duration >= 7 days, "Minimum 7 days lock");

        stakingToken.transferFrom(msg.sender, address(this), _amount);

        stakes[msg.sender] = StakeInfo({
            amount: _amount,
            startTime: block.timestamp,
            lockDuration: _duration,
            rewardDebt: 0
        });

        totalStaked += _amount;
        emit Staked(msg.sender, _amount, _duration);
    }

    function calculateRewards(address _user) public view returns (uint256) {
        StakeInfo memory stakeInfo = stakes[_user];
        if (stakeInfo.amount == 0) return 0;

        uint256 elapsed = block.timestamp - stakeInfo.startTime;
        uint256 rewards = (stakeInfo.amount * rewardRate * elapsed) / (365 days * 1e18);

        return rewards;
    }

    function claimRewards() public nonReentrant {
        uint256 rewards = calculateRewards(msg.sender);
        require(rewards > 0, "No rewards available");

        stakes[msg.sender].startTime = block.timestamp; // Reset timer for reward interval
        rewardToken.transfer(msg.sender, rewards);

        emit RewardsClaimed(msg.sender, rewards);
    }

    function unstake() public nonReentrant {
        StakeInfo memory stakeInfo = stakes[msg.sender];
        require(stakeInfo.amount > 0, "No stake found");
        require(
            block.timestamp >= stakeInfo.startTime + stakeInfo.lockDuration,
            "Stake is still locked"
        );

        uint256 amount = stakeInfo.amount;
        totalStaked -= amount;

        delete stakes[msg.sender];

        stakingToken.transfer(msg.sender, amount);
        emit Unstaked(msg.sender, amount);
    }
}
