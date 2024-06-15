# Elasticsearch

## Elasticsearch Installation

### Step 1:  Install

1. Download and install the public signing key:

```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg
```

2. Add the Elastic repository to the sources list:

```
echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list
```

3. Update the package list and install Elasticsearch:

```
sudo apt update
sudo apt install elasticsearch
```

4. Configure Elasticsearch by editing the `elasticsearch.yml` file located in the `/etc/elasticsearch` directory.

&#x20;\- Open configuration file:

```
sudo nano /etc/elasticsearch/elasticsearch.yml
```

&#x20;\- Basic configuration

```
# Cluster name (customize according to your needs)
cluster.name: my-elk-cluster

# Node name (customize according to your needs)
node.name: node-1

# Network settings
network.host: 0.0.0.0
http.port: 9200

# Discovery settings (useful for single-node setup)
discovery.type: single-node

# Path to data and logs (make sure the directories exist and are writable)
path.data: /var/lib/elasticsearch
path.logs: /var/log/elasticsearch

# X-Pack security settings (optional, but recommended for production)
xpack.security.enabled: true
xpack.security.transport.ssl.enabled: true
xpack.security.transport.ssl.verification_mode: certificate
xpack.security.transport.ssl.keystore.path: /path/to/your/keystore.p12
xpack.security.transport.ssl.truststore.path: /path/to/your/truststore.p12

# Enable TLS/SSL for HTTP layer (optional, but recommended for production)
xpack.security.http.ssl.enabled: true
xpack.security.http.ssl.keystore.path: /path/to/your/keystore.p12
xpack.security.http.ssl.truststore.path: /path/to/your/truststore.p12
```

&#x20;\- Save and close the file `CTRL + X`

5. Start and enable Elasticsearch:
6. ####

```
sudo systemctl start elasticsearch
```

### Step 3:  Start Elasticsearch
