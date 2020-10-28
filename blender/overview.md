# Blender - Overview

## Description

Blender is a 3D creation suite used by many for animation, videogame modeling, 3D art, architecture, and much more. Blender is a free and open source project, reaching different users with different focuses and unique ways to use the software. 

The users mainly consist of 3D artists, who use the powerful 3D engine to craft models and other assets. Another bulk of the user base can be defined as animators, who use the animation tools to create full or partial videos. Architects can be found amongst the users, using the design tools, as well as the physics engine to build simulated buildings. 

Advanced users can employ Blender's API for python to include specialized tools in order to fit their needs, as well as editing the software on their machine to modify and personalize their experience.

## Visualization

//ToDo: Using Structurizr model the architectural structure ofthe system, and generate a Landscape/Context diagram and one ormore Container diagrams.  You must include all types of users, and allexternal services integrated.

![alt text](assets/default.png "Image Example")

## Quality Attrbiutes

### QA1
Rendering large 3d model with the Eevee renderer. Performance

High priority.

Source → Users.

Stimulus/Event → Render file.

Artifact → Eevee.

Environment → normal operations.

Response → creates 2d view of model.

Response measure → Time and processing power used during render.

### QA2
Physics simulation. Users have to be able to simultate certain physical phenomena.
Performance

Medium Priority

Source → Users.

Stimulus/Event → Attempt to simultate water.

Artifact → Blender.

Environment → Normal runtime.

Response → Simulate the movement of water according to real physics.

Response measure → Time of rendering and similarity with reality.

### QA3
Cross platform usability: Blender boasts usability in windows, iOS, and Linux making it a very versitile software. A user using blender on different platforms must be able to enjoy all of it's attributes equally.

High Priority

Source → Users.

Stimulus/Event → use of different features.

Artifact → Linux.

Environment → Runtime.

Response → continue working the same as other OSs.
Response measure → speed of different functions under different OSs.ibe the 3 principal QAs for the project,based on your understanding of the system.  Provide 1 relevant QAscenario for each.
