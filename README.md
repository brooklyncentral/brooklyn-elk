# Apache Brooklyn :: ELK

An example Apache Brooklyn application demonstrating an ELK stack (Elasticsearch, Logstash, Kibana)

This example demonstrates the deployment of an ELK Stack (Elasticsearch, Logstash and Kibana), using the provided blueprint to deploy, install, run and manage all three. Briefly, the component parts are:

* Elasticsearch: A clustered search engine
* Logstash: Collects, parses and stores logs. For our example it will store logs in Elasticsearch
* Kibana: A web front end to Elasticsearch

For more about the ELK stack, please see the documentation [here](https://www.elastic.co/).


## The Blueprints
-----------------

There are four blueprints that make up this application. Each of them are used to add one or more catalog items to Brooklyn. You can find them below:

* [Elasticsearch](elasticsearch/catalog/elasticsearch/elasticsearch.bom)
* [Logstash](logstash/catalog/logstash/logstash.bom)
* [Kibana](kibana/catalog/kibana/kibana.bom)
* [ELK](catalog.bom) (WIP)

## Adding ELK to brooklyn
-------------------------

```bash
br catalog add https://raw.githubusercontent.com/brooklyncentral/brooklyn-elk/master/catalog.bom
```
 

## Examples
-----------

### [Elasticsearch](elasticsearch/examples/elasticsearch.example.yaml)
### [Kibana](kibana/examples/kibana.example.yaml)
### [Logstash](logstash/examples/logstash.example.yaml)
