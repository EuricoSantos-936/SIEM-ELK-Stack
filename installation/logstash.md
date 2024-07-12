# Logstash

## Step 1: Install Logstash

1. Install Logstash:

```
sudo apt update
sudo apt install logstash
```

### Step 2: Configure Logstash

1.  **Create a configuration file**:

    * Create `logstash.conf` with the following content:

    ```plaintext

    input {
      beats {
        port = 5044
      }
    }

    output {
      if [@metadata][pipeline] {
     elasticsearch {
       hosts = ["localhost:9200"]
       manage_template = false
       index = "%{[@metadata][beat]}-%{[@metadata][version]}-%{+YYYY.MM.dd}"
       pipeline = "%{[@metadata][pipeline]}"
     }
      } else {
     elasticsearch {
       hosts = ["localhost:9200"]
       manage_template = false
       index = "%{[@metadata][beat]}-%{[@metadata][version]}-%{+YYYY.MM.dd}"
     }
      }
    }
    ```
2. **Save the configuration file** in the appropriate directory:`/etc/logstash/conf.d/logstash.conf`
3. Testing configuration of Logstash

```
sudo -u logstash /usr/share/logstash/bin/logstash --path.settings /etc/logstash -t
```

### Step 3: Start Logstash

1.  **Start the service**:

    ```bash
    sudo systemctl start logstash
    sudo systemctl enable logstash
    ```
2. **Verify Logstash is running**:
   * Check the logs for any errors and ensure it connects to Elasticsearch.
