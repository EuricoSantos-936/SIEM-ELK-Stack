# Data Sources

### Adding Data Sources

1. **Configure Logstash to receive data** from various sources (e.g., application logs, system logs).
   *   Example Logstash input configuration:

       ```plaintext
       input {
         file {
           path => "/var/log/*.log"
           start_position => "beginning"
         }
       }
       ```
2. **Configure Filebeat to ship logs** to Logstash:
   *   Edit `filebeat.yml` to set Logstash as the output:

       ```yaml
       output.logstash:
         hosts: ["localhost:5044"]
       ```
3. **Verify data is being ingested**:
   * Check Kibana to see if the logs are being indexed and visualized correctly.
