# VSCode — Overview

## 1. Description

### 1.1 Purpose of the system

The application is intended to be used for software development and general source code edition. Is a desktop application that works on Windows,Linux and macOS. The main characteristic of the application is its flexibility and extension availability, which makes the application very customizable, at the taste of the user.

### 1.2 System users

The application is mainly used by software developers that need a lightweight code editor. It is the most used code editor due to its flexibility and extension availability. Also, the Extension Api, that provides functionalities for making other extensions.

We can recognize 2 types of users for the application:

- Normal users: also known as developers, are those who use the application for coding purposes. They know how to use the application and use the extension system for personalization.
- Extension developers: those who use the Extension API and develop extensions for the application. They may use the application for coding purposes but are diferenciated due its capabilities on extension development.

## 2 Visualization


The following diagrams describes to levels of the architecture of the system.

![Context diagram](assets/context_diagram.png "Context diagram")
![Container diagram](assets/container_diagram.png "Container diagram")

## 3. Quality Attrbiutes

In the following section, three Quality Attributes are specified for VSCode and a QA scenario is developed for each one.

### 3.1 QA description

The 3 principal QAs for VSCode, based on our understanding of the system, are as follows:

    1. Performance: VSCode stands out for being lightweight, and seeks fastness on the coding experience. The extensions of VSCode add functionalities, however, these run in different processes, so they decrease little or nothing the software performance.

    2. Usability: being one of the most important, stands out in VSCode. First of all, the application has a huge list of keyboard shortcuts (More can be added through extensions), which accelerate user interaction. Secondly, VSCode is available for Windows, macOS and Linux, i.e., the most used operating systems in the world. Also, it is easy to understand how to use it, where everything is, etc.

    3. Flexibility: this text editor is built with extensibility in mind, which makes it very flexible, since extensions provide a lot and in a wide range of functionalities, ranging from improving the UI and UX to support a new programming language or debugging a specific runtime, among others.

### 3.2 QA scenarios

#### 3.2.3 Flexibility

1. Scenario description: A Ruby on Rails developer that uses vscode was asked by his supervisor to develop a simple javascript application using NodeJS and other tools based on javascript. The developer rapidly downloads several extensions at the same time and the extension system integrates them into the application, making the developer able to use new functionalities.

2. Source: Developer.

3. Stimulus/Event: developer requests for new functionalities.

4. Artifact: Extension system.

5. Environment: Normal operation.

6. Response: Continue to operate with new functionalities.

7. Response measure: No downtime.
