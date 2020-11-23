# LiquidStakeDAO

Liquid (transferable) stakes for HEX with optional shared reward pool.
Basically this allows you to stake HEX with the contract and get a LiquidStake
NFT for that. The nice thing is that the Token ID of this NFT equals the HEX
Stake ID.

The code for this is minimal and can fit on a single screen:
[LiquidStake.sol](./contracts/LiquidStake.sol)

You can get a good understanding of this by reading the [test
case](./tests/test_integration.py#L85).

## Main Contract Goals

* No admin key
* Unstoppable, unpausable, no governance functionality
* Test suite
* Audited (post-launch by donations?)

## Benefits of LiquidStakes

* Can be gifted
* Can be inherited
* Can be moved in case your wallet got compromised
* Tradeable on secondary markets (not necessarily a benefit for HEX stakers?)
* Can be borrowed against (in theory)
* It's like a HEX bond and facilitates HEX yield curves by market pricing of
  short term stakes vs long term stakes
* Can be generally used in other DeFi protocols which will increase adoption
  and solidifies HEX market position via network effects (see Protocol Sink
  Thesis)

## Optional Rewards Pool

This contract can also be deployed with a Rewards pool. Users of the
LiquidStakeDAO (LSD) token could claim their portion of the fees generated by
the main contract.

## Optional Farming

In order to distribute the LSD token, this repository also includes an optional
farming contract: The system can have a fair launch with all LSD tokens
distributed to users of the protocol (no team allocation etc.). How is this
possible? By staking your LiquidStake NFT into the farming contract and get
rewarded with LSD. The amount decreases every month so the earlier adopters are
still able to get an advantage.

## Run tests

Run tests like this:

    brownie test --network mainnet-fork

## Deploy

**NOTE: THIS IS A PROTOTYPE AND BASICALLY A PROGRAMMING EXERCISE AND NOT MEANT
TO BE DEPLOYED.**

Deploy like this:

    brownie run scripts/deploy.py
