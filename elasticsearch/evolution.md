# ElasticSearch - Evolution

## 1. History and Evolution

Even from the begining, Elasticsearch was a search engine with different features:

+ Distributed and Highly Available Search Engine.
  + Each index is fully sharded with a configurable number of shards.
  + Each shard can have one or more backups.
  + Read / Search operations performed on either primary or backup shards.
+ Multi Tenant with Multi Types.
  + Support for more than one index.
  + Support for more than one type per index.
  + Index level configuration (number of shards, index storage, …).
+ Various set of APIs
  + HTTP RESTful API
  + Native Java API.
  + All APIs perform automatic node operation rerouting.
+ Document oriented
  + No need for upfront schema definition.
  + Schema can be defined per type for customization of the indexing process.
+ Reliable, Asynchronous Write Behind for long term persistency.
+ (Near) Real Time Search.
+ Built on top of Lucene
  + Each shard is a fully functional Lucene index
  + All the power of Lucene easily exposed through simple configuration / plugins.
+ Per operation consistency
  + Single document level operations are atomic, consistent, isolated and durable.
+ Open Source under Apache 2 License.

And now, it hasn't really change it's main functionality, but has added quality ones. The list of actual features is the next one:

+ Scalability and resiliency
  + Clustering and high availability
  + Automatic node recovery
  + Automatic data rebalancing
  + Horizontal scalability
  + Rack awareness
  + Cross-cluster replication
  + Cross-datacenter replication
+ Management
  + Index lifecycle management
  + Hot-warm architecture
  + Frozen indices
  + Snapshot lifecycle management
  + Snapshot and restore
  + Source-only snapshots
  + Data rollups
  + Data streams
  + Transforms
  + Upgrade Assistant API
  + API key management
+ Security
  + Elasticsearch secure settings
  + Encrypted communications
  + Encryption at rest support
  + Role-based access control (RBAC)
  + Attribute-based access control (ABAC)
  + Field- and document-level security
  + Audit logging
  + IP filtering
  + Security realms
  + Single sign-on (SSO)
  + Third-party security integration
+ Alerting
  + Highly available, scalable alerting
  + Notiﬁcations via email, Slack, PagerDuty, ServiceNow, or webhooks
+ Clients
  + Language clients
  + Elasticsearch DSL
  + Elasticsearch SQL
  + Event Query Language (EQL)
  + JDBC client
  + ODBC client
  + Tableau Connector for Elasticsearch
  + CLI tools
+ REST APIs
  + Document APIs
  + Search APIs
  + Aggregations APIs
  + Ingest APIs
  + Management APIs
+ Integrartions
  + Elasticsearch-Hadoop
  + Apache Hive
  + Apache Pig
  + Apache Spark
  + Apache Storm
  + Business intelligence (BI)
  + Plugins and integrations
+ Deployment
  + Download and install
  + Elastic Cloud
  + Elastic Cloud Enterprise
  + Elastic Cloud on Kubernetes
  + Helm Charts
  + Docker containerization
  
## 2. Architecture Decision Records
