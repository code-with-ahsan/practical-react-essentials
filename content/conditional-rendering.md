## Dynamic & Conditional Rendering in React

--

#### What is conditional rendering?

- Rendering different UI components based on certain conditions
- It makes applications interactive and responsive to user inputs <!-- .element: class="fragment" -->
- Techniques: <!-- .element: class="fragment" -->
  - Ternary operator, Logical `&&` operator, and `if-else` statements.
 <!-- .element: class="fragment" -->

  - Early returns<!-- .element: class="fragment" -->

--

#### Using the Ternary Operator

- Syntax: `condition ? trueExpression : falseExpression`
<!-- .element: class="fragment" -->

- Ideal for inline rendering decision within JSX <!-- .element: class="fragment" -->

```jsx []
const WelcomeMessage = ({ isLoggedIn }) => {
  return (
    <div>
      {isLoggedIn ? <h1>Welcome back!</h1> : <h1>Welcome, guest!</h1>}
    </div>
  );
}
```
<!-- .element: class="fragment" style="font-size: 1.2rem" -->

--
#### Logical `&&` Operator

- Syntax: `condition && expression`
- Renders the expression **only** if the condition is `true`
<!-- .element: class="fragment" -->


```jsx []

const UserDashboard = ({ user }) => {
  return (
    <div>
      {user && <h1>Hello, {user.name}</h1>}
    </div>
  );
}

```
<!-- .element: class="fragment" data-line-numbers data-trim data-id="loginFormCode" style="font-size: 1rem;" -->

--

#### If-Else Statements in Component Functions

- Can not use directly in JSX
- Use in component functions to control larger logic flows

```jsx []

const LoginButton = ({ isLoggedIn }) => {
  if (isLoggedIn) {
    return <button>Logout</button>;
  } else {
    return <button>Login</button>;
  }
}

```
<!-- .element: class="fragment" data-line-numbers data-trim data-id="loginFormCode" style="font-size: 1rem;" -->

--

#### Early Return

- Use to handle pre-conditions or guard clauses <!-- .element: class="fragment" -->

- Improves code readability and reduces nesting <!-- .element: class="fragment" -->


```jsx []

const UserProfile = ({ user }) => {
  if (!user) {
    return <h1>Loading...</h1>;
  }
  return (
    <div>
      <h1>{user.name}</h1>
      <p>Email: {user.email}</p>
    </div>
  );
}

```
<!-- .element: class="fragment" data-line-numbers data-trim data-id="loginFormCode" style="font-size: 1rem;" -->

--

#### Rendering Arrays of Items

- use the `.map()` function to transform an array into JSX elements
<!-- .element: class="fragment" -->

- `key` prop is crucial for performance and stability
<!-- .element: class="fragment" -->

```jsx []

const ItemList = ({ items }) => {
  return (
    <ul>
      {items.map(item => <li key={item.id}>{item.name}</li>)}
    </ul>
  );
}

```
<!-- .element: class="fragment" data-line-numbers data-trim data-id="loginFormCode" style="font-size: 0.8rem;" -->

--

## Conclusion

- We covered ternary operators, logical &&, if-else statements, early returns, and rendering lists. <!-- .element: class="fragment" -->
- Experiment with these techniques in your own React projects. <!-- .element: class="fragment" -->
- Play around with different conditions to see dynamic changes in your app. <!-- .element: class="fragment" -->