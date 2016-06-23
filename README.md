# Supported tags and respective `Dockerfile` links

* [`1.1`, `latest` (_1.1/Dockerfile_)](https://github.com/roistat/docker-clickhouse/blob/master/1.1/Dockerfile)

![Clickhouse Logo](https://habrastorage.org/files/d9b/066/e61/d9b066e61e1f480a977d889dc03ded99.png)

# What is Clickhouse?

ClickHouse manages extremely large volumes of data in a stable and sustainable manner. It currently
powers Yandex.Metrica, world’s second largest web analytics platform, with over 13 trillion database
records and over 20 billion events a day, generating customized reports on-the-fly, directly from
non-aggregated data. This system was successfully implemented at CERN’s LHCb experiment to store and
process metadata on 10bn events with over 1000 attributes per event registered in 2011.

# How to use this image

### start a clickhouse instance

`$ docker run -p 8123:8123 -p 9000:9000 roistat/clickhouse`

### connect to clickhouse via tcp client

`$ docker exec -it {container_name} clickhouse-client`

### docker-compose

```yaml
version: '2'
 services:
   clickhouse:
     image: roistat/clickhouse
     ports:
       - 9000:9000
       - 8123:8123
     volumes:
       - ./clickhouse-config.xml:/etc/clickhouse-server/config.xml
       - ./clickhouse-data:/opt/clickhouse/data
```

You can download sample clickhouse config from [here](https://raw.githubusercontent.com/roistat/docker-clickhouse/master/1.1/config.xml).