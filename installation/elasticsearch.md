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

### Step 2:  Start and enable Elasticsearch

```
sudo systemctl start elasticsearch
sudo systemctl enable elasticsearch
```
