1. What is React Flow?
   React Flow is a library for building node-based applications. with features such as:

- Add, remove, resize, drag and drop node
- Zooming and paining function
- Custom node and edge
- Sub flows
- handle events:

  - select a node/edge (onNodesChange/onEdgesChange)
  - drag a node (onNodesChange)
  - drop (onDrop)
  - zoom, ...

  - node: onClick, dragging, onDrop, onNodesChange (drag or select a node)
  - edge: onConnectEnd, onEdgesChange
  - connection: onConnect

2. What are the benefits of using React Flow in a React project?

- Supports custom node and edge
- Provides a fully interactive node-based user interface
- Simple setup and installation
- Detailed document
- Upgrade to React Flow Pro (auto/force layout, expand and collapse, workflow builder...)

3. How does React Flow differ from other flowchart libraries?
4. How do you integrate React Flow into a React project?
5. Can you explain the basic architecture of React Flow?
   The basic architecture of React Flow includes:

- Graph component
- Node and Edge components
- Event handlers
- Layout algorithms
- Styling

5. What are some of the features provided by React Flow?
6. How do you handle user events in React Flow?
7. What are some of the limitations of React Flow?

- reactflow/core:

- reactflow/background: The Background component comes with three background variants: dots, lines and cross.
- reactflow/controls: The controls component contains a panel with a zoom-in, zoom-out, fit-view and a lock/unlock button
- reactflow/minimap: adds an interactive Minimap to React Flow that shows the whole graph
- reactflow/node-toolbar: renders a toolbar that is attached to a node
- reactflow/node-resizer: can be used to add a resize functionality to your node

* State

- node[]
- edge[]
- onNodesChange
- onEdgesChange
- minZoom ....

1.

- 3.5 nam kinh nghiem frontend developer:

- mid-level developer

2.

- reactjs, nextjs
- MUI, antdesign, tailwind, styled-component
- redux
- axios
- react-flow (jsplumb)

3. DnD project

- nextjs + MUI
- axios
- redux
- react-flow

* responsibilities:

- Create UI by using ReactFlow: drag and drop module code to build smart contract
- integrate elkjs with React Flow for more advanced tree layouts: calculate node's position and sub flow
- @monaco-editor: build editor code for solidity language (The Monaco Editor is the code editor that powers VS Code)
