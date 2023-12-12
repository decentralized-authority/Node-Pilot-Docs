# Select Chains

Select the chains you would want activated on Community Chains. You can activate new chains anytime.

<figure><img src="../.gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

## Update Your POKT Node's chains.json

After you have selected your chains, you will need to update your chains.json with the CC endpoints.

{% hint style="warning" %}
It is recommended that you always backup the original files before editing.\
\
PLEASE BACKUP A COPY OF YOUR `chains.json` BEFORE PROCEEDING.\


_**Node Pilot Users**_\
\
BACKUP A COPY OF YOUR `~/.node-pilot/config` FOLDER BEFORE PROCEEDING.
{% endhint %}

To get the CC endpoints for your chains.json, you can either:

1. Copy each chain's endpoint with the Copy icon
2. Download a new chains.json with the Download icon

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

After you have updated or replaced your chains.json, restart you POKT node.

{% hint style="danger" %}
### _Node Pilot Users_

DO **NOT** EDIT THE `chains.json` LOCATED AT:\
\~`/.node-pilot/config/chains.json`\
\
ONLY EDIT THE `chains.json` LOCATED INSIDE OF YOUR POKT NODE'S FOLDER:\
`~/.node-pilot/config/nodes/pokt-000/config/chains.json`
{% endhint %}

## Update Stake

If you are adding new chains to your POKT nodes, you will need to do an new stake transaction to add those new chains to your stake.

Below is POKT staking command.

```
pocket nodes stake custodial <relay_chains> mainnet 10000 true
```

To earn more about the POKT's staking command: [Click here](https://docs.pokt.network/node/setup/#stake-the-node) (POKT's official documentation)

### _Node Pilot Users_

Once you have updated the chains.json and done a Full Restart, wait until your POKT node has a status of "Running", and then click "Restake Node" to send a new stake transaction.

![](<../.gitbook/assets/image (37).png>)

After a block has passed, then you can verify that your node is staked to all the right chains by checking the "Chains" section in Validator Info.

<figure><img src="../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>
