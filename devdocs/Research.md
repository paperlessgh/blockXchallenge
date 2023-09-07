# Requirements

A smart contract system that allows individuals to challenge each other on random topics. A challenge pool comes with a topic, monetary commitment value and a maturity time. Anyone can initiate a challenge pool and anyone can join a challenge pool as long as they like the terms and conditions on the pool. A pool has a limit of maximum number of people who can join. All these are abstract, and example could be a challenge pool that is initialized on the correct score outcome of an upcoming football match.

The initiator will initiate the pool, stake a certain amount on their predicted outcome. Anyone can later join, stake the same amount on their predicted outcome as well. If the match is between say Manchester and liverpool. Pool creator A initializes a pool with 1 eth and score prediction of 1-1. Another person B comes along to the pool and is interested in the terms of the pool. So this person also stakes 1 eth and gives their score prediction of 2-1. Before the joining deadline on the pool, anyone can join until the pool joining limit is reached, that is the maximum number of people who can join the pool.

Once the pool matures, if there are no winners, all participants gets back their stake. If there are winners, they get back their stake plus the stake of losers are equally shared among the winners. Consequently, if everyone wins then they just get back their stake.

## Functional Requirements

1. Users should be able to register a challenge topic.
2. Users should be able to register a challenge pool.
3. Users should be able to join a challenge pool.
4. Users should be able to see ongoing challenges.
5. Users should be able to filter challenges by various means;
    1. Filter by challenge topic
    2. Filter by maturity time
    3. Filter by status (open, locked, stale, closed)
    4. Filter by stake amount
    5. Filter by number of participants
        1. max participants > number of participants (not full)
        2. max participants == number of participants (full)
6. Users should be able to invite other users to join their pool.
7. Users should be able to connect their wallets and participate.
8. Users should be able to register for alerts/notifications.
9. Users should be able to chat with each other.

## User Interface Descriptions

The user interface should be more social and make users feel like they are not alone when browsing the site. For example show a pop up when a new pool is created, some ui indicator, share invite links to pools. These little effects will give the social feeling of participation. However, the absolutely important pages are as follows;

  

1. Activity/Landing Page
2. Challenge Topics Lists Page
3. Challenge Topic Detail Page
4. Create Challenge Topic Flow
5. Challenge Pool Lists Page
6. Challenge Pool Detail Page
7. Create Challenge Pool Flow
8. Join Challenge Pool Flow

  

For all the pages both desktop and mobile screen sizes should be considered.

### Activity / Landing Page

This page should be a unified interface from which users can access other parts of the applications. Divided into sections it could have a small section for ongoing challenges whether open or locked, etc ... It could have a section that continually updates with new challenges created and a section continually updating with closed challenges. It would also have buttons to create challenge pools, topics, and join a pool straight away.

### Challenge Topics List Page

A page where you can see all the challenge topics and interact with them. Interaction could be creating a topic. clicking a topic to see more details about it, etc...

### Challenge Topic Detail Page

From this page a user should see more details about a particular challenge topic, be able to create a challenge pool, etc ...

### Create Challenge Topic Flow

This flow should guide the user to creating a challenge topic. This is a more daunting task for now since it involves the creation of an evaluator smart contract for the pool topic.

### Challenge Pool List Page

This page will show challenge pools, under various interesting filters. For example, open, locked, stale, closed etc ... User would also be able to interact with the pools like joining a pool, clicking to see pool details, creating a new pool ...

### Challenge Pool Detail page

This page will show details of a pool, allow user to join or create similar pool etc ...

### Create Challenge Pool Flow

This flow should guide the user to creating challenge pool, one main functionality of the application is to be able to create pools by any user at all.

#### Steps

1. User will set the parameters
    1. Which type of pool
    2. Their prediction
    3. Maturity time
    4. Their stake
2. A popup / page to show final parameters for user's confirmation
3. Wallet authentication
4. Loader waiting for pool creation.
5. Redirect to new pool detail page.

### Join Challenge Pool Flow

This flow should guide the user to join a challenge pool. shouldn't be much different from creating a challenge pool.

#### Steps

1. User will set the parameters
    1. Their prediction
        1. For joining a pool the stake and maturity time is predetermined
        2. in the pool already since the pool has been initialized.
2. A popup / page to show final parameters for user's confirmation
3. Wallet authentication
4. Loader waiting for pool creation.
5. Redirect to pool detail page.

## Non-Functional Requirements

This system offers a platform for others to deploy challenge topics from which challenge pools can be created. It is expected that the number of challenge pools active at any given time will only keep increasing. It also handles the generic logic of closing challenge pools and distributing rewards securely. As such it is obvious that it must be able to satisfy certain non-functional constraints, as follows;

1. Should be able to handle high transaction volume.
2. Most computations should be moved off-chain as possible.
3. Closing of pools and reward distribution should be automated.
    1. users don't have to monitor and close their pools.
    2. users don't have to initiate withdrawal of their funds.
4. Simplicity is key, nothing complex in a smart contract environment.
5. A migration scheme must be employed from the beginning.
6. Security!!!

# Research

### How would the system evaluate winners & losers?

Users are challenging each other about real world events, hence for the system to be able to evaluate the outcome of these challenges it must have access to real world happenings.

These are smart contract systems and hence do not have access to real world events by default. In order to evaluate the outcome of challenges, oracles are needed to determine tell the smart contracts about real world events. A reliable choice to go with is chainlink oracles.

#### Chainlink Oracles

*   [https://docs.chain.link/data-feeds](https://docs.chain.link/data-feeds)
*   [https://docs.chain.link/getting-started/conceptual-overview](https://docs.chain.link/getting-started/conceptual-overview)
*   

### How would the system automate closing challenge pools?

Since there might be a pool closing event every block, it is necessary to automatically trigger and endpoint on the smart contract to check and close ripe pools. This is also essential to the whole system since pools are time bound and it will be fair to participants to respect that. A reliable choice to go with is chain link automation.

#### Chainlink Automation

*   [https://chain.link/automation](https://chain.link/automation)
*   [https://chain.link/education-hub/smart-contract-automation](https://chain.link/education-hub/smart-contract-automation)
*   [https://docs.chain.link/chainlink-automation/introduction](https://docs.chain.link/chainlink-automation/introduction)
*   [https://docs.chain.link/chainlink-automation/job-scheduler](https://docs.chain.link/chainlink-automation/job-scheduler)
*   [https://docs.chain.link/chainlink-automation/compatible-contracts](https://docs.chain.link/chainlink-automation/compatible-contracts)
*   [https://docs.chain.link/chainlink-automation/overview](https://docs.chain.link/chainlink-automation/overview)

  

### Which chain is appropriate?

# Components

## Smart Contracts

  

## Smart Contract Oracles

  

## Smart Contract Automation

  

## Subgraphs

  

## Web Application

# Implementation

