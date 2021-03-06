# OpenEdx - DeepDive

One of the core containers of OpenEdx is the LMS (Learning Management System). The most essential feature for Edx is the component that allow users to explore courses, study and learn. Through the LMS Container, several components such as XBlock Renderer allows to show XBlock-formatted course data in a given course sections and sub-sections.

The design of the courses itselves and their XBlocks content is done on Studio component, which is dedicated to educational content and course creation.

## Component Diagram
![Component Diagram](assets/lms_container_component_diagram.png "LMS Container Component Diagram")

## Relevant Workflows

### Students uses course material
In order to access course materials, an student must get to the course browser in the Edx portal. From that point the user will be able to see the courses that already have access (or in 'enrolled' status on project's terminology) along other courses. Each course will show a sections index, which at the same time may have subsections. Each section or subsection should be composed of a single or several XBlocks which contain the course material, along other functionalities such as a discussion board for a certain topic.

![Dynamic Diagram](assets/student_browses_course.png "Dynamic Diagram of how the student gets to see the course material")


### Student sends comment through xblock-inserted discussion box
The student has to access the course browser, which then retrieves courses list from courses controller, which fetches course data from the sections controller which in turn displays the current course and section through the xblock renderer, then fetches the discussions from Discussions, then the discussions are rendered and displayed to the student which in turns makes a comment and submits it by sending it to the discussions.

![Dynamic Diagram Two](assets/studentCommentWorkflow.PNG "Student comment Workflow")


### Instructor creates course
The instructor creates the course using Studio, which in turns sends its data to the Sections controllers, adds the course to the course list in the Course Controller and creates its own interface in the XBlock Renderer.

![Dynamic Diagram Three](assets/InstructorCreatesCourseWorkflow.PNG "Instructor creates course Workflow")