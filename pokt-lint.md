# POKT Lint

Any POKT node runner knows that the most important factors to maximizing rewards are:

1. Chain selection
2. Relay latency

Fortunately, through tools like [https://poktscan.com](https://poktscan.com), node runners can research chain rewards to identify which chains they want to serve… but there are no practical ways for node runners to identify their relay latency in respect to Pocket Portal locations until now.\
\
Use [POKT Lint](https://poktlint.com) to measure your node's latency on the Pocket Network.

### How to use

**1) Turn on Simulate Relays on the nodes you want to test. This requires restarting your node.**

Node Pilot user can simply click “Simulate Relays”

![](<.gitbook/assets/image (22).png>)

Other node runners can start pocket-core [with the --simulateRelay glage](https://docs.pokt.network/home/paths/node-runner#test-your-node)

```
pocket start --simulateRelay
```



**2) Wait for the node to finish starting up**

Pocket nodes can take up to 20 minutes to warm up.

Node Pilot users will know when the node is warmed up when the block height appears.

![](<.gitbook/assets/image (73).png>)



**3) Go to POKTLint. and add your node addresses.**

Submitting multiple nodes requires a comma between each address



```
c59c793082d5673cba8470dcc73d24218bc3c165,f23464c8ec8a60b2ebae74589dce43c7b0bf37ad
```

![](<.gitbook/assets/image (34).png>)



**4) See the results!**



<mark style="color:green;"><100ms = GREAT</mark> (Guaranteed full potential rewards from that Portal location)

<mark style="color:yellow;">100ms - 300ms = OK</mark> (likely to see less rewards in most sessions)

<mark style="color:orange;">300ms - 400ms = MINIMAL</mark> (likely faster nodes are getting the lions share of the rewards)

<mark style="color:red;">>500ms - TO SLOW</mark> (don't expect any rewards)

![](<.gitbook/assets/image (32).png>)



**5) After testing be sure to restart your POKT node without Simulate Relays.**

Simulate Relays should not remain on.

![](https://lh4.googleusercontent.com/ni9WSFj4poFoXadDBTksYeScdnaQOQ47gAEwIrdbIFhG10mIR731Nw8daBrGHD0oMYXBycTLVIg9xczVBWeAF-7IVjGTrN46YwhTv59pd0\_cJ4sWtKmLJ1LYYg2e6l\_QhGrW8-a8)
