# ElasticSearch - Overview

## Description

Elasticsearch is a RESTful API, a real-time distributed search and analytics engine with high availability. It is used for full-text search, structured search, analytics, or all three in combination.
The client can index the data, meaning that Elasticsearch indexes it in the document-oriented data store (based in Apache Lucene). 
The client can also use this datastore as it primary database. Then, the client can search in the indexed data through JSONs queries.
There are two types of users: the administrator user, who configures it and indexes the data, and sets who the search client is. Then the main user is the search client, who uses Elasticsearch as the search engine it is. 
This client may not necessarily be a person, as it Elasticsearch is meant to be used by other applications and services.

## Visualization
Container Diagram
![alt text](assets/ContainerDiagram.png "Container Diagram")
Context Diagram
![alt text](assets/ContextDiagram.png "Context Diagram")

## Quality Attrbiutes

//ToDo: Describe the 3 principal QAs for the project,based on your understanding of the system.  Provide 1 relevant QAscenario for each.
