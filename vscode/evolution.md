# VSCode - Evolution

## 1. History and Evolution

- Visual studio code was originaly intended to be an online code editor. Where developers can code and run their codes online. The final decision was to create a desktop application which could be usefull to code in TypeScript and C# only. Also, the developer team created a debugger for coding purposes. All this was made during the beta version of Visual Studio Code which was not open source. Some months later, Visual Studio Code was launched in a more official way, with new functionalities that lasts until today and make Visual Studio Code what it is: The most used code editor. Some of these functionalities are Extension support, the new architecture and the launched it as an open source software.
The current repository does not have the complete history of vscode, but it has information since 2016, where all the main functionalities were established.

- Chart describing the evolution of the number of lines of code in the Github repository, from the first commit to the current commit. For more details, you can see the image in https://raw.githubusercontent.com/softwaredesign-uandes/architecture-reviews/a87e21224feb88f0297065fb6c388cb08196d464/vscode/assets/vscode_graph.svg and hover the lines.
![](assets/vscode_graph.svg "Evolution of lines of code in the Github repository")

## 2. Architecture Decision Records

### ADR 1: Electron as main framework (Origin)

#### Context

- The application needed to be a desktop application
- Microsoft wanted to make a cross-platform application

#### Decision

- Use electron as main framework

#### Status: Implemented

#### Consequences

- Had to use NodeJS as backend for vscode
- Maintain further updates of the framework.

### ADR 2: Core architecture layered (Origin)

#### Context

- Needed an architecture that allow extensibility and order in the code

#### Decision

- Separate the application in 5 layers: Base, platform, editor, languages and workbench

#### Status: Implemented

#### Consequences

- Comunication between all the blocks should be implemented for being monitored
- Adapt this layer structure to electron.

### ADR 3: Monaco editor for workbench layer (Origin)

#### Context

- Needed a base editor for the application
- The editor should be able to use in a JS environment
- The editor should be basic and open source

#### Decision

- Use Monaco as Editor in the workbench layer

#### Status: Implemented

#### Consequences

- Make the workbench layer able to provide framework viewlets (Explorer, status bar, menu, etc.)
- Integrate the debugging funtion in the editor

### ADR 4: Architecture for extensions

### ADR 5: Removal of languages layer
