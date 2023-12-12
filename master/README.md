# Node Pilot

{% hint style="info" %}
Node Pilot is still in Alpha and is not meant for production use. It is being released for testing purposes only.
{% endhint %}

Node Pilot is the first, automated, deployment solution that can scale to support any blockchain node. To achieve automation there are some important steps that you should take to ensure your nodes remain secure.

### 1: Do not give untrusted parties access to your server.

Depending on the node, Node Pilot may store Key Passwords in plain text so it can be accessed for automation. Key passwords can be used in some cases to access private keys. Most nodes by design, like Bitcoin, store Key Passwords only in plain text.

**Giving anyone access to your server is giving them access to your private keys.**&#x20;

### 2: Do not install extra software on your Node Pilot instance.

Any software installed on your Node Pilot instance could access your Private Keys through the Key Password being in plain text.

**We advise that users install only the OS and Docker.**
