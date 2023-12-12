# POKT Shared Wallet

The Shared Wallet is a way for CC to automate payments for users. The private key is shared with CC so it can submit payment transactions on the user's behalf. All CC payments are given invoiced which can be learned about [here](invoices.md).

The Shared Wallet is also how users can change their endpoint from "Disabled" to "Enabled" by sending POKT to the shared wallet, but before any payments are sent, the user needs to backup their private key.

## Backup Your Private Key

Click the eye icon next to your wallet address to view the private key.

![](<../.gitbook/assets/image (48).png>)

Backup that private key to a safe source. If you ever want to discontinue using CC you will need the private key to retrieve your funds.

{% hint style="warning" %}
The user is the owner and authorized custodian of the Shared Wallet. The user is solely responsible for the wallet and it's funds. You must back up your private key.
{% endhint %}

## Enable Your Endpoints

Once your private key is backed up, you can enable your endpoints by adding POKT to your Shared Wallet.

Follow the Portal instructions to enable your endpoint:

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

In this case, at least **50 POKT** per node is required for the endpoint to be active.

{% hint style="info" %}
_**EXAMPLE:**_ If you have 10 nodes, then 50 POKT per node would mean your endpoints will be disabled if the balance goes bellow **500 POKT**.

499 POKT = Status: <mark style="color:red;">**Disabled**</mark>

501 POKT = Status: <mark style="color:green;">**Enabled**</mark>
{% endhint %}

Because CC automates payments, you always need to make sure you have plenty of POKT in your wallet to pay the CC fees and keep your endpoints enabled. This is why CC recommends 100 POKT per node to start off with, but you can send more funds if you desire.

The greater the buffer, the longer you can use CC without needing to top off your Shared Wallet.

{% hint style="info" %}
_PRO TIP: If you add more POKT nodes to CC, then you will need to also make sure you add more POKT to your Shared Wallet._
{% endhint %}

