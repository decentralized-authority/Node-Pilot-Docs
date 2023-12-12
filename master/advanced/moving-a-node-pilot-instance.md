# Moving A Node Pilot Instance

Node Pilot is designed to be as portable as possible. This is important because hardware requirements may change frequently as chains update their node clients.

All settings and configurations are transferred over when following this guide.

_NOTE: For these instructions, (A) represents the old instance, and (B) represents the new instance._

{% hint style="danger" %}
**PORT FORWARDING**: If you are running either instance of Node Pilot behind a home router or firewall, you will need to set up port forwarding for port **22**. Transferring a Node Pilot config will require port **22** accessible by both (A) and (B).
{% endhint %}

{% hint style="danger" %}
**CUSTOM CHAIN DIRECTORIES:** If you opted to use custom "Chains Directory" when creating a node, then when migrating you will need to either:\
\
1\. Have the same paths availble in the new instance\
2\. Change the Chain Data location for the effected nodes in `/.node-pilot/config/chains.json`
{% endhint %}

## Prepare Machine(B)

#### 1. Create new machine with the same username. Using a different username with break the migration.

#### 2. [Install Node Pilot](../install.md) on machine(B), but do not run Node Pilot(B) yet.

{% hint style="warning" %}
If Node Pilot was run on machine(B), then the `/.node-pilot` folder needs to be deleted. **DO NOT RUN THIS COMMAND ON MACHINE(A)!**\
\
Delete via CLI:

```
rm -r ~/.node-pilot
```
{% endhint %}

**3. Create a new `.node-pilot` folder on machine(B) in the home directory**

{% hint style="info" %}
Via CLI:

```
mkdir ~/.node-pilot
```
{% endhint %}

## Backup and transfer on Machine(A)

#### 4. [Save a Backup](../backup-node-pilot.md) of Node Pilot(A) for extra protection.

Click "BACKUP" to download a backup ZIP of your config folder. If your backup includes Pocket nodes, the file could be many gigabytes which will take a few minutes before the download begins.

**DO NOT NAVIGATE AWAY FROM THIS PAGE UNTIL THE FILE IS SAVED.**

![](<../../.gitbook/assets/backup (1).png>)

#### 5. Shut down Node Pilot(A)

![](<../../.gitbook/assets/image (85).png>)

#### 6. Go to your DNS service provider and point your Node Pilot domains to the public IP address of machine(B). YOU MUST USE THE SAME DOMAINS.

{% hint style="info" %}
See [Configure Node Pilot](../configure/user-dns-ports-tls.md) for the original DNS instructions&#x20;
{% endhint %}

#### 7. From machine(A), use this command to transfer your Node Pilot config folder to machine(B)

```
scp -r '/home/<USER(1)>/.node-pilot/config' <USER(2)>@<DOMAIN NAME>:/home/<USER(2)>/.node-pilot/
```

Example: `scp -r '/home/amish/.node-pilot/config' amishb@node3.routewall.com:/home/amishb/.node-pilot/`

## Launch on Machine(B)

#### 8. Once the transfer is complete, configure any port forwarding if applicable on machine(B) (see [Configure Node Pilot](../configure/user-dns-ports-tls.md))

#### 9. Run Node Pilot(B)

```
./np start -d
```

#### 10. Go to your Node Pilot domain and log in to ensure everything is working.

![](<../../.gitbook/assets/image (19).png>)

#### 11. Machine(A) is now ready to be wiped or deleted
