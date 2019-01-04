---
description: >-
  Components let you split the UI into independent, reusable pieces, and think
  about each piece in isolation.
---

# Components and Props

Conceptually, components are like JavaScript functions. They accept arbitrary inputs \(called “props”\) and return React elements describing what should appear on the screen.

## Function Component

Function Component accepts a single “props” \(which stands for properties\) object argument with data and returns a React element. Props are read only.

```jsx
// Simple way
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
// Use an ES6 class to define a component:
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
// Render the above component
const element = <Welcome name="Sara" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```

## Class Component

### Overview

1. Class Component: Input: Props and State; Output: React.Component.
2. State can be changed, but Props not.
3. This.setState will trigger the render method.
4. If we export a class using default, like export default component, x; We can Import it without {} and with any name, like import comp, {x} from "./module". Only apply to first exported parameter.

```jsx
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

  componentDidMount() {
    this.timerID = setInterval(
      () => this.tick(),
      1000
    );
  }

  componentWillUnmount() {
    clearInterval(this.timerID);
  }

  tick() {
    this.setState({
      date: new Date()
    });
  }

  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}

ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
```

### Using State Correctly <a id="using-state-correctly"></a>

#### Do Not Modify State Directly. Use the setState. <a id="do-not-modify-state-directly"></a>

```text
this.setState((state, props) => ({
  counter: state.counter + props.increment
}));
```

#### State Updates are Merged <a id="state-updates-are-merged"></a>

 When you call `setState()`, React merges the object you provide into the current state.

