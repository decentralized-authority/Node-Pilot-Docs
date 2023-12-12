---
description: >-
  This information is for educational purposes only and should not be regarded
  as advise of any kind.
---

# Pocket

## FAQ

_All this information can be found in the_ [_Pocket Docs_](https://docs.pokt.network) _or other publicly available resources._

### How much POKT is required to run a Pocket node?

15,000+ POKT is required. It is important that you always stake a little more than the minimum (15,100 POKT is recommended) to [account for small burns](./#will-my-node-be-slashed-for-downtime).

### What is the current POKT token supply?

{% hint style="info" %}
NOTE: The sources below are in uPOKT. Move the decimal forward 6 places to get the POKT amount. [Learn more here](https://docs.pokt.network/home/integrations/pokt-accounts-and-transactions#pokt-and-upokt).
{% endhint %}

1. NOTE: These&#x20;
2. Total supply of POKT: [https://supply.research.pokt.network:8192/total](https://supply.research.pokt.network:8192/total)
3. Circulating supply of POKT: [https://supply.research.pokt.network:8192/circulating](https://supply.research.pokt.network:8192/circulating)



### How does a Pocket node generate rewards?

Crypto applications that need to connect to networks like Ethereum, Harmony, Polygon, etc. use Pocket to connect to blockchains in a reliable, decentralized manner. When a Pocket node is connected to chain node like Ethereum, it is able to connect applications to Ethereum and generate rewards for providing a service.

This is why Pocket nodes **MUST ALWAYS** be connected to chain nodes to generate rewards. Pocket nodes do not generate rewards on their own.

### How much rewards do Pocket nodes produce?

Your Pocket nodes generate reward when the Pocket Network pseudorandomly pairs your Pocket nodes with application access to a chain you support. These sessions last about an hour and can vary in reward amount, depending on how many requests that applications sends.

For a quick look the historical reward averages per chain, see the [Rewards page on POKTscan](https://www.poktscan.com/public/explore).

![Adjust the Date Range to research reward averages over longer periods of time.](<../../../.gitbook/assets/image (39).png>)

For info on how Pocket's reward economics work, see [Pocket's Pricing and Economics](https://docs.pokt.network/home/resources/faq/pricing-and-economics).

{% hint style="warning" %}
NOTE: Though the daily "average" is represented in POKTscan, in reality node can go for long periods of time before being&#x20;
{% endhint %}

### Will I receive POKT rewards immediately?

The Pocket Network will pay a node for it's work in serving an application a few hours after [that session](./#how-much-rewards-do-pocket-nodes-produce) has concluded. So rewards for a session are paid out quickly if a node remains online a few hours after a session.\
\
**HOWEVER**, it may take days, or even a week+, for a node to see significant rewards. This is because Pocket has many large applications that provide the reward for a good portion of the network. It can take time for your nodes to be pseudorandomly assigned a session with a large application.

This means nodes are more likely to have many low reward days before having a high reward day. Since day to day rewards can vary, it's best to consider your averages over a few week time span and not expect an average reward each day.

### How much POKT is required to run a Pocket node?

15,000+ POKT is required. It is important that you always stake a little more than the minimum **(15,100 POKT is recommended)** to [account for small burns](./#will-my-node-be-slashed-for-downtime).

### Does staking more POKT on a node increase rewards?

No. The Pocket Network does not favor rewards depending on the size of the stake (unless you are a [Validator](./#what-is-the-difference-between-a-servicer-and-validator)).\
\
Because of this, it is more profitable to deploy more nodes than to have one node with significant stake.

### What is the difference between a Servicer and Validator?

A Pocket node can either act as a Servicer or a Validator.\
\
Servicers are the vast major of POKT nodes. They generate rewards for serving RPC requests. Validators are the top 1000 staked nodes. They generate rewards from serving RPC requests + they get some extra reward for being a block producer on the Pocket Network.\
\
The block producing reward that Validators receive is considered minimal compared to the rewards received for serving RPC requests. Because of this, it is generally understood that running more Servicers is more valuable than staking more POKT on a single node to be a Validator.\
\
Learn more about the difference between Servicers and Validators from the [original proposal](https://forum.pokt.network/t/pip-7-consensus-rule-change-validator-servicer-split-validator-consolidation/1272).

### Will my node be slashed for downtime? <a href="#will-my-node-be-slashed-for-downtime" id="will-my-node-be-slashed-for-downtime"></a>

There are negligible burns at this stage of the network, determined by the [SlashFractionDowntime](https://docs.pokt.network/home/resources/references/protocol-parameters#slashfractiondowntime) parameter. As the network matures, the rate will probably be increased to push for better service.

Is there a lock up periods?

Pocket does not have a lock-up period for new nodes. The moment you stake a node, it is ready to support applications and generate rewards.\
\
However, if you chose to unstake a node, then there is a 21 day unstaking period. This is a safety measure to create node stability and prevent nodes from jumping on and off the network. After the 21 day period, the unstaked POKT.

### How do I run a node?

There are four options:

1. Deploy your own node from scratch using the [Pocket Docs](https://docs.pokt.network/home/paths/node-runner) (advanced users)
2. Run your own node with [Node Pilot](https://nodepilot.tech) (user-friendly)
3. [Give a 3rd party service](https://forum.pokt.network/t/recommended-node-hosting-services/366) your POKT and run a node for you (user-friendly).
4. Give a 3rd party pooling service your POKT to create shared nodes. Learn more at the [POKTPool Discord](https://discord.gg/sEhx6dgDtE).

### Are their other ways to stake POKT for rewards that do not require running a node?

The Pocket blockchain only rewards those that run nodes and serve application.

[The Pocket Foundation is building wPOKT](https://wrapped.pokt.network), an ERC-20 token on Ethereum that will have reward mechanics for those not operating nodes.

### How do I acquire POKT for my node?

We can only point you to what the [Pocket Foundation has posted](https://forum.pokt.network/t/secondary-markets-for-pokt/629). If you have any further questions regarding acquiring POKT, please direct your questions to the Official Pocket [Discord](https://discord.gg/MtRp4BE) or [Telegram](https://t.me/POKTnetwork).



###
