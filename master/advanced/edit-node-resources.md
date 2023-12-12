# Edit Node Resources

In future releases, we plan to allow users to edit node settings directly in the GUI. Until then, Node Pilot makes it easy to manually edit your node settings through JSON files.

To edit the vCPUs and Memory for a node, follow these steps:

#### 1. Identify the node you would to edit (for this example: XDAI-0000)

![](<../../.gitbook/assets/image (47).png>)

#### 2. Shut down NP

![](<../../.gitbook/assets/image (85).png>)

#### 3. Edit the settings file

For Validator nodes: `~/.node-pilot/config/nodes.json`&#x20;

For Chain nodes: `~/.node-pilot/config/chains.json`&#x20;

{% hint style="info" %}
Via command line:

```
nano ~/.node-pilot/config/nodes.json
```
{% endhint %}

{% hint style="danger" %}
Only edit `"cpus"` and `"mem"` variables. Editing other variables could break your node and cause errors.
{% endhint %}

Example:

`{` \
`"_id": "xdai-000",`\
`"type": "MANAGED",`\
`"chainType": "FULL_NODE",`\
`"ticker": "xdai",`\
`"network": "mainnet",`\
`"rpcPort": 8555,`\
`"walletPassword": "",`\
`"cpus": 4,`\
`"mem": 8192,`\
`"chainDir": "",`\
`"createdAt": "2021-07-20T20:46:23.840Z",`\
`"updatedAt": "2021-07-20T20:46:23.840Z"`\
`}`

#### 4. Save changes and exit.

{% hint style="info" %}
Via command line:

Press `Ctrl + o` then press `Enter`&#x20;

Press `Ctrl + x`to exit
{% endhint %}

**5. Verify file was changed**

```
cat ~/.node-pilot/config/nodes.json
```

#### 6. Start NP

```
./np start -d
```
