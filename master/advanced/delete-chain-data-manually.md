# Delete Chain Data Manually

Sometimes a node's chain data can get corrupted, which requires deleting the chain data so it can re-sync.

Example of corruption in a node's logs:

`2021-09-20 00:53:40 UTC Encountered error during snapshot restoration: Snapshot error Chunk size is too large.`

In most cases, you can delete the chain directly from that node's Dashboard:

![](<../../.gitbook/assets/image (41).png>)

In some cases, you may need to clear the chain data manually. To do so, follow these steps:

#### 1. Identify the NodeID you would to edit (for this example: FUSE-0000)

![](<../../.gitbook/assets/image (63).png>)

**2. Shut down NP**

![](<../../.gitbook/assets/image (85).png>)

#### 3. Delete the node's chain data folder in \~/.node-pilot/chains/\<nodeID>

{% hint style="info" %}
Via command line (Example for FUSE-000):

```
rm -r ~/.node-pilot/chains/fuse-000
```
{% endhint %}

For nodes that were given custom Chain Directories, apply this step to the custom directory instead of the default directory.

![](<../../.gitbook/assets/image (81).png>)

#### 4. Start NP

```
./np start -d
```
