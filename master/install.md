# Install

{% hint style="info" %}
Node Pilot is still in Alpha and is not meant for production use. It is being released for testing purposes only.
{% endhint %}

Node Pilot has three dependencies:&#x20;

1. **Debian-based Linux OS**
2. **Docker**
3. **Docker Compose Plugin**

The following guide was put together using Ubuntu Server (Ubutunu Desktop for those who prefer a GUI). Other Debian-based OS's can be used as well, although they may require more configuration.

{% hint style="danger" %}
Node Pilot does not work with Windows Subsystem for Linux (WSL).
{% endhint %}

### Docker Setup

From a fresh install of Ubuntu, Docker can be installed by copy and pasting these following commands into the terminal. These commands and their explanation can be found in [Docker's official install instructions for Ubuntu](https://docs.docker.com/engine/install/ubuntu/).

**Command 1:**

```bash
sudo apt-get update
```

**Command 2:**

```bash
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

**Command 3:**

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

**Command 4:**

```bash
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

**Command 5:**

```bash
sudo apt-get update
```

**Command 6:**

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

**Command 7:**

```bash
sudo groupadd docker
```

**Command 8:**

```bash
sudo usermod -aG docker $USER
```

**Command 9:**

```bash
sudo reboot
```



### Docker Compose Setup

**Command 10:**

```bash
sudo apt-get update && sudo apt-get install docker-compose-plugin
```

###

### Install Node Pilot

{% hint style="success" %}
By installing Node Pilot, you are agreeing to our [Terms and Conditions](https://nodepilot.tech/terms-and-conditions/).
{% endhint %}

Node Pilot can install in a single copy-and-paste command. The following command will install Node Pilot, configure permissions, and open the required ports:

{% hint style="danger" %}
DO NOT INSTALL OR RUN NODE PILOT AS A ROOT USER. Always make sure you are a standard user.
{% endhint %}

```bash
cd ~ && sudo apt-get update && sudo apt-get install -y wget && wget -O ./np https://builds.decentralizedauthority.com/node-pilot/v0.18.17/np && sudo chmod +x ./np && sudo ufw allow 80 && sudo ufw allow 443 && sudo ufw allow 22 && sudo ufw allow 34416 && sudo ufw allow 19999 && sudo ufw allow 26656 && sudo ufw enable
```

### Start Node Pilot For Configuring

With Node Pilot now installed, start Node Pilot with the following command and keep the console open until the configuration steps are complete. After configuration, you will want to [start-as-daemon.md](configure/start-as-daemon.md "mention").

{% hint style="danger" %}
DO NOT RUN WITH `sudo`.
{% endhint %}

Start for configuration:

```bash
./np
```

### Update Node Pilot

Updates are currently handled manually and require a copy-and-paste command. For instructions, see [Versions](versions.md).
