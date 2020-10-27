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

## Quality Attributes

### Availability
As OpenEdx offers a platform for students, it’s crucial to have access to course information to have them study. Also, as users will be taking exams, the platform must be able to receive and process successfully each exam attempt.

### Scalability
To be able to host many courses along it’s students, the platform must be able to serve traffic spikes on certain times (exams) and low traffic periods as well.

### Security
Being a MOOC-ready (massive open online course) software, data integrity is important to avoid malicious attackers from manipulating sensible data such as course grades, certificates and transaction data.

## Quality Attributes Scenarios
### Availability

#### Scenario description
A huge concurrent traffic spike is seen during a critical exam period
#### Source
Legit and malicious requests
#### Stimulus
Navigate through course data while in exam
#### Artifact
Student Portal
#### Environment
Under heavy load conditions.
#### Response
Legit users requests are served successfully
#### Response measure
<1% requests served with 503 error

### Scalability

#### Scenario description
A huge concurrent traffic spike is seen during a critical exam period.

#### Source
Students doing exams.

#### Stimulus
Navigate through portal while taking exam.

#### Artifact
Application server.

#### Environment
Under heavy load conditions.

#### Response
Requests are served in a timely manner.

#### Response measure
Requests first packet served in less than 200ms.

### Security

#### Scenario description
A rogue student trying to modify his grades in order to pass a course.

#### Source 
Authorized user with malicious intent.

#### Stimulus
Tries to modify his grades.

#### Artifact
Data within the system/his grades.

#### Environment
Under normal conditions.

#### Response
System doesn’t modify the grades.

#### Response measure
Forbidden status code served to user and event logged to log analytics component.

