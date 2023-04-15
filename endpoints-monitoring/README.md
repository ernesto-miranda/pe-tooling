

## Getting Started
These instructions will get you a copy of the project up and running on your local machine.

## Prerequisites
What things you need to install the software and how to install them

Docker
Docker Compose
## Installing
A step by step series of examples that tell you how to get a development env running

1. Clone this repository
2. Open the terminal and navigate to the project's root directory
3. Run docker-compose up command
4. Open http://localhost:5601 in your browser to access OpenSearch Dashboards
5. Open http://localhost:3000 in your browser to access Grafana
6. (Optional) Modify the configurations in heartbeat.yml or logstash-pipeline according to your needs
## Services
opensearch-node1: OpenSearch node 1
opensearch-node2: OpenSearch node 2
logstash: Logstash with OpenSearch output plugin
heartbeat: Heartbeat for monitoring services
opensearch-dashboards: OpenSearch Dashboards
grafana: Grafana for visualizing data
## Ports
9200: OpenSearch REST API port
9600: Required for Performance Analyzer
5044: Logstash input port
5601: OpenSearch Dashboards port
3000: Grafana port
# Volumes
opensearch-data1: OpenSearch data for node 1
opensearch-data2: OpenSearch data for node 2
grafana-data: Grafana data
## Configuration
OpenSearch
`cluster.name`: Cluster name
`node.name`: Node name
`discovery.seed_hosts`: Seed hosts for discovery
`cluster.initial_cluster_manager_nodes`: Initial cluster manager nodes
`bootstrap.memory_lock`: Disable swapping
`OPENSEARCH_JAVA_OPTS`: Java heap size
Logstash
`./src/logstash-pipeline`: Logstash pipeline configuration
Heartbeat
`./src/heartbeat.yml`: Heartbeat configuration
OpenSearch Dashboards
`OPENSEARCH_HOSTS`: OpenSearch hosts
Grafana
`/var/lib/grafana`: Grafana data
## Troubleshooting
If any container fails to start, run `docker-compose logs <container_name>` to view its logs and troubleshoot the issue.
Make sure that the ports used by the containers are not already in use by other applications.
If OpenSearch Dashboards fail to connect to OpenSearch nodes, check the OPENSEARCH_HOSTS environment variable and make sure that it points to the correct hosts.
