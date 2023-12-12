# User / DNS / Ports / TLS

## Setup User

![](<../../.gitbook/assets/image (3).png>)

\
DNS Records
-----------

To properly configure Node Pilot, you need to direct a domain or subdomain to the Public IP address of this Node Pilot instance. We recommend using a subdomain so you can add more instances of Node Pilot to the same domain in the future.

{% tabs %}
{% tab title="Subdomain" %}
Add these three DNS entries:

1. Hostname = \[subdomain of your choosing]
2. Hostname = \*.\[subdomain from the step above]

The " \* " hostname allows Node Pilot to create second-level subdomains automatically for your nodes. This " \* " entry is known as a "wildcard", which is supported by most DNS providers. If your DNS provider does not support wildcards, then you may need to purchase a domain from another provider (we recommend [iwantmyname.com](https://iwantmyname.com/)).

{% hint style="danger" %}
GoDaddy does not work with 2 letter subdomains. For those using GoDaddy use at least 3 letters.
{% endhint %}

![Example of DNS settings](<../../.gitbook/assets/image (71).png>)
{% endtab %}

{% tab title="Domain" %}
{% hint style="warning" %}
It is recommended you use a subdomain instead of the top level domain. Unless you have a specific reason to use a top level domain, we advise following the subdomain instructions.
{% endhint %}

Add these two DNS entries:

1. Hostname = @
2. Hostname = \*

The " \* " hostname allows Node Pilot to create subdomains automatically for your nodes. This " \* " entry is known as a "wildcard", which is supported by most DNS providers. If your DNS provider does not support wildcards, then you may need to purchase a domain from another provider (we recommend [iwantmyname.com](https://iwantmyname.com/)).

![Example of DNS settings.](<../../.gitbook/assets/image (25).png>)
{% endtab %}
{% endtabs %}

## Setup Ports, DNS, and TLS

{% hint style="danger" %}
**PORT FORWARDING**: We **strongly recommend** you always run Node Pilot behind a firewall or home router. This means you will need to set up port forwarding for ports **80**, **443**, and **26656** to the servers local IP address. Node Pilot requires those ports to operate.
{% endhint %}

Inside the main screen, Node Pilot displays the status of the state of your ports, DNS, and TLS settings.

Click on each status to configure, and follow the in-app instruction.

![](<../../.gitbook/assets/Main Public Click to configure.png>)

Once TLS is configured, Node Pilot will automatically logout your user and reload your instance from your domain.

![](<../../.gitbook/assets/image (50).png>)

