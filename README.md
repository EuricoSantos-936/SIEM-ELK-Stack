# Home

## SIEM with ELK Stack

### Introduction

The objective of this project is to implement a Security Information and Event Management (SIEM) system using the ELK stack (Elasticsearch, Logstash, Kibana, FIlebeat) on Kali Linux. This system will collect, analyze, and visualize security data from various sources within a network, enabling real-time monitoring and alerting for security events.

**Technologies Used**

* **Elasticsearch**: A distributed, RESTful search and analytics engine.
* **Logstash**: A server-side data processing pipeline that ingests data from multiple sources simultaneously, transforms it, and then sends it to a “stash” like Elasticsearch.
* **Kibana**: An open-source data visualization and exploration tool for reviewing logs and time-stamped data.
* **Filebeat:** Is a lightweight shipper for forwarding and centralizing log data. Installed as an agent on your servers, Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to [Elasticsearch](https://www.elastic.co/products/elasticsearch) or [Logstash](https://www.elastic.co/products/logstash) for indexing.

### Contents

* Installation
  * Elasticsearch
  * Logstash
  * Kibana
  * Filebeat
* Configuration
  * Data Sources
  * Dashboards
* Monitoring
* Conclusion
