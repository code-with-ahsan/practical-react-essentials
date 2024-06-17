## React, Prop Drilling, and Context API

---

### State management recap

To maintain a state in a React component (_function component_), we use the `useState` hook
<!-- .element: class="fragment" -->

---

## What is prop drilling?

The concept of passing props to multiple nested levels of a component tree is referred to as 

`Prop Drilling`.

--

## Disadvantages of prop drilling

- Hard to maintain. Every new prop has to be passed all along in the component tree
- Less scalable and reusable
  

--

## Solution??

---

## Context API

--

First, create the context

```jsx []
const ThemeContext = createContext('light');
```

--

Then, provide the context in your application. This depends on which components you want to _wrap your context around_.

```jsx []
function App() {
  const [theme, setTheme] = useState('light');
  // ...
  return (
    <ThemeContext.Provider value={theme}>
      <Page />
    </ThemeContext.Provider>
  );
}
```

--
<!-- .slide: data-auto-animate -->
Finally, you can consume the value from the context in your component, as follows:

```jsx []
function Button() {
  // 🟡 Legacy way (not recommended)
  return (
    <ThemeContext.Consumer>
      {theme => (
        <button className={theme} />
      )}
    </ThemeContext.Consumer>
  );
}
```
<!-- .element: data-id="theme-consumer" -->

--
<!-- .slide: data-auto-animate -->
Finally, you can consume the value from the context in your component, as follows:

```jsx []
function Button() {
  // ✅ Recommended way
  const theme = useContext(ThemeContext);
  return <button className={theme} />;
}
```
<!-- .element: data-id="theme-consumer" -->

