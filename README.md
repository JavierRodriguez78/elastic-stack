# 📶 Elastic Stack Docker + Sample Go App

Elastic Stack which includes **Elasticsearch**, **Kibana**, **Filebeat** and **Metricbeat**. It comes with a very simple Go application that publishes a tiny HTTP API. **Go** app connects to a **MySQL** database. Also there's an **HA Proxy** that acts as the load balancer of the Go App to allow scale up/down the app containers.

[![Actions Status](https://github.com/rubencougil/elastic-stack/workflows/Build/badge.svg)](https://github.com/rubencougil/elastic-stack/actions)

![Screenshot 2020-02-24 at 11 39 09](https://user-images.githubusercontent.com/1073799/75146132-b1061500-56fa-11ea-8776-94d324e4456a.png)

## How to run it?

For spinning up the stack:

`docker-compose up -d` 

After all services are running, you can use following Go application endpoints to generate random data (:8080 is the exposed port of th HA Proxy connected to Go application instances):

* `curl http://localhost:8080/`
* `curl http://localhost:8080/create -d {}`


To scale up/down Go application:

`docker-compose scale app --replicas 3`
