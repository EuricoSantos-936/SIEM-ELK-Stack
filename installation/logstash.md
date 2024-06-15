# Logstash

## Step 1: Install Logstash

1. Install Logstash:

```
sudo apt update
sudo apt install logstash
```

2. If you need configure Logstash edit the `logstash.yml` file located in the `/etc/logstash` directory.

## Step 2: Start and enable Logstash

```
sudo systemctl start logstash
sudo systemctl enable logstash
```

