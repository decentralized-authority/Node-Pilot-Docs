# Deploy Pocket Validator

## Create a Pocket Node

{% hint style="danger" %}
**ATTENTION**: Before you deploy Pocket Validators, you must FIRST deploy all the nodes for all the chains you want your validator to support.
{% endhint %}

Click "+" to add a new validator node.

![](<../../../.gitbook/assets/Main add validator.PNG>)

From here, Pocket Validator nodes can be set up in 4 steps:

1. Select configurations _(See our_ [hardware-recommendations.md](../../hardware-recommendations.md "mention") _for best resource delegation)_
2. Generate password
3. Select chains to be supported by this validator
4. _(optional)_ Add custom seed nodes

![](<../../../.gitbook/assets/validator settings.png>)

Then click "Create Pocket Node" and wait for the node to deploy.

## Send POKT and Stake

{% hint style="danger" %}
Ensure that your Poket Node is fully synced before these next steps. You can ensure your node is fully synced by checking the block height at [POKTscan](https://poktscan.com).
{% endhint %}

The next step is to send POKT to the address created by that node.\
\
Send at least **15,051 POKT** to the Wallet Address.

{% hint style="info" %}
You can send Testnet POKT to a Testnet Validator from [Pocket's Testnet Faucet](https://faucet.pokt.network/).
{% endhint %}

![](<../../../.gitbook/assets/validator wallet.png>)

Once the POKT has been received, your balance will reflect the amount sent after the current block is confirmed (can take 15+ minutes).

{% hint style="warning" %}
Only 1 POKT will remain unstaked once you press "Stake Validator". Be sure to only send the amount of POKT you wish stake on your validator.
{% endhint %}

Click "Start Validator" to then start the staking process. The automation can take 30+ seconds to complete.

{% hint style="info" %}
Here is an example of what you will see in the Node Output after to know your validation transaction was successful sent to the network. If you see something like this then just wait:\
\
`{`

`"logs": null,`\
`"txhash": "E4F541B26B1A6928E7EC08A461E0764A901DE6C2F361CA4AC2E378AEB3A7BA83" }` \
`}`
{% endhint %}

Once the transaction is sent, it can take 15+ minutes for the next block to process on the Pocket blockchain. This means you will likely have to wait 15+ minutes before your validator will be active.

### Backup Your Private Key

After creating a Validator, it is important to make sure you backup your private key to another source.

![](<../../../.gitbook/assets/image (21).png>)
