# Errors in Logs

### `wrong Block.Header`

`error during handshake: error on replay: wrong Block.Header.AppHash. Expected BF34AAEB908D2207A9451F5DC8E15C3439A4D15BCB9CBC631CAE2DFF163B0F53, got 15DE1A44BC72792E0AA016523F461E71298822A000DC2C3057A98E49262FB812 {"timestamp":"2022-01-05T14:34:55.108Z"}`

**Importance:** <mark style="color:red;background-color:red;">TAKE ACTION</mark>

**Meaning:**

* Pocket data files have corrupted, which can happen on occasion.

Next Steps:

* [Delete chain data](broken-reference) for that Pocket node.



### **`closed with status code 1`**

`Error: start --useCache --maintnet closed with status code 1`

**Importance:** <mark style="color:red;background-color:red;">TAKE ACTION</mark>

Same as [#wrong-block.header](errors-in-logs.md#wrong-block.header "mention")



### `error executing the http request`

`E[2021-12-03|17:31:38.148] could not send relay with error: ERROR: Codespace: pocketcore`\
`Code: 28`\
`Message: "error executing the http request: Post "http://eth-mainnet": dial tcp 172.18.0.11:80: connect: connection refused"`

**Importance:** <mark style="color:red;background-color:red;">TAKE ACTION</mark>

**Meaning:**

* Your Pocket node is not able to connect to a chain node. You back-end isn't connected properly.

{% hint style="info" %}
This will only occur if have made custom changes to Node Pilot that are misconfigured.
{% endhint %}

**Next Steps:**

* Fix your connection issues or revert back to your backup of Node Pilot.





### `the evidence is sealed`

`{"timestamp":"2022-01-03T09:33:52.877Z"} info: E[2022-01-03|09:33:58.374] could not validate relay for app: 1ccafd13daef2413697af2a3254fc585b22847507d0e8888995b92df15983ec0 for chainID: 0027 with error: ERROR: Codespace: pocketcore Code: 90 Message: "the evidence is sealed, either max relays reached or claim already submitted" {"timestamp":"2022-01-03T09:36:01.252Z"} info: error in RPC Handler WriteJSONResponse: http: Handler timeout`



**Importance:** <mark style="color:purple;background-color:purple;">IGNORE</mark>

**Meaning:**

* This is the result of an app using more relays that what is staked for them. This relates to app, not nodes.



### `Pong timeout / Invalid evidence`

`Connection failed @ sendRoutine module=p2p peer=c42eb91779789b02a735db4434ed7429d30d8285@64.225.97.59:26656 conn=MConn{64.225.97.59:26656} err="pong timeout" E[2021-12-08|05:44:29.568] Stopping peer for error module=p2p peer="Peer{MConn{64.225.97.59:26656} c42eb91779789b02a735db4434ed7429d30d8285 out}" err="pong timeout"`

**OR**

`E[2021-12-22|15:42:06.069] enterPrevote: ProposalBlock is invalid module=consensus height=45931 round=1 err="Invalid evidence: evidence was already committed. Evidence: VoteA: Vote{5119:97FBC8D876FE 41838/01/2(Precommit) 1A6D69B9EAEB 979A77B34C07 @ 2021-11-04T23:03:00.609946237Z}; VoteB: Vote{5119:97FBC8D876FE 41838/01/2(Precommit) 000000000000 591B24A9E42E @ 2021-11-04T23:04:13.733787364Z}" proposer=01A2C7D61502A8EC5834A8F75873453883137611`

**Importance:** <mark style="color:purple;background-color:purple;">IGNORE</mark>

**Meaning:**

* This simply means that Tendermint is rotating peers or sessions. This is not an "error" but part of regular node processes.



### `the block height passed is invalid`

`E[2021-12-03|18:54:46.824] could not validate relay for app: 1ccafd13daef2413697af2a3254fc585b22847507d0e8888995b92df15983ec0 for chainID: 0025 with error: ERROR: Codespace: pocketcore Code: 60 Message: "the block height passed is invalid"`

**Importance:** <mark style="color:purple;background-color:purple;">IGNORE</mark>

Same as [#pong-timeout](errors-in-logs.md#pong-timeout "mention")



### `the blockchain in the relay request is not supported on this node`

`E[2021-12-22|20:36:17.431] could not validate relay for app: e36b91e62ba7c611d041dafb65152fb7d290cdf202ca16232ead997263be0a43 for chainID: 0040 with error: ERROR: Codespace: pocketcore: Code: 26 Dec 22 20:36:17: Message: "the blockchain in the relay request is not supported on this node"`

**Importance:** <mark style="color:purple;background-color:purple;">IGNORE</mark>

**Meaning:**

* An app is sending requests to the wrong chain node. This is not a node issue.



### `WARNING: Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap`

**Importance:** <mark style="color:purple;background-color:purple;">IGNORE</mark>

**Meaning:**

* Docker has not been given resource limitation. Node Pilot allows nodes to use full system resources without system wide limitations.
