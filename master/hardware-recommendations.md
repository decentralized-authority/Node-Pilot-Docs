---
description: >-
  To help with determining the proper hardware for node running, here are some
  concepts and recommendation to assist with resource planning.
---

# Hardware Recommendations

### CPUs vs vCPUs

vCPUs are equal to the amount of "Threads" (not cores) your CPU supports.

_Example: 8 Threads = 8 vCPUs_

This means that [this common Xeon server CPU](https://ark.intel.com/content/www/us/en/ark/products/91754/intel-xeon-processor-e52680-v4-35m-cache-2-40-ghz.html) has 28 vCPUs to use for nodes.



### NVMe vs SSD&#x20;

We are recommending only using NMVe since fast drives are best for serving RPC requests. SSDs may cause less revenue and add to more frequent jailings for Pocket nodes.

When considering drive speeds, IOPS is the metric to consider. The higher the IOPS the faster that drive can perform random reads and writes, which results in greater performance, especially when running many nodes on a single drive.&#x20;

{% hint style="warning" %}
Too many nodes running on a single drive can cause a degradation in performance. We have internally tested Node Pilot with 5 chain nodes and 5 POKT Validators on a single Gen3 NVMe drive with great performance. Some users have reported more nodes on a single drive with success, but _**your mileage may vary depending on your hardware and node selection.**_\
\
With multiple NVMe drives, we've successfully tested up to 12+ POKT Validators on one Gen3 NVMe drive while having chain nodes on another drive.
{% endhint %}



### RAID 0

When considering RAID, only use RAID 0 since RAID 1 greatly decreases drive IOPS.



### Per Node Hardware Requirements

Here are the suggested hardware specs for nodes being used on the Pocket Network. These are primarily pulled from official sources (when available).

{% hint style="danger" %}
Blockchain storage requirements grow with time. For best practice you should expect each blockchain to increase their storage requirements by 50% to 100% per year.
{% endhint %}

| Node                                                                                                        | vCPUs                                                                                                                                                                         | RAM   | NVMe Storage |
| ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----- | ------------ |
| [Pocket](https://docs.pokt.network/home/paths/node-runner#prepare-your-kit)                                 | <p>4 to 8<br><em>NOTE: plan hardware for 4 vCPUs per node, but when creating the node allocate 16. This will allow nodes extra resources to close app large session.</em></p> | 20GB  | 600GB        |
| [Avalanche](https://docs.avax.network/build/tutorials/nodes-and-staking/run-avalanche-node)                 | 8                                                                                                                                                                             | 16GB  | 1TB          |
| [Bitcoin](https://comit.network/blog/2020/09/21/setup-bitcoin-cloud-node/)                                  | 4                                                                                                                                                                             | 8GB   | 500GB        |
| [BSC](https://docs.binance.org/smart-chain/developer/fullnode.html)                                         | 8                                                                                                                                                                             | 32GB  | 2TB          |
| [Ethereum](https://ethereum.org/en/developers/docs/nodes-and-clients/#hardware)                             | 8\*                                                                                                                                                                           | 16GB  | 2TB          |
| [Fuse](https://docs.fuse.io/docs/developers/run-or-access-fuse-nodes#hardware)                              | 6\*                                                                                                                                                                           | 8GB   | 45GB         |
| [Harmony](https://docs.harmony.one/home/network/validators/server-setup/requirements) (Shard 0)             | 16\*                                                                                                                                                                          | 32G\* | 6TB          |
| [Polygon](https://wiki.polygon.technology/docs/operate/technical-requirements/)                             | 16                                                                                                                                                                            | 16    | 6TB          |
| [xDAI](https://www.xdaichain.com/for-validators/for-consensus-validators/node-deployment/manual-deployment) | 6\*                                                                                                                                                                           | 8GB\* | 400GB        |

&#x20;\* Have been modified to reflect the advice from experienced Pocket node runners
