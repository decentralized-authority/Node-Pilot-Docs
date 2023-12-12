# Errors from POKTscan

The [Pocket Portal](https://portal.pokt.network) is a tool run by the Pocket Foundation that allows applications to create accounts and get access relays on the Pocket Network. The Portal has an error API that can help node runner identify potential errors with their nodes.\
\
To see what errors the Portal might have in regards to your node, go to [POKTscan](https://www.poktscan.com/public/explore?tab=nodes), search for your node, and click eye on the right hand side to see your full node details. Scroll down to a section called "Errors" to see any errors from the Portal API.

{% hint style="warning" %}
NOTE: Many errors can be ignored as they have nothing to do with the performance of your node.
{% endhint %}

## Error FAQ

### Do I need to worry if there are errors with my node?

It depend on the error. Search for the error below to identify if it should be ignored or has relevance to your node.

### Does the Chain Check or Sync Check only happen when a node is in a session, or does the gateway ping all validators all the time?

Currently they run only when sessions are active; every 5 minutes. In the future they will run continuously and separately from the sessions.

### What is the difference between Chain Check and Sync Check?

* Sync check makes sure that the node is within a certain allowance of the oracles we check. For fast chains like Harmony, the allowance is longer than slower chains like Ethereum.
* Chain check ensures that the nodes are serving the correct chain ID.  It is an edge case, but it is possible to get a session full of nodes serving the wrong chain but agreeing on blockheight, and therefore passing the sync check.

## Relevant Errors



### `timeout of 4000ms exceeded`

![](https://lh5.googleusercontent.com/FpMqlKxEyBQJ\_jGBfu6k4-ajpP5RvCEoeG53-xaVNh3KUnC2CiHKtcRMZyjw5TewMDLwfVPIu-pzZDZP5a3YC33CLNfPaEATKQobERtjcqJnkvoHvOLLP5mv6lkFWPhnUT-3QY-7)

**Importance:** <mark style="color:red;background-color:red;">TAKE ACTION</mark>

**Meaning:**

* Apps are sending larger requests than what your node is setup for. Not serving these requests can mean less rewards.

**Possible Next Steps:**

Increase your RPC timout variable in `config.json` with the following steps:

1. Shut down Node Pilot (or just that Pocket node)
2. Edit `~/.node-pilot/config/nodes/[NODE-ID]/root/config/config.json`
   * (for non Node Pilot users, inside your node's folder: `/root/config/config.json`)
3. Change `"rpc_timeout":` from `3000` to `15000`
4. Save changes
5. Start Node Pilot (or start that Pocket node)



### `Server Timeout Handling Request`

![](https://lh4.googleusercontent.com/PJ\_p-uT\_9NVGMe7eBE-1vwI9w1T2ba4ba-JejKqume3zP\_SXZGJiVMk8dMkkB-zBVesyOsmysNGqPz62oTJ52ijDB8LzwDyuY0T1N1O2kuME7bUZ\_ChEtoTe35sdNTqwaS1-Hnm3)

**Importance:** <mark style="color:orange;background-color:orange;">WORTH MONITORING</mark>

**Meaning:**

* Your pocket node timed out
* Your data node timed out
* There was a blip in the internet service between the API and your pocket node
* The pocket node was under stress due to block/session rollover and was unable to handle the RPC

**Possible Next Steps:**

* Give your node [more hardware resources](../../edit-node-resources.md) so it can handle more stress.
* Change node location or service provider if the interent is unreliable.



### `OUT OF SYNC: current block height on chain 0021: 13646961 altruist block height: 13646961 nodes height: 13641317 sync allowance: 3`

![](https://lh4.googleusercontent.com/OK1lJxL46DD9IMquZT-ftCa0UhzDQuOat-c5GrlFSjQjxFiCGAVQEIk0hgybItt5ARkG-Orw94bi9XrruUTn7R157AqBzZuS823ch\_ssYGAOIgU9SYOFQRV22xl64c6ogZ8tTuxF)

**Importance:** <mark style="color:orange;background-color:orange;">WORTH MONITORING</mark>

**Meaning:**

* Your data node is more than the allowance out of sync.

**Possible Next Steps:**

Check that chain node's current block height against the block height of a trusted explorer. If you node is at the current block height, it may have gotten behind temporarily. If it is behind, then try any of the following.

* Restart that chain node
* Give your node [more hardware resources](../../edit-node-resources.md) in-case the node is too stressed.
* [Delete the chain data](broken-reference) and resync.



### `502 Bad Gateway`&#x20;

![](https://lh6.googleusercontent.com/KDa1Fz8gk2YK6ar7boUR5bpqj9QOOJvc63hkJl74SOfhpG1dpcsAEGit4RwjYTUfuASBfOo6pQbEfB6F\_fDaHMYC-Ls3ncZRFE2MZUn6NaM4bavA98xJJwFwBQ1C-ckWw8e8cqHw)

The load balancer in front of your node is unable to talk to the Pocket node due to the Pocket node timing out.

Same as [#server-timeout-handling-request](errors-from-poktscan.md#server-timeout-handling-request "mention")



### `certificate has expired` <a href="#docs-internal-guid-8aa678ee-7fff-c562-4793-4bdb0879d502" id="docs-internal-guid-8aa678ee-7fff-c562-4793-4bdb0879d502"></a>

![](https://lh4.googleusercontent.com/k\_0C5L6riiC8QacqO2OX7rrgl6oL5zM\_KZ4KWodren1Z9-G1AHik8s9bDTVJ3xR5-cr8BOv0-7nBtsK6PiQn4C44vYphKVPHIEHAOfs6laymhNyrMMmxZ-o\_di-mv9oqfR3\_blr7)

**Importance:** <mark style="color:red;background-color:red;">TAKE ACTION</mark>

**Meaning:**

* Node runner has an expired TLS cert.

**Possible Next Steps:**

* Renew TLS cert.





### `the blockchain in the relay request is not supported on this node` <a href="#docs-internal-guid-8aa678ee-7fff-c562-4793-4bdb0879d502" id="docs-internal-guid-8aa678ee-7fff-c562-4793-4bdb0879d502"></a>

**Importance:** <mark style="color:red;background-color:red;">TAKE ACTION</mark>

**Meaning:**

* It means that your POKT node is staked for a chain node but isn't able to connect with it.

**Possible Next Steps:**

* Restart your node
  * If you have added or removed any connected chains, you need to restart your POKT node so the node accepts the changes.



## Irrelevant Errors

### `Provided Node is not part of the current session for this application, check your PocketAAT`

![](https://lh6.googleusercontent.com/5SBC0wfaNnHJdklHfIbiJXxfyEOEDqNrVvaRySzZfTf\_boa9YAWqJAR47EYoCy6I60QbcLTorSpCiX2fVBXN7gNkq4RxTrJWuil6s5HVp4wLKJnjwLrABkE73KusVKELHx9byaY4)

**Importance:** <mark style="color:purple;background-color:purple;">IGNORE</mark>

**Meaning:**

Due to differing blockheight between dispatch and your pocket nodes. It isn't something you can correct (other than making sure your pocket node is in sync) and this error isn't counted against your node. It is something the core team hopes to eliminate in the next major version release.



### `missing trie node`

![](https://lh5.googleusercontent.com/hy6osolIRrHSLAlzO\_9Xh7A81p8TbcAZkb9d2z9cZ3d32WhswghnR442WYgY7cE3BAmSo1rqeVFaRbmJ5giggfFJIcealDxsy9lDgqNZlh54ftjVcB5Zx0FuCkrpG0--XAvZRQwJ)

**Importance:** <mark style="color:purple;background-color:purple;">IGNORE</mark>

**Meaning:**

* The app is querying your node for data that has been pruned
* Likely to be an app error where the app should be using an archival endpoint and not a standard mainnet endpoint



### `Client network socket disconnected before secure TLS connection was established`

![](https://lh6.googleusercontent.com/j960GMcvJgMlJ9FnampLBqekDPaHVw8tm0IiFGdhqc6DW-wgWidtGNkYpbeBaVsIk\_Pq9GNuUv9ZBbchBQ7HyTfAwtHZLk7hFgqcgE1nw4tZ8Xb9uJRHC5EEiSZO42XgeaxTOs\_j)

**Importance:** <mark style="color:purple;background-color:purple;">UNKNOWN</mark>

**Meaning:**

* Unknown, probably similar to [#server-timeout-handling-request](errors-from-poktscan.md#server-timeout-handling-request "mention")



### `the evidence is sealed, either max relays reached or claim already submitted` <a href="#docs-internal-guid-c44109d5-7fff-8dcc-1dda-73c2d03f18e4" id="docs-internal-guid-c44109d5-7fff-8dcc-1dda-73c2d03f18e4"></a>

![](https://lh5.googleusercontent.com/y4uH27ze2iMKZjBwAz64W0JYtHB9WdSOeI-Ch8HsKHTy0LBgERH6GiMYID0GzmY8pR6xG6Iz1YnakiMKFd7jUFb5Tus05-WTF\_\_I\_DgAgFGht0erkaVRPs3a8o\_LC7qE41gMnq7w)

**Importance:** <mark style="color:purple;background-color:purple;">IGNORE</mark>

**Meaning:**

* This is the result of an app using more relays that what is staked for them. This relates to app, not nodes.



### `execution reverted`

![](https://lh4.googleusercontent.com/vSN\_ryhI00ICI\_nd7Izb7lJVaj2yQ7fMFJ-SLyU7p432Cvx6-xaTCs8koRszv63pe4fc\_CvTy3vaspOHk1zdgdyXq5mtGs7iHi4XH832mdy3YuVv-31bHnwI6Z36HTr8wtuunuNv)

**Importance:** <mark style="color:purple;background-color:purple;">IGNORE</mark>

**Meaning:**

* An app error they receive when submitting incorrect transactions, failing gas wars, etc.



### `the blockchain in the relay request is not supported for this app` <a href="#docs-internal-guid-043abd8a-7fff-400c-3b5c-ecc2841e6583" id="docs-internal-guid-043abd8a-7fff-400c-3b5c-ecc2841e6583"></a>

![](https://lh4.googleusercontent.com/pDcIaxxBtPiE1AgIgqy4qdzFSNzFCiS7gapJOyOIs-ZbYeg9-0sz6TIbzDEGV\_HpOJeqwtWBD6WqvPy0D73IYU\_tlaozHhzcawP9W5mGRMmZLOTxah9kz\_VPajjqyRM-0mCJQ\_kT)

Same as [#execution-reverted](errors-from-poktscan.md#execution-reverted "mention")

