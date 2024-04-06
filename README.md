- [Components](#components)
- [JSX](#jsx)
- [Curly Braces](#curly-braces)
- [Fragments](#fragments)
- [Props](#props)
- [Children](#children)
- [Keys](#keys)
- [Rendering](#rendering)
- [Event Handling](#event-handling)
- [State](#state)
- [Controlled Components](#controlled-components)
- [Hooks](#hooks)
- [Purity](#purity)
- [Strict Mode](#strict-mode)
- [Effects](#effects)
- [Refs](#refs)
- [Context](#context)
- [Portals](#portals)
- [Suspense](#suspense)
- [Error Boundaries](#error-boundaries)

---

## Components

Components are the backbone of React. 

Under the hood, a React component is:

1. A JavaScript function 
2. That returns "markup" called JSX

---

## JSX

In older versions of React, you must use `createElement()` to generate components, but this is legacy and not used in the latest version of React.

These days, most React is written using JSX. 

JSX is not HTML, so you must use camelCase; otherwise, your React will try to render the JSX as plain HTML, which will cause side effects and unintended consequences. 

JSX is dynamic and holds states without needing to create multiple HTML pages to change the content of a page. This is why it's commonly used in state-heavy applications and is the preferred way to create interactive pages. HTML is great if your website is not changing or the changes you make don't require a lot of real-time rendering.

---

### Full Component Example

```javascript
import React from 'react';

// Functional Component
const Header = ({ title }) => {
  return <h1>{title}</h1>;
};

// Class Component
class TodoList extends React.Component {
  render() {
    return (
      <ul>
        {this.props.todos.map((todo, index) => (
          <li key={index}>{todo}</li>
        ))}
      </ul>
    );
  }
}

// Functional Component
const Footer = () => {
  return <footer>&copy; 2024 My Portfolio</footer>;
};

// Parent Component
class App extends React.Component {
  state = {
    todos: ['Learn React', 'Build Portfolio', 'Deploy to GitHub Pages']
  };

  render() {
    return (
      <div>
        <Header title="My Todo List" />
        <TodoList todos={this.state.todos} />
        <Footer />
      </div>
    );
  }
}

export default App;
```

### Components

Components are the backbone of React. 

Under the hood, a React component is essentially:

1. A JavaScript function 
2. That returns "markup" called JSX

### JSX

In older versions of React, you must use `createElement()` to generate components, but this is legacy and not used in the latest version of React.

These days, most React is written using JSX. 

JSX is not HTML, so you must use camelCase; otherwise, your React will try to render the JSX as plain HTML, which will cause side effects and unintended consequences. 

JSX is dynamic and holds states without needing to create multiple HTML pages to change the content of a page. This is why it's commonly used in state-heavy applications and is the preferred way to create interactive pages. HTML is great if your website is not changing or the changes you make don't require a lot of real-time rendering.

### Full Component Example

```javascript
import React from 'react';

// Functional Component
const Header = ({ title }) => {
  return <h1>{title}</h1>;
};

// Class Component
class TodoList extends React.Component {
  render() {
    return (
      <ul>
        {this.props.todos.map((todo, index) => (
          <li key={index}>{todo}</li>
        ))}
      </ul>
    );
  }
}

// Functional Component
const Footer = () => {
  return <footer>&copy; 2024 My Portfolio</footer>;
};

// Parent Component
class App extends React.Component {
  state = {
    todos: ['Learn React', 'Build Portfolio', 'Deploy to GitHub Pages']
  };

  render() {
    return (
      <div>
        <Header title="My Todo List" />
        <TodoList todos={this.state.todos} />
        <Footer />
      </div>
    );
  }
}

export default App;
```

### Button
```javascript


import React from 'react';

const Button = ({ onClick, children, className }) => {
  return (
    <button className={className} onClick={onClick}>
      {children}
    </button>
  );
};

export default Button;
```
### Input
```javascript

import React from 'react';

const Input = ({ type, value, onChange, placeholder, className }) => {
  return (
    <input
      type={type}
      value={value}
      onChange={onChange}
      placeholder={placeholder}
      className={className}
    />
  );
};

export default Input;
```

### React Props Example

In React, props (short for properties) allow you to pass data from parent components to child components. This is essential for creating reusable and modular components.

Consider the following example:

```javascript
import React from 'react';

// Child component
const Greeting = (props) => {
  return <h1>Hello, {props.name}!</h1>;
};

// Parent component
const App = () => {
  return (
    <div>
      <Greeting name="Alice" />
      <Greeting name="Bob" />
      <Greeting name="Charlie" />
    </div>
  );
};

export default App;
```
