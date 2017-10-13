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

### [For contributors] Release Process

#### Snapshot Release

In order to release a new snapshot version to Sonatype:

```bash
mvn deploy -DdeployTo=sonatype
```

#### Official Relesae

1. Create a new branch, e.g. `release/2.0.1`, and checkout that branch

2. Update the version running the command below (and double-check that pom.xml was correctly updated):

   ```bash
   GA_VERSION=2.0.1
   ~/repos/brooklyn/brooklyn-dist/release/change-version.sh BROOKLYN_ELK ${GA_VERSION}-SNAPSHOT ${GA_VERSION}
   ```

3. Confirm it builds: `mvn clean install`

4. Push release to sonatype, following the normal Sonatype process:

   ```bash
   mvn deploy -DdeployTo=sonatype
   ```