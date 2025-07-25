# Elastic Stack Environment

This project sets up an Elastic Stack environment on a **Linux RHEL 9.6** system.

## Requirements
- Docker latest version installed  

## Configure de vm.max_map_count
Setting this configuration in your Linux environment is essential in order for the Elastic to run properly. To configure vm.max_map_count run the following commands:
```bash
sudo sysctl -w vm.max_map_count=262144
sudo sysctl -p
```

## Prepare Environment Folders

Before running the stack, execute the following commands to create and configure the necessary directories:

```bash
mkdir certs elasticdata elasticlogs backups

cd elasticdata
mkdir data2volume datavolume filebeatdata logstashdata mastervolume metricbeatdata
chmod g+rwx data2volume/ datavolume/ filebeatdata/ logstashdata/ mastervolume/ metricbeatdata/
sudo chgrp 0 data2volume/ datavolume/ filebeatdata/ logstashdata/ mastervolume/ metricbeatdata/
cd ..

cd elasticlogs
mkdir coordlogs data2logs datalogs masterlogs
chmod g+rwx coordlogs data2logs datalogs masterlogs
sudo chgrp 0 coordlogs data2logs datalogs masterlogs
cd ..

chmod g+rwx backups certs
sudo chgrp 0 backups certs
```

## Run the Environment

Start the Elastic Stack containers:

```bash
sudo docker compose -f compose.yml up -d
```

## Run Python Test App

To deploy the Python test application:

```bash
sudo docker compose -f app.yml up -d
```

## Stop All Services

To stop both the app and environment:

```bash
sudo docker compose -f app.yml down
sudo docker compose -f compose.yml down
```
