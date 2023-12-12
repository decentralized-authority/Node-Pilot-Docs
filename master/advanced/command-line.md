---
description: >-
  In the case that users need to send CLI, RPC, or CURL commands to their nodes,
  there are a few options:
---

# Command-line

### CLI

CLI commands for Pocket nodes can be found [here](https://docs.pokt.network/core/specs/cli).&#x20;

{% tabs %}
{% tab title="via Node Pilot" %}
For select nodes (like Pocket nodes), you can send CLI commands directly to a node via Node Pilot.

_Pocket commands that require a password will need to include `--pwd <PASSWORD KEY>` at the end of the command. If you are having issues submitting a command, switch to using the terminal._

**1. Select node:**

![](<../../.gitbook/assets/image (8).png>)

**2. Submit commands:**

![](<../../.gitbook/assets/image (30).png>)

{% hint style="info" %}
If a CLI command is not providing an output, try restarting the node via the "Restart" button.
{% endhint %}
{% endtab %}

{% tab title="via Terminal" %}
CLI commands can be sent to nodes via terminal.

```
docker exec -ti [node id] [params]
```
{% endtab %}
{% endtabs %}

### CURL

CURL commands can be sent to nodes via terminal.

```
docker exec [node id] curl [params]
```

{% hint style="info" %}
EXAMPLE: Pocket node Tendermint RPC request

```
docker exec pokt-000 curl http://localhost:26657/status
```
{% endhint %}

_NodeIDs can be found on the Dashboard:_

![](<../../.gitbook/assets/image (7).png>)

