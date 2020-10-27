# OpenEdx - Overview
![openedx logo](assets/openedx.png "OpenEdx logo")
## Description

OpenEdx is an open-source Learning Management System (LMS) that allows deploying a full learning ecosystem for educational institutions that may want to offer online courses.

Along with many functionalities, OpenEdx aims to offer solutions to institutions, teachers, and students with their platform that allows course management, design, tests performing, and certificates.

One important design decision at OpenEdx is the adoption of IDAs (independently deployable application) for features that are not directly related to the core LMS functionality.

### Main Components
- **Course Browser**: simple course listing, different from the one offered at edx.org (which is proprietary)
- **XBlock Specification**: component-based architecture that allows the creation of modern online educational experiences. This specification is not coupled to the rest of OpenEdx architecture, allowing developers to design courses without needing to depend on the whole OpenEdx project.
- **OpenEdx Studio**: course authoring module that allows teams to create and update courses.
- **Discussions**: student discussion forums are managed by a ruby-written IDA that exposes endpoints to connect with the core LMS.
- **Mobile application**: iOS and Android application that allow learners to watch and read courses
- **Analytics**: OpenEdx includes an analytics pipeline that will ingest learners' events through the website and process them through a big data process to finally insert results to the LMS.
- **Background work**: the project uses Celery and RabbitMQ to manage background workers and offers an IDA to manage them.
- **Search**: ElasticSearch is used to provide searching capabilities through the platform.


## Visualization

//ToDo: Using Structurizr model the architectural structure ofthe system, and generate a Landscape/Context diagram and one ormore Container diagrams.  You must include all types of users, and allexternal services integrated.

![alt text](assets/default.png "Image Example")

## Quality Attrbiutes

//ToDo: Describe the 3 principal QAs for the project,based on your understanding of the system.  Provide 1 relevant QAscenario for each.
