# React Fundamentals

---

### Why React?

- React is a tiny library that allows us to build dynamic and interactive web apps and user interfaces <!-- .element class="fragment" -->
- Very fast and performant due to Virtual DOM and the new compiler  <!-- .element class="fragment" -->
- Excellent tooling and ecosystem like React Native, NextJS, Remix etc. <!-- .element class="fragment" -->
- One of the most popular frameworks to get a job <!-- .element class="fragment" -->

---

#### JSX (JavaScript Syntax Extension)

<div style="display: flex !important; gap: 16px; align-items: center;">
  <p class="fragment">
    JSX is HTML written inside JavaScript components
  </p>
  <img width="700" src="assets/images/react-fundamentals/jsx.png">
</div>

---

### React Components

--

#### React Components

- Reusable piece of code that help build pages/elements in an app <!-- .element: class="fragment" -->
- Can receive `props` from outside and will rerender when props change 
<!-- .element: class="fragment" -->

- Can have their own `state` and will rerender when the state changes
<!-- .element: class="fragment" -->

- Allows us to break the logic (especially UI) into multiple functions and files to allow scaling the app better <!-- .element: class="fragment" -->

--

Basic example

```jsx
const Button = ({text = "submit"}) => {
  return <button>{text}</button>;
}
```

--

React components are just JavaScript functions

```jsx
const Button = ({text}) => {
  if (!text) {
    text = "submit";
  }
  return <button>{text}</button>;
}
```

---

## `Props` vs `State` in React

--

### What are Props?

Props are `read-only` properties passed from the parent component to child components.

- They can not be modified by the child component <!-- .element: class="fragment" -->
- If the props change, the child component is re-rendered <!-- .element: class="fragment" -->
- Example of props: <!-- .element: class="fragment" -->
  - strings, numbers, functions, etc. <!-- .element: class="fragment" -->

--

### What is State?

State data is maintained inside a component

- They can be modified by the component itself <!-- .element: class="fragment" -->
- Can be initialized with a default value <!-- .element: class="fragment" -->
- Used to track changes like user inputs, form submissions etc. <!-- .element: class="fragment" -->
- Example: <!-- .element: class="fragment" -->
  - A counter component showing a count, and some action buttons to: <!-- .element: class="fragment" -->
    - Increment counter <!-- .element: class="fragment" -->
    - Decrement counter <!-- .element: class="fragment" -->
    - Reset counter <!-- .element: class="fragment" -->
  
