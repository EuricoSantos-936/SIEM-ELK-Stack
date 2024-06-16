# Filebeat

### Step 1: Download and Install

1.  **Install Filebeat**:

    ```bash
    sudo apt-get update 
    sudo apt-get install filebeat
    ```

### Step 2: Configure Filebeat

1. **Edit `filebeat.yml`**:
   * Located in `/etc/filebeat/filebeat.yml`
   *   Important settings:

       ```yaml
       filebeat.inputs:
       - type: log
         enabled: true
         paths:
           - /var/log/*.log

       output.logstash:
         hosts: ["localhost:5044"]
       ```
2. **Load Kibana Dashboards**:
   *   Run the following command to load the predefined Kibana dashboards:

       ```bash
       filebeat setup --dashboards
       ```

### Step 3: Start Filebeat

1.  **Start the service**:

    ```bash
    sudo systemctl start filebeat
    sudo systemctl enable filebeat
    ```
2. **Verify Filebeat is running**:
   * Check the logs for any errors and ensure it connects to Logstash or Elasticsearch.
