# Versions / Updates

## v0.18.21 - 2024-1-28

#### **Updated**

* Support for Pocket version `RC-0.10.4`
  * This version will automatically update your pocket config files to be compatible with the new release, including updating seeds and setting `client_session_sync_allowance` to its default value of `1`.
* POKT Snapshot updated to work with POKT new endpoint.



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.18.21/np && chmod +x ./np
```

3\. Start Node Pilot as daemon:

```bash
./np start -d
```

4\. Type in your Node Pilot password

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

## v0.18.17 - 2023-7-20

#### **Updated**

* Support for Pocket version `RC-0.10.4`
  * This version will automatically update your pocket config files to be compatible with the new release, including updating seeds and setting `client_session_sync_allowance` to its default value of `1`.
* POKT Snapshot updated to work with POKT new endpoint.



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.18.17/np && chmod +x ./np
```

3\. Start Node Pilot as daemon:

```bash
./np start -d
```

4\. Type in your Node Pilot password

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

## v0.18.14 - 2023-4-13

{% hint style="danger" %}
**1) ONLY UPDATE TO `v0.18.x` FROM `v0.16.1` or newer.**\
\
**2)** Because of the changes to how Pocket nodes are run, this release is not backwards compatible for Pocket nodes. Once you have upgraded to this version of Node Pilot, you cannot go back to a previous version of Node Pilot.

**After successfully updating to v0.18.x it is recommended you create a** [**new backup of your Node Pilot instance**](backup-node-pilot.md)**.**\
\
**3) Please install the Docker Compose Plugin as detailed** [**here**](install.md#docker-compose-setup)**.**
{% endhint %}

#### **Updated**

* Updated Ethereum, Polygon, Avalanche, and Binance Smart Chain clients



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.18.14/np && chmod +x ./np
```

3\. Start Node Pilot as daemon:

```bash
./np start -d
```

4\. Type in your Node Pilot password

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

## v0.18.12 - 2023-1-23

{% hint style="danger" %}
**1) ONLY UPDATE TO `v0.18.x` FROM `v0.16.1` or newer.**\
\
**2)** Because of the changes to how Pocket nodes are run, this release is not backwards compatible for Pocket nodes. Once you have upgraded to this version of Node Pilot, you cannot go back to a previous version of Node Pilot.

**After successfully updating to v0.18.x it is recommended you create a** [**new backup of your Node Pilot instance**](backup-node-pilot.md)**.**\
\
**3) Please install the Docker Compose Plugin as detailed** [**here**](install.md#docker-compose-setup)**.**
{% endhint %}



#### **Added**

* Choose client option (supported with Ethereum and more chains to come)
* Import and export individual nodes from the UI.
* Status updates to "Session" when POKT Validators are in a session.
* New secrets management using Docker Secrets to remove `priv_val_key.json` from POKT config directories.

{% hint style="info" %}
It is recommended that users create new backups of their Node Pilot instances after updating, as older backups include the `priv_val_key.json` file which can be used to extract private keys.\
\
Backups created with v0.18.x and beyond do not store any `priv_val_key.json` files as they are only stored in an in-memory filesystem when Node Pilot launches.
{% endhint %}

{% hint style="warning" %}
Due to the use of Docker Secrets, starting Node Pilot now requires your password during the startup process.

\
There are 3 ways to input your Node Pilot password

1. Manual entry via stdin (RECOMMENDED as most secure. See Update Process below.)
2. [Password Flag](advanced/commands-and-flags.md)
3. Environment variable (advanced users only)
{% endhint %}

* Expose `nginx.conf` for the node manager nginx server to `~/.node-pilot/config/nginx/nginx.conf` so that advanced users can set custom config values.



#### **Updated**

* Updated logging to differentiate between Node Pilot processes. Daemon instance logs go to `daemon.log`, restarter instance logs go to `restarter.log`, and Node Pilot logs go to `server.log`.
* Fixed Polygon snapshots
* Fixed Harmony block counts
* Updated versions of many supported chains

{% hint style="info" %}
Gnosis nodes will need to be deleted from Node Pilot and redeployed as the new version requires new clients. This will require a resync.
{% endhint %}

* Many Node Launcher updates



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Install Docker Compose

```bash
sudo apt-get update && sudo apt-get install docker-compose-plugin
```

3\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.18.12/np && chmod +x ./np
```

4\. Start Node Pilot as daemon:

```bash
./np start -d
```

5\. Type in your Node Pilot password

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>



## v0.16.1 - 2022-9-23

{% hint style="danger" %}
**MAJOR BREAKING CHANGES!** \
\
This update includes file structure changes and a **SPECIAL UPDATE PROCESS**. Please read the **"IMPORTANT NODES"** below :point\_down:
{% endhint %}

#### **Added**

* Ethereum 2.0 support (using the Prism client)
* Ethereum Goerli testnet support
* All Node Pilot functionality is exposed via a JSON-RPC server at port 34417 (temporary documentation can be found here: [https://gist.github.com/rBurgett/22605a4880e6f6e1cda15e426d02b299](https://gist.github.com/rBurgett/22605a4880e6f6e1cda15e426d02b299))
* All key passwords are now encrypted
* Nodes now automatically restart if they unexpectedly shut down
* Node Pilot can shut down without shutting down nodes



#### **Updated**

* Rinkeby deprecation&#x20;
  * _The Ethereum Rinkeby testnet has been deprecated by the Ethereum foundation (_[_https://blog.ethereum.org/2022/06/21/testnet-deprecation_](https://blog.ethereum.org/2022/06/21/testnet-deprecation)_). As result, we will no longer be supporting Rinkeby in Node Pilot. You can no longer create Rinkeby nodes and we would recommend you delete any existing Rinkeby nodes. If you want to test with an Ethereum testnet, Goerli is the official testnet for Ethereum and as such Node Pilot now supports it._
* Pocket nodes are now served via Node Launcher which allows for one-click updating like other Node Pilot supported chains
* Updated file structure to allow for more flexibility and chain implementations as well as significantly smaller backup files
* POKT Validators fully use Node Launcher's validator API, which will soon include support for Fuse, Harmony, and Ethereum 2.0 staking through the UI.
* All node peer ports are now exposed to the host machine

### IMPORTANT NOTES :point\_down:

This is the biggest release in the history of Node Pilot. It includes many significant new features as well as countless bug fixes. Node Pilot now provides API access to all of its functionality. This can be access via the new JSON-RPC server at port 34417 as well as via the command line. This allows for large-scale scripting of all Node Pilot functionality. The API has been heavily tested in production over the last few months with enterprise deployments running hundreds of Pocket nodes completely headless. This release also includes support for the new standard validator API through Node Launcher which allows for creating validator nodes and staking on multiple blockchains, not just Pocket. In the near future, Node Pilot will allow you to create and stake Fuse, Harmony, and Ethereum 2.0 validators.

When you first run Node Pilot 0.16.0 you will be led through a number of prompts while it updates. Before you upgrade, you will want to save a backup of your config folder in case anything unexpected happens during the upgrade. It is important to understand that these are breaking updates. After the changes have been made, you cannot revert to a previous version of Node Pilot without replacing your config folder with a backed up version and possibly your data folder as well.

It is important that these breaking changes be understood before updating.

### BREAKING CHANGES

**1. File structure updates**\
\
There are a number of file structure changes which were necessary in order to support the validator API as well as a number of newer chains and chain clients. For example, there is no longer a `nodes.json` file in `~/.node-pilot/config`. The Pocket Nodes which used to be in there now live in `~/.node-pilot/config/chains.json`. There are also many changes within `~/.node-pilot/config/nodes`. Fuse and Pocket for example both have updated config file structures. In pocket node folders you will no longer find a root directory. The directories which used to be under the root directory in the config folder are now in the chain data folder. The configs themselves have been moved around as well. The pocket keystore is now in the keys directory where it belongs, having previously been in the root folder which no longer exists. Chain data in `~/.node-pilot/chains` have also been updated as well, with some chains experiencing more changes than others.



**2. Encrypted Passwords**\
\
All key passwords are now encrypted. They used to be in plain text in `nodes.json` but are now stored encrypted within a new file called `~/.node-pilot/config/passwords.json`. This provides significantly more security, but it also means that you will not be able to copy validator nodes between Node Pilot instances just by copying the data from within `chains.json`. While we have always encouraged people to not touch the files within the `.node-pilot` directory, we know that some people do go in there and make their own changes at their own risk so it was worth bringing up.\
\
All passwords are encrypted with the user's master password, so keeping track of your master password is more important than ever. If you lose your master password, you will lose all access to your Node Pilot instance. You can no longer do old tricks like deleting `users.json` and then creating a new user. If you do that, you will not be able to decrypt your passwords. So, it is absolutely essential that you keep track of your master password and that you keep backups of your config folder and all of your keys.



**3. CLI Changes**\
\
There are now multipe options when shutting down Node Pilot. `./np stop` used to stop Node Pilot and all nodes. But, now it only stops Node Pilot itself while leaving the daemonized nodes running. If you want to do a full shutdown of Node Pilot from the command line, you must enter `./np stop --all`.



**4. Moving pocket nodes between Node Pilot instances**\
\
With Node Pilot 0.16.0, because of the changes to passwords and nodes, there is currently no way to move pocket nodes between Node Pilot instances. You can no longer just copy the files from one instance to another. We are working on a native solution for importing/exporting from the UI as well as from the CLI and via the API, but that is not ready yet. So, for the moment your pocket nodes cannot be moved from the Node Pilot instance that they were created in to another Node Pilot instance.



{% hint style="danger" %}
SPECIAL UPDATE PROCESS :point\_down:
{% endhint %}

1\. Backup your Node Pilot instance:

![NOTE: It may take several minutes for NP to zip your config folder. Just click backup and do not navigate away from the screen until the "Save As" prompt appears. ](<../.gitbook/assets/backup (1).png>)

2\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

3\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.16.1/np && sudo chmod +x ./np
```

4\. Start Node Pilot as daemon:

```bash
./np start -d
```

5\. Confirm you understand that this update has file/folder structure changes

<figure><img src="../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

6\. Confirm you have a backup of NP saved

<figure><img src="../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

7\. Confirm you have space for NP to make another backup of your NP configs

<figure><img src="../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

8\. Create a master password (this is the same password you use to log into the NP dashboard.)

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

9\. **ETHEREUM USERS** need to click "UPDATE" to upgrade to ETH2 nodes

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption><p>NOTE: Currently ETH2 nodes will only have a "RUNNING" status and will not show a "SYNCING" status. This will be patched in a later NP update.</p></figcaption></figure>

10\. Delete any Rinkeby nodes

## v0.12.14 - 2022-8-17

#### **Updated**

* Pocked nodes updated to pocket-core RC v0.9.0



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.12.14/np && sudo chmod +x ./np
```

3\. Start Node Pilot as daemon:

```bash
./np start -d
```

## v0.12.12 - 2022-4-28

{% hint style="danger" %}
Starting from v0.12.0 [Node Launcher](https://github.com/decentralized-authority/node-launcher) now uses a `config` directory and a `keys` directory for all chain nodes.

**IF YOUR NODE PILOT SETUP PRE-v.012.0 AND HAS SCRIPTS OR CUSTOMIZATIONS, PLEASE NOTE THIS POSSIBLY BREAKING CHANGE!**\
\
Node folders (ex: `~/.node-pilot/config/nodes/eth-000/`) now contain a `config` folder and a `keys` folder. This allows for more flexibility in the future, but it does break backwards compatibility with previous versions of Node Pilot. This means that once you upgrade to Node Pilot 0.12.1, you cannot revert back to an earlier version. For this reason, **WE HIGHLY RECOMMEND SAVING A BACKUP OF YOUR NODE PILOT CONFIG DIRECTORY BEFORE UPGRADING!**
{% endhint %}

_**NOTE:** Polygon, IoTeX, and OEC are still considered BETA features._

#### **Updated**

* Improved clean shutdown process to optimize for Polygon nodes
* New POKT Testnet seeds added for Testnet nodes



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.12.12/np && sudo chmod +x ./np
```

3\. Start Node Pilot as daemon:

```bash
./np start -d
```

## v0.12.11 - 2022-4-26

{% hint style="danger" %}
Starting from v0.12.0 [Node Launcher](https://github.com/decentralized-authority/node-launcher) now uses a `config` directory and a `keys` directory for all chain nodes.

**IF YOUR NODE PILOT SETUP PRE-v.012.0 AND HAS SCRIPTS OR CUSTOMIZATIONS, PLEASE NOTE THIS POSSIBLY BREAKING CHANGE!**\
\
Node folders (ex: `~/.node-pilot/config/nodes/eth-000/`) now contain a `config` folder and a `keys` folder. This allows for more flexibility in the future, but it does break backwards compatibility with previous versions of Node Pilot. This means that once you upgrade to Node Pilot 0.12.1, you cannot revert back to an earlier version. For this reason, **WE HIGHLY RECOMMEND SAVING A BACKUP OF YOUR NODE PILOT CONFIG DIRECTORY BEFORE UPGRADING!**
{% endhint %}

_**NOTE:** Polygon, IoTeX, and OEC are still considered BETA features._

#### **Added**

* Automatically fixes broken Let's Encrypt symbolic links
* IoTeX memory reporting bug fixed

#### **Updated**

* POKT nodes updated to v0.8.2
* IoTeX memory reporting bug fixed
* General updates and fixes



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.12.11/np && sudo chmod +x ./np
```

3\. Start Node Pilot as daemon:

```bash
./np start -d
```

## v0.12.5 - 2022-4-16

{% hint style="danger" %}
Starting from v0.12.0 [Node Launcher](https://github.com/decentralized-authority/node-launcher) now uses a `config` directory and a `keys` directory for all chain nodes.

**IF YOUR NODE PILOT SETUP PRE-v.012.0 AND HAS SCRIPTS OR CUSTOMIZATIONS, PLEASE NOTE THIS POSSIBLY BREAKING CHANGE!**\
\
Node folders (ex: `~/.node-pilot/config/nodes/eth-000/`) now contain a `config` folder and a `keys` folder. This allows for more flexibility in the future, but it does break backwards compatibility with previous versions of Node Pilot. This means that once you upgrade to Node Pilot 0.12.1, you cannot revert back to an earlier version. For this reason, **WE HIGHLY RECOMMEND SAVING A BACKUP OF YOUR NODE PILOT CONFIG DIRECTORY BEFORE UPGRADING!**
{% endhint %}

_**NOTE:** Polygon, IoTeX, and OEC are still considered BETA features, but improvements to Polygon have been made in this release._

#### **Updated**

* Polygon Snapshots Fixed
* POKT nodes updated to v0.7.1.1
* Updated seed nodes for Fuse and Gnosis
* Updated NGNX to only whitelist `/v1` and `/v1/client` routes when accesses from public DNS.



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.12.5/np && sudo chmod +x ./np
```

3\. _<mark style="color:red;">**NEW NODE PILOT START COMMAND**</mark> <mark style="color:red;"></mark><mark style="color:red;">(since v0.9.4)</mark>_

```bash
./np start -d
```

## v0.12.1 - 2022-4-11

{% hint style="danger" %}
[Node Launcher](https://github.com/decentralized-authority/node-launcher) now uses a `config` directory and a `keys` directory for all chain nodes.

**IF YOUR NODE PILOT SETUP HAS SCRIPTS OR CUSTOMIZATIONS, PLEASE NOTE THIS POSSIBLY BREAKING CHANGE!**\
\
Node folders (ex: `~/.node-pilot/config/nodes/eth-000/`) now contain a `config` folder and a `keys` folder. This allows for more flexibility in the future, but it does break backwards compatibility with previous versions of Node Pilot. This means that once you upgrade to Node Pilot 0.12.1, you cannot revert back to an earlier version. For this reason, **WE HIGHLY RECOMMEND SAVING A BACKUP OF YOUR NODE PILOT CONFIG DIRECTORY BEFORE UPGRADING!**
{% endhint %}

_**NOTE:** Polygon, IoTeX, and OEC should be considered BETA features as we have only been able to conduct limited testing._&#x20;

#### **Added**

* [Node Launcher](https://github.com/decentralized-authority/node-launcher) now separates configs and keys
* Polygon, IoTeX, and OEC are now available
* Added support for a NetData config file
* Ability to update TLS certs manually

#### **Updated**

* Adjust NetData storage parameters
* Updated NGINX cache paramerter
* Improved process for adding new chains to POKT nodes
* General updates and fixes



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.12.1/np && sudo chmod +x ./np
```

3\. _<mark style="color:red;">**NEW NODE PILOT START COMMAND**</mark> <mark style="color:red;"></mark><mark style="color:red;">(since v0.9.4)</mark>_

```bash
./np start -d
```

## v0.11.1 - 2022-2-4

{% hint style="danger" %}
#### **For those on an older v0.7.xx version, please update to** v0.8.12 before updating to this version.
{% endhint %}

#### **Updated**

* Fixed "Pull Snapshot" issues for POKT bootstrapping
* Harmony and Ethereum nodes updated
* Optimized SSL Cert updating
* Limited NGINX logs to save on storage space
* GUI boots independent of POKT nodes
* Warnings users from running with a root user
* Fixed Harmony RelayChainID for new nodes
* Other [Node Launcher](https://github.com/decentralized-authority/node-launcher) updates and fixes



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.11.1/np && sudo chmod +x ./np
```

3\. _<mark style="color:red;">**NEW NODE PILOT START COMMAND**</mark> <mark style="color:red;"></mark><mark style="color:red;">(since v0.9.4)</mark>_

```bash
./np start -d
```

## v0.11.0 - 2022-1-20

{% hint style="danger" %}
#### **For those on an older v0.7.xx version, please update to** v0.8.12 before updating to this version.
{% endhint %}

#### **Added**

* Harmony explorer node integration
  * _NOTE: Currently Harmony nodes do not have an accessible way to pull the syncing status. For this reason, Harmony nodes will say "Running" even if they are syncing. To learn if you node is synced, check the latest block-height at the_ [_Harmony Explorer_](https://explorer.harmony.one/)_)_
* Pull snapshot functionality for Pocket, Harmony, and Fuse
* Add/Remove Pocket Validator relay chains from the UI
* Allow Pocket Validators to server 0001 (Pocket Network)
* Stop node functionality
* Update stake functionality
* Clear node data directory functionality
* Delete node functionality
* Unjail functionality

#### **Updated**

* Users can set their own stake amount
* Increase Pocket RPC timeout
* Other [Node Launcher](https://github.com/decentralized-authority/node-launcher) updates and fixes



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.11.0/np && sudo chmod +x ./np
```

3\. _<mark style="color:red;">**NEW NODE PILOT START COMMAND**</mark> <mark style="color:red;"></mark><mark style="color:red;">(since v0.9.4)</mark>_

```bash
./np start -d
```

## v0.9.5 - 2021-12-11

{% hint style="danger" %}
#### **For those on an older v0.7.xx version, please update to** v0.8.12 before updating to this version.
{% endhint %}

#### **Updated**

* Improved shutdown process
* Enables chain node updating without restarting
* Fixed update button glitch



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.9.5/np && sudo chmod +x ./np
```

3\. _<mark style="color:red;">**NEW NODE PILOT START COMMAND**</mark> <mark style="color:red;"></mark><mark style="color:red;">(since v0.9.4)</mark>_

```bash
./np start -d
```

## v0.9.4 - 2021-12-7

{% hint style="danger" %}
#### **For those on an older v0.7.xx version, please update to** v0.8.12 before updating to this version.
{% endhint %}

#### **Added**

* Daemon functionality (runs Node Pilot as an auto-restarting background application)
* 1-click updates for chain nodes
* Terminal commands and flags (see [commands-and-flags.md](advanced/commands-and-flags.md "mention"))
* System check debug tool (see [commands-and-flags.md](advanced/commands-and-flags.md "mention"))
* Manual IP addresses (see [commands-and-flags.md](advanced/commands-and-flags.md "mention"))

#### **Updated**

* Pocket updated to RC-v0.7.0.1
* Remove excessive pocket node info logs



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://builds.decentralizedauthority.com/node-pilot/v0.9.4/np && sudo chmod +x ./np
```

3\. _<mark style="color:red;">**NEW NODE PILOT START COMMAND**</mark>_

```bash
./np start -d
```

## v0.8.12 - 2021-11-17

{% hint style="danger" %}
#### **Please update to** v0.7.11 **before updating to** v0.8.12 if you are running an older version of Node Pilot.
{% endhint %}

{% hint style="info" %}
Once upgraded to v0.8.12, users can not return to past versions of Node Pilot.
{% endhint %}

#### **Added**

* Integrated [Node Launcher](https://github.com/decentralized-authority/node-launcher) engine for running chains
* Show "Syncing" and "Running" states for both Pocket and Avalanche nodes
* Assign unique peer ports for all chains
* Expanding logging to catch errors during node startup

#### **Updated**

* Removed legacy codec flag from Pocket stake command
* Updated docker run command logging to correctly log all commands
* Updated nginx reverse proxy configs to decouple the UI nginx instance and nodes during boot
* Updated and clarified memory usage in node tables
* Updated xDAI load balancer name in configs to Pocket relay names
* Disabled Docker logging for node containers
* xDAI and AVAX nodes updated



#### **Update Process:**

1\. Make sure you are running v0.7.11 before updating

2\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

3\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/6e8cfa48-32e4-4059-a8c2-b530e4fafad1/np && sudo chmod +x ./np
```

4\. Start Node Pilot

```bash
./np
```



## v0.7.11 - 2021-11-4

{% hint style="danger" %}
#### **UPDATE REQUIRES SPECIAL INSTRUCTIONS FOR POCKET NODES. Follow all instructions in the Update Process below.**

Pocket nodes may take several minutes to launch after the update due to new caching features with BETA-v0.6.3.11.
{% endhint %}

#### **Updated**

* Pocket updated to BETA-v0.6.3.11
* Updates Pocket inbound peers to 14 _(as recommended by the Pocket team)_
* Fuse updated to 3.2.6 _(this is a hard fork update for Fuse nodes and a resync is required. Fuse chain data will be deleted a the resync will be automatically started upon Node Pilot launch)_
* ETH and AVAX nodes updated



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/e36c70b1-15dc-452f-b0d9-4b1b7fd4a995/np && sudo chmod +x ./np
```

3\. Update all Pocket nodes to have 8GB of RAM. This resource update is required for pocket-core BETA-v0.6.3.11.

{% hint style="warning" %}
Instructions for updating node resources can be found here: [edit-node-resources.md](advanced/edit-node-resources.md "mention")
{% endhint %}

4\. Start Node Pilot

```bash
./np
```

## v0.7.5 - 2021-10-3

#### **Updated**

* Pocket updated to v0.6.3.7
* Updates fast sync for Pocket nodes to v1 _(a requirement for v0.6.3.7)_
* Patch for addressing error 125.



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/a6a2a422-4014-4a13-8f0a-05536f0cecd7/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.7.4 - 2021-9-24

#### **Added**

* Reveal private key functionality
* Pocket Mainnet simulate relay toggle

#### **Updated**

* Improved restart node process
* Passphrase errors fixed
* Update Avalanche to x1.6.0



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/72a21107-a981-4de1-8f4d-be8f0ac1772a/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.7.2 - 2021-8-27

#### **Updated**

* Updated ETH, AVAX, and BSC to the latest versions.



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/f2102a4a-cae0-4028-96ed-def9be29183b/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.7.1 - 2021-7-30

#### **Updated**

* Updated ETH, AVAX, and BSC to the latest versions.



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/3d4212e9-b4ef-43f0-890a-9618f2a3381d/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.7.0 - 2021-7-21

#### **Added**

* FUSE nodes are now supported.
* Chain data folders can now be moved to a custom directory
  * Find in the "Advanced" options when creating a node.

#### **Updated**

* AVAX, xDAI, and BSC nodes have been updated.
* Main dashboard shows stats for all nodes.
* Remote ETH nodes work inside of the GUI.



#### **Update Process:**

1\. Shutdown NP:

![](<../.gitbook/assets/image (1).png>)

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/25daee9a-6d10-4948-b594-45712062726b/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.6.5 - 2021-7-4 _(experimental update)_

{% hint style="warning" %}
Due to the recent nature of Pocket 0.6.3.6, it has not been fully tested and automated within Node Pilot. The POKT testnet has not been updated to 0.6.3.6, which is essential for testing this new release.

To use Node Pilot for Pocket Mainnet, there may be manual steps required (like deleting chain folders and so on) which you may have to figure out yourself. If you have an issue with 0.6.3.6, reach out to the Pocket community via the #node-runner channel in the [Pocket Discord.](https://discord.gg/MtRp4BE)
{% endhint %}

#### **Added**

* Let's Encrypt auto-updating has been configured.

#### **Updated**

* Pocket updated to 0.6.3.6
* Legacy codecs are now disabled.



#### **Update Command:**

1\. Restart server:

```bash
sudo reboot
```

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/1bdca714-98db-4cf9-9834-1a9a3cbb3118/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.6.3 - 2021-5-31

#### **Added**

* Upgrade to Pocket `0.6.3` &#x20;
* Safe shutdown functionality from both the UI and command line
* Auto backups for Node Pilot config JSON files are changed
* Command Entry output modal window
* Ability to send curl commands directly to pocket node containers

#### **Updated**

* FastSync default to `v0` for all Pocket nodes
* Updated dependencies



#### **Update Command:**

1\. Restart server:

```bash
sudo reboot
```

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/d8af2a0b-4f6d-4dc5-8698-bdf8cc121866/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.5.12 - 2021-5-24

#### **Added**

* Local network IP address selector added to config process



#### **Update Command:**

1\. Restart server:

```bash
sudo reboot
```

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/52c52264-81d5-483d-8d33-7b5a49b4ee76/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.5.11 - 2021-4-26

#### **Updated**

* Pocket Testnet to version 0.6.1



#### **Update Process:**

1\. Restart server:

```bash
sudo reboot
```

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/a511ef9f-3991-495b-b63a-30db6ade0421/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.5.10 - 2021-4-26

#### Added

* Notification if any necessary ports are already in use
* Node Pilot version in UI navbar



#### Update Command:

1\. Restart server:

```bash
sudo reboot
```

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/bb2d6ce0-df10-4cf7-ba15-864adada503d/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```

## v0.5.7 - 2021-4-24

#### Fixed

* Corrected total memory stats
* Corrected CPU core count on virtual machines



#### Update Command:

1\. Restart server:

```bash
sudo reboot
```

2\. Update command:

```bash
cd ~ && wget -O np https://s3.amazonaws.com/files.decentralizedauthority.com/d16face2-e63e-4924-a711-def7c2293a64/np && sudo chmod +x ./np
```

3\. Start Node Pilot

```bash
./np
```
