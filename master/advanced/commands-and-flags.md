# Commands and flags

Commands tell Node Pilot what to do, while flags provide additional instruction.

Commands and flags follow this format:&#x20;

`./np <command> <flags>`&#x20;

Here is a list of commands/flags:

<table><thead><tr><th width="150">Command</th><th width="165">Short flag</th><th width="150">Full flag</th><th>Purpose</th></tr></thead><tbody><tr><td></td><td>-h</td><td>--help</td><td></td></tr><tr><td>start</td><td>-d</td><td>--daemon</td><td>Starts Node Pilot as an auto-restarting daemon.</td></tr><tr><td>start</td><td></td><td>--local-ip</td><td>Manually set local IP address.</td></tr><tr><td>start</td><td></td><td>--public-ip</td><td>Manually set public IP address.</td></tr><tr><td>stop</td><td></td><td></td><td>Stops the Node Pilot daemon.</td></tr><tr><td>check</td><td></td><td></td><td>Runs Node Pilot automated system checks to help identify issues with IP address, ports, DNS, permissions, etc.<br></td></tr><tr><td>password</td><td></td><td>--password</td><td>Starts Node Pilot with the password attached.</td></tr></tbody></table>

## Examples

**1. Starting Node Pilot as a daemon:**

```
./np start -d
```

Expected output:

![](<../../.gitbook/assets/image (66).png>)

**2. Stop Node Pilot running as a daemon:**

```
./np stop
```

Expected output:

![](<../../.gitbook/assets/image (2).png>)

**3. Run Node Pilot system check:**

```
./np check
```

Expected output:

![](<../../.gitbook/assets/image (23).png>)



{% hint style="danger" %}
Any red "x" in the system check is an indication of a misconfiguration.
{% endhint %}

**3. Start Node Pilot with password attached**

`./np start -d --password mypasswordhere`
