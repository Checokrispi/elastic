# elastic

Before begining run de following commands to create de folders for the environment:
```bash
mkdir certs elasticdata elasticlogs backups
cd elasticdata
mkdir data2volume datavolume filebeatdata logstashdata mastervolume metricbeatdata
chmod g+rwx data2volume/ datavolume/ filebeatdata/ logstashdata/ mastervolume/ metricbeatdata/
sudo chgrp 0 data2volume/ datavolume/ filebeatdata/ logstashdata/ mastervolume/ metricbeatdata/
cd ..
cd elasticlogs
mkdir coordlogs  data2logs  datalogs  masterlogs
chmod g+rwx coordlogs  data2logs  datalogs  masterlogs
sudo chgrp 0 coordlogs  data2logs  datalogs  masterlogs
cd ..
chmod g+rwx backups certs
sudo chgrp 0 backups certs
```



