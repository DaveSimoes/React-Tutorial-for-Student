


![React Tutorial Picture](https://www.apac-insider.com/wp-content/uploads/2023/01/image1-2.jpg)
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=for-the-badge&logo=react-router&logoColor=white)
![Redux](https://img.shields.io/badge/redux-%23593d88.svg?style=for-the-badge&logo=redux&logoColor=white)
![Webpack](https://img.shields.io/badge/webpack-%238DD6F9.svg?style=for-the-badge&logo=webpack&logoColor=black)
![React Hook Form](https://img.shields.io/badge/React%20Hook%20Form-%23EC5990.svg?style=for-the-badge&logo=reacthookform&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Facebook](https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)

<div  align= "center">
<h3><code>Bem-Vindo React Helpful Tutorial - BR</code> Sua mais nova ferramenta de aprendizagem
</div>



# 📋 Índice
  
1.  [Introduction to React](#introduction-to-react)
2.  [JSX](#jsx)
3.  [Functional Components](#functional-components)
4.  [Class Components](#class-components)
5.  [Props](#props)
6.  [State](#state)
7.  [Lifecycle Methods](#lifecycle-methods)
8.  [Events Handling](#events-handling)
9.  [React Hooks](#react-hooks)
10. [Controlled Components](#controlled-components)
11. [Error Boundaries](#error-boundaries)
12. [Higher Order Components](#higher-order-components)
13. [Rendering Lists](#rendering-lists)
14. [Context API](#context-api)
15. [Keys](#keys)
17. [Forms](#forms)
18. [Styling in React](#styling-in-react)
19. [Render Props](#render-props)
20. [CSS Modules](#css-modules)
21. [Real World Examples](#real-world-examples)  
22. [Best Practices](#best-practices)
23. [Additional Topics](#additional-topics)
24. [License to use](#license-to-use)

## Introdução ao React
React is a JavaScript library for creating user interfaces. It enables developers to build reusable UI components and efficiently update the DOM by using a virtual DOM for optimal performance.
`create-react-app`
 
```
# Terminal
npx create-react-app my-react-app
cd my-react-app
npm start
```

## JSX
JSX is a syntax extension for JavaScript that looks similar to XML or HTML. It allows developers to write HTML elements and components in a more concise and readable manner within JavaScript files.

```// src/App.js
import React from 'react';

function App() {
  return (
    <div>
      <h1>Hello, React!</h1>
    </div>
  );
}

export default App;
```

## Functional Components
Class components are ES6 classes that extend the React Component. 
They can maintain and manage local state and have access to lifecycle methods, making them more feature-rich than functional components.
```
import React from 'react';

const FunctionalComponent = () => {
  return <p>This is a functional component.</p>;
}

export default FunctionalComponent;
```

## Class Components
Class components are ES6 classes that extend the React Component.
They can maintain and manage local state and have access to lifecycle methods, making them more feature-rich than functional components.

```
import React, { Component } from 'react';

class ClassComponent extends Component {
  render() {
    return <p>This is a class component.</p>;
  }
}

export default ClassComponent;
```

## Props
Props are a way of passing data from a parent component to a child component in React. They are immutable and provide a way of making components dynamic and reusable.
```
import React from 'react';

const PropsExample = (props) => {
  return <p>{props.message}</p>;
}

export default PropsExample;

```

## State
 State React represents the changing state of a component. This allows components to manage and update their own data, resulting in dynamic and interactive user interfaces.
 ```
import React, { Component } from 'react';

class StateExample extends Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Increment
        </button>
      </div>
    );
  }
}

export default StateExample;

 ```


## Lifecycle Methods
Lifecycle methods são métodos especiais em componentes de classe que são invocados em diferentes fases do ciclo de vida de um componente. componentDidMount é um método de ciclo de vida comummente utilizado, executado depois de um componente ser renderizado no DOM.
```
import React, { Component } from 'react';

class LifecycleExample extends Component {
  componentDidMount() {
    console.log('Component is mounted!');
  }

  render() {
    return <p>Lifecycle Example</p>;
  }
}

export default LifecycleExample;
```




## Events Handling
O React utiliza o camelCase para o tratamento de eventos. Podem ser definidas funções para tratar eventos como cliques, alterações, etc., proporcionando interatividade aos componentes.

```
import React from 'react';

const EventHandlingExample = () => {
  const handleClick = () => {
    alert('Button clicked!');
  }

  return (
    <button onClick={handleClick}>
      Click me
    </button>
  );
}

export default EventHandlingExample;

```

##  React Hooks

React Hooks are functions that allow functional components to manage state and side effects.
They were introduced in React 16.8 and provide a more concise way of working with state and lifecycle methods in functional components.

```

import React, { useState } from 'react';

const UseStateExample = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>
        Increment
      </button>
    </div>
  );
}

export default UseStateExample;
```` 



## Controlled Components

Controlled components in React have inputs and their state controlled by React. They receive their current value and the onChange handler as props, making them controlled by React and not by the DOM.

  ```
import React, { useState } from 'react';

const ControlledComponent = () => {
  const [inputValue, setInputValue] = useState('');

  const handleChange = (e) => {
    setInputValue(e.target.value);
  }

  return (
    <input
      type="text"
      value={inputValue}
      onChange={handleChange}
      placeholder="Type here"
    />
  );
}

export default ControlledComponent;
```

## Error Boundaries
Error boundaries are React components that detect JavaScript errors anywhere in the child component tree and log those errors, present a fallback UI or take other action.
```
import React, { Component } from 'react';

class ErrorBoundary extends Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  componentDidCatch(error, errorInfo) {
    logErrorToMyService(error, errorInfo);
  }

  render() {
    if (this.state.hasError) {
      return <p>Something went wrong.</p>;
    }

    return this.props.children;
  }
}

export default ErrorBoundary;
```

## Higher Order Components

Higher Order Components (HOCs) are functions that take a component and return a new component with additional functionality. They are a way of reusing the component's logic.

```
import React from 'react';

const WithLogger = (WrappedComponent) => {
  return class extends React.Component {
    componentDidMount() {
      console.log('Component is mounted!');
    }

    render() {
      return <WrappedComponent {...this.props} />;
    }
  };
}

export default WithLogger;

// Usage
import React from 'react';
import WithLogger from './WithLogger';

const MyComponent = () => {
  return <p>My Component</p>;
}

const EnhancedComponent = WithLogger(MyComponent);
```

## Rendering Lists
React provides the `map` function to render lists of items dynamically. Each item in the array is mapped to a React element, making it easier to render dynamic content.
```
import React from 'react';

const RenderingList = () => {
  const items = ['Item 1', 'Item 2', 'Item 3'];

  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>{item}</li>
      ))}
    </ul>
  );
}

export default RenderingList;
```

## Context API

The Context API in React offers a way of transmitting data through the component tree without having to pass props manually at each level. It's useful for sharing values such as themes or authentication status.
```
import React from 'react';

const ThemeContext = React.createContext('light');

export default ThemeContext;
```

```
import React, { useContext } from 'react';
import ThemeContext from './ThemeContext';

const ThemedComponent = () => {
  const theme = useContext(ThemeContext);

  return <p style={{ color: theme === 'light' ? 'black' : 'white' }}>Themed Component</p>;
}

export default ThemedComponent;

```

## Keys

Keys in React help identify which items have been changed, added or removed. They should be unique within the list and help React with efficient updates.
```
import React from 'react';

const KeysExample = () => {
  const data = [
    { id: 1, name: 'Item 1' },
    { id: 2, name: 'Item 2' },
    { id: 3, name: 'Item 3' },
  ];

  return (
    <ul>
      {data.map(item => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
}

export default KeysExample;
```

## Forms 

Handling forms in React involves managing form data using state and handling form submission via event handlers. Controlled components are used to synchronize form elements with React's state.

```
import React, { useState } from 'react';

const FormExample = () => {
  const [formData, setFormData] = useState({ username: '', password: '' });

  const handleChange = (e) => {
    setFormData({
      ...formData,
      [e.target.name]: e.target.value,
    });
  }

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log('Form submitted:', formData);
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Username:
        <input
          type="text"
          name="username"
          value={formData.username}
          onChange={handleChange}
        />
      </label>
      <label>
        Password:
        <input
          type="password"
          name="password"
          value={formData.password}
          onChange={handleChange}
        />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
}

export default FormExample;
```

## Styling in React
Inline Styles: 
React allows you to style components using inline styles, where styles are defined as objects and applied directly to elements.

```
import React from 'react';

const InlineStyleExample = () => {
  const styles = {
    color: 'blue',
    fontSize: '18px',
  };

  return <p style={styles}>Styled with inline styles</p>;
}

export default InlineStyleExample;
 ```

## Render Props

Render Props is a technique for sharing code between React components using a prop whose value is a function. This allows for the dynamic composition of components.

```
import React, { useState } from 'react';

const MouseTracker = ({ render }) => {
  const [position, setPosition] = useState({ x: 0, y: 0 });

  const handleMouseMove = (event) => {
    setPosition({ x: event.clientX, y: event.clientY });
  }

  return (
    <div style={{ height: '100vh' }} onMouseMove={handleMouseMove}>
      {render(position)}
    </div>
  );
}

export default MouseTracker;
```
```
// Usage
import React from 'react';
import MouseTracker from './MouseTracker';

const App = () => {
  return (
    <MouseTracker
      render={(position) => (
        <p>
          Mouse position: {position.x}, {position.y}
        </p>
      )}
    />
  );
}

export default App;
```

## CSS Modules

CSS Modules help define the scope of styles for a specific component, avoiding global style conflicts. Each component can have its own CSS module with locally scoped styles.

```
.myComponent {
  color: green;
}
```

```
import React from 'react';
import styles from './CSSModulesExample.module.css';

const CSSModulesExample = () => {
  return <p className={styles.myComponent}>Styled with CSS Modules</p>;
}

export default CSSModulesExample;
```

## Real World Examples
### example 1: To-Do List Application

Features:

* Adding and removing tasks
* Marking tasks as completed
* Filtering tasks (completed/incomplete)
  
 ```
import React, { useState } from 'react';

const TodoApp = () => {
  const [tasks, setTasks] = useState([]);
  const [newTask, setNewTask] = useState('');

  const addTask = () => {
    setTasks([...tasks, { text: newTask, completed: false }]);
    setNewTask('');
  };

  const toggleTask = (index) => {
    const updatedTasks = [...tasks];
    updatedTasks[index].completed = !updatedTasks[index].completed;
    setTasks(updatedTasks);
  };

  const removeTask = (index) => {
    const updatedTasks = [...tasks];
    updatedTasks.splice(index, 1);
    setTasks(updatedTasks);
  };

  return (
    <div>
      <input
        type="text"
        value={newTask}
        onChange={(e) => setNewTask(e.target.value)}
      />
      <button onClick={addTask}>Add Task</button>
      <ul>
        {tasks.map((task, index) => (
          <li key={index}>
            <input
              type="checkbox"
              checked={task.completed}
              onChange={() => toggleTask(index)}
            />
            <span style={{ textDecoration: task.completed ? 'line-through' : 'none' }}>
              {task.text}
            </span>
            <button onClick={() => removeTask(index)}>Remove</button>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default TodoApp;
```

### Example 2: Weather App

This weather application example illustrates the practical application of React concepts, including state management, useEffect for side effects, event handling, API interaction and conditional rendering. Users can learn how to create a functional weather application and understand the integration of React hooks into real-world scenarios.

Fetaures:

Functional Component and State Hooks:

* The WeatherApp is a functional component.
* State is controlled using the `useState` hooks for `weather` and `city`.

 Using useEffect to obtain data:

* The `useEffect` hooks are used to perform side effects, such as fetching weather data from the OpenWeatherMap API.
* The `fetchWeatherData` function is asynchronous and fetches weather data based on the selected city using the `fetch` API.
  
  Conditional Rendering:

* The weather data is conditionally rendered only if it exists (`weather && ...`).

Event Handling:

* The user input for the city is captured through an input element, and the `setCity` function is called on its `onChange` event.

 API Interaction:

* The OpenWeatherMap API is used to fetch real-time weather data based on the user's selected city.
* An API key is required for authentication and authorization.

 Dynamically Updating Content:

* The weather data is dynamically updated based on the selected city, and the component re-renders when the city changes.

 Styling:

* Basic styling is applied using standard HTML and inline styles for simplicity.

 Temperature Conversion:

* The temperature is converted from Kelvin to Celsius for better readability.

```
// src/RealWorldExamples/WeatherApp.js
import React, { useState, useEffect } from 'react';

const WeatherApp = () => {
  const [weather, setWeather] = useState(null);
  const [city, setCity] = useState('New York');
  const apiKey = 'YOUR_OPENWEATHERMAP_API_KEY';

  useEffect(() => {
    // Fetch weather data from OpenWeatherMap API
    const fetchWeatherData = async () => {
      try {
        const response = await fetch(
          `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}`
        );

        if (!response.ok) {
          throw new Error('Failed to fetch weather data');
        }

        const data = await response.json();
        setWeather(data);
      } catch (error) {
        console.error(error.message);
      }
    };

    fetchWeatherData();
  }, [city, apiKey]);

  return (
    <div>
      <h1>Weather App</h1>
      <label>
        Enter City:
        <input
          type="text"
          value={city}
          onChange={(e) => setCity(e.target.value)}
        />
      </label>

      {weather && (
        <div>
          <h2>{weather.name}, {weather.sys.country}</h2>
          <p>Temperature: {Math.round(weather.main.temp - 273.15)}°C</p>
          <p>Weather: {weather.weather[0].description}</p>
        </div>
      )}
    </div>
  );
};

export default WeatherApp;
```

  ## Best Practices


### Structuring React projects

Best practices:
* Follow folder structure conventions (for example, grouping components, styles and tests in separate folders).
* Use meaningful names for components, avoiding generic terms like "Item" or "Data".
* Organize code based on features rather than file types (for example, group components, styles and tests for a specific feature in the same folder).

  
```
/src
  /components
    /Button
      Button.js
      Button.test.js
      Button.css
  /features
    /Todo
      TodoList.js
      TodoItem.js
      TodoForm.js
  /styles
    global.css
  /tests
    /unit
      Button.test.js
    /integration
      TodoIntegration.test.js
   ```


### Performance optimization techniques:

Best practices:

* Use PureComponent or React.memo for components that are only rendered again when properties or state change.
* Implement code splitting to load only the necessary components when needed, improving initial loading times.
* Use lazy loading for components that are not immediately needed, improving application performance.
```
// Using React.memo
const MemoizedComponent = React.memo(({ data }) => {
  // Component logic
});

// Using Code Splitting and Lazy Loading
const MyComponent = React.lazy(() => import('./MyComponent'));

// In your component
const App = () => (
  <React.Suspense fallback={<LoadingSpinner />}>
    <MyComponent />
  </React.Suspense>
);
```

### Testing React applications:

Best practices:

* Write unit tests for individual components using test libraries such as Jest and test utilities provided by React.
* Implement integration tests to ensure that different components work together smoothly.
* Use tools such as React's test library to test user interactions and component behavior.

Example:
```
// Jest Unit Test
test('renders correctly', () => {
  const { getByText } = render(<Button label="Click me" />);
  expect(getByText('Click me')).toBeInTheDocument();
});

// Jest Integration Test
test('increments count on button click', () => {
  const { getByText } = render(<Counter />);
  fireEvent.click(getByText('Increment'));
  expect(getByText('Count: 1')).toBeInTheDocument();
});

// React Testing Library
import { render, screen } from '@testing-library/react';
import userEvent from '@testing-library/user-event';

test('clicking button increments count', () => {
  render(<MyComponent />);
  userEvent.click(screen.getByRole('button'));
  expect(screen.getByText('Count: 1')).toBeInTheDocument();
});
```

### Routing e Navigation:

Best practices:

* Use React Router for client-side routing in a single-page application.
* Define routes to different views or sections of your application.
* Implement navigation components, such as `<Link>`, to allow easy navigation between routes.

  Example:
  
```
// React Router
import { BrowserRouter as Router, Route, Link } from 'react-router-dom';

const App = () => (
  <Router>
    <nav>
      <ul>
        <li><Link to="/">Home</Link></li>
        <li><Link to="/about">About</Link></li>
        <li><Link to="/contact">Contact</Link></li>
      </ul>
    </nav>
    <Route path="/" exact component={Home} />
    <Route path="/about" component={About} />
    <Route path="/contact" component={Contact} />
  </Router>
);
```

### State Management:

Best practice:

* Use local component state for simple, localized state requirements.
* Use the Context API to share state between components without prop drilling.
* Consider external state management libraries, such as Redux or Recoil, for complex state management needs in larger applications.
  
```
// Using Local Component State
const Counter = () => {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};

// Using Context API
const ThemeContext = React.createContext('light');

const ThemedComponent = () => {
  const theme = useContext(ThemeContext);
  return <p style={{ color: theme === 'light' ? 'black' : 'white' }}>Themed Component</p>;
};

// Using Redux
// (Assuming you have a Redux store configured)
import { useSelector, useDispatch } from 'react-redux';

const CounterRedux = () => {
  const count = useSelector(state => state.count);
  const dispatch = useDispatch();

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => dispatch({ type: 'INCREMENT' })}>Increment</button>
    </div>
  );
};
```

### Deployment

Best practices:

* Choose a hosting platform such as Netlify, Vercel or GitHub Pages to facilitate deployment.
* Set up build scripts to optimize assets for production (packaging, minification and compression).
* Set up continuous integration/continuous deployment (CI/CD) pipelines for automatic deployment on code changes.
  
Example:

* Deployment platforms like Netlify and Vercel offer straightforward deployment based on your Git repository. You can connect your repository to the platform, configure build settings, and deploy with e

  
### Error Handling:

Best practices:

* Implement error thresholds to catch and handle errors gracefully, preventing the entire application from crashing.
* Record errors in a service for tracing and debugging purposes.
* Present user-friendly error messages and provide instructions on how to recover from errors, when possible.

  
Example:

```
// Error Boundary
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  componentDidCatch(error, errorInfo) {
    logErrorToService(error, errorInfo);
  }

  render() {
    if (this.state.hasError) {
      return <p>Something went wrong. Please try again.</p>;
    }

    return this.props.children;
  }
}
```

### Accessibility (a11y):

Best practices:

* Use semantic HTML elements to provide meaningful structure to the page.
* Include ARIA functions and attributes to improve accessibility for screen readers.
* Ensure that keyboard navigation is seamless and logical for users who depend on it.

Example:

```
// Semantic HTML Elements
<article>
  <h2>Article Title</h2>
  <p>Article content...</p>
</article>

// ARIA Roles and Attributes
<button aria-label="Close" onClick={handleClose}>
  &#x2715;
</button>

// Keyboard Navigation
<input type="text" onKeyDown={handleKeyDown} />
```

### Performance Optimization:

Best practices:

* Optimize component rendering using memoization techniques (React.memo or useMemo).
* Take advantage of code splitting and slow loading to reduce the size of the initial package and improve loading times.
* Use React's PureComponent or shouldComponentUpdate to avoid unnecessary rendering.


Example:

```
// Using React.memo
const MemoizedComponent = React.memo(({ data }) => {
  // Component logic
});

// Using Code Splitting and Lazy Loading
const MyComponent = React.lazy(() => import('./MyComponent'));

// In your component
const App = () => (
  <React.Suspense fallback={<LoadingSpinner />}>
    <MyComponent />
  </React.Suspense>
);

// Using PureComponent
class PureCounter extends React.PureComponent {
  render() {
    return <p>Count: {this.props.count}</p>;
}
```


## Additional Topics

### Version control and updates:

* Regularly update dependencies to benefit from new features, bug fixes and security patches.
* Follow semantic versioning for libraries and packages used in the project.
* Be cautious with major updates and test thoroughly before updating.

  Example:
```
# Regularly update dependencies
npm update

# Follow semantic versioning
# Example: Major.Minor.Patch
# ^1.2.3 means any version that is compatible with 1.2.3

```

### Implementation in production:

 * Minimize the number of requests and optimize assets for faster loading times.
 * Implement server-side rendering (SSR) to improve performance and search engine optimization (SEO).
 * Use tools such as Webpack for packaging and Babel to transpile code for production.
 * 
Configure Webpack for production builds with optimizations:
```
// webpack.config.js
const path = require('path');

module.exports = {
  mode: 'production',
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
  // Other webpack configurations...
};
```


### Community resources:

* Encourage students to explore the official React documentation for detailed explanations and examples.
* Join the React community by participating in forums such as Stack Overflow, Reddit or the Reactiflux Discord community.
* Explore tutorials, blog posts and video courses from reliable sources to deepen your knowledge.

  
Examples:
Point students to the official React documentation: [React Documentation].(https://react.dev/)




## Contribution guidelines

Thank you for your interest in contributing to this Amazing React Tutorial! Your contributions help make this resource even more valuable to students of all levels. Whether you're fixing a bug, improving an existing feature or adding something entirely new, your efforts make a difference.

## How to contribute

1. **Fork the Repository: Click on the "Fork" button in the top right corner of this repository to create your copy.

2. **Clone the Repository: Clone the repository to your local machine using `git clone <repository-url>`.

3. **Create a Branch: Create a new branch for your contribution with a descriptive name: `git checkout -b your-feature`.

4. **Make changes: Make your changes in the appropriate files. Feel free to improve existing examples, add new ones, correct typos or improve the documentation.

5. **Commit changes: Submit your changes with a clear and concise message: `git commit -m "Your message here"`.

6. **Push Changes: Send your changes to the forked repository: `git push origin your-feature`.

7. **Create a Pull Request:** Open a pull request in the original repository. Forneça um título claro, descreva suas alterações e envie o pull request.

 ## Coding style and standards

 Follow consistent coding styles.
 Make sure your code is well documented, especially if you are adding new examples or features.
 
## Report problems

If you encounter a problem or have suggestions for improvement, please open a problem in the [Problems] tab (https://github.com/your-username/react-tutorial/issues).
## Thank you

Thank you for considering contributing to this React Tutorial. Your dedication to making this resource better is greatly appreciated. Let's learn and grow together!

## License to Use
<h6 align="center"><a href="/LICENSE">MIT</a> @ David Simoes</h6>

### Did you like the React Tutorial?


If you found this React Tutorial useful, consider giving it a star! ⭐ Your support is incredibly motivating and helps others discover this resource.
 Thank you for being part of our community and hap! 🚀

