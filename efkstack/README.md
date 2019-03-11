# EFK Logging

Kubernetes resources definitions for Elasticsearch, Fluentd, Kibana logging stack.

To install it, run 

`kubectl apply --recursive -f resources`.

This will deploy Elasticsearch and Fluentd.
Kibana can be run locally from *kibana-compose* file.
To do so, run

`docker-compose -f kibana-compose up`.

Since kibana is run locally, we need to create a proxy:

`kubectl port-forward svc/elasticsearch 9200:9200 -n kube-logging`.

Now, navigate to url http://localhost:5601 and start by creating index logstash*.

TODO:
- Add kibana deployment definition.
- Create helm chart (??).
 
