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

4. If you need configure Elasticsearch edit the `elasticsearch.yml` file located in the `/etc/elasticsearch` directory.

### Step 2:  Start and enable Elasticsearch

```
sudo systemctl start elasticsearch
sudo systemctl enable elasticsearch
```

## Step 3: Verify if Elasticsearch is running

```
curl -X GET "localhost:9200/"
```

You should see a response with information about your Elasticsearch cluster

### Step 4: Basic Configuration

1. **Edit `elasticsearch.yml`**:
   * Located in `/etc/elasticsearch/elasticsearch.yml`
   *   Important settings:

       ```yaml
       cluster.name: my-cluster
       node.name: node-1
       network.host: 0.0.0.0
       ```
2. **Set memory limits**:
   *   Edit `jvm.options` file to set appropriate memory limits:

       ```plaintext
       -Xms1g
       -Xmx1g
       ```
3.  **Restart Elasticsearch** to apply changes:

    ```bash
    sudo systemctl restart elasticsearch
    ```
