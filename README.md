# Template Project: React + TypeScript

## NOTICE

You cannot use imports / exports here, becuase this project is bundled thanks to the typescript compiler. So to use multiple folders, you will have to use triple slash directives which will give you 100% access to the mentionned file. You don't need to import React and ReactDOM, it is already done behind the hood. 

Example:

```js
// create-react-app
import React, { useState } from 'react';
const [state, setState] = useState();
```

```js
// my react template
// no need to import
const [state, setState] = React.useState();
```

Example 2:

```txt
File tree:
src/
├─ components/
│  ├─ Component.tsx
├─ App.tsx
```

With create-react-app:

```js
// App.tsx
import React from 'react';
import ReactDOM from 'react-dom';
import { Component } from './components/Component.tsx';

const App: React.FC = (props): JSX.Element => {
   return (
      <div>
        <p>Hello world!</p>
        <Component />
      </div>
   );
};

ReactDOM.render(<App />, document.getElementById("root"));
```

With my react template:

```js
// App.tsx
/// <reference path="./components/Component.tsx" />

const App: React.FC = (props): JSX.Element => {
   return (
      <div>
        <p>Hello world!</p>
        <Component />
      </div>
   );
};

ReactDOM.render(<App />, document.getElementById("root"));
```
