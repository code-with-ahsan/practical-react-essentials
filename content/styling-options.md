## Styling options in React

--

In React, there are multiple ways to apply styles, each with its advantages. Whether you're applying styles directly within your JSX or using sophisticated libraries, React makes it flexible to suit your project's needs.


---

#### Introduction to Styling in React

- Inline Styling <!-- .element class="fragment" -->
- CSS Modules <!-- .element class="fragment" -->
- Styling Libraries <!-- .element class="fragment" -->
  - Styled Components <!-- .element class="fragment" -->
  - Material UI <!-- .element class="fragment" -->
  - Tailwind CSS <!-- .element class="fragment" -->

---

#### Inline Styling

- Definition: Applying styles directly within JSX using the style attribute.
- Example:

```jsx []
const Counter = () => {
  return <div style={{
    margin: 10,
    padding: 20,
    border: '1px solid red'
  }}>
    Hello, counter
  </div>
}
```
--

#### Inline Styling

Pros and Cons:
- Quick and easy for simple styles
- Limited scalability and reusability

---

#### CSS Modules

- Definition: A CSS file in which all class names and animation names are scoped locally by default.
- Code example:

```css []
/* Button.module.css */
.myButton {
  padding: 10px 15px;
  border: none;
  background-color: blue;
  color: white;
  border-radius: 5px;
}
```
<!-- .element: style="font-size: 1rem;" -->

```jsx []
// Button.jsx
import { FC } from 'react';
import styles from './Button.module.css';
const ButtonProps = {
  text: string;
}
const Button: FC<ButtonProps> = ({text}) => {
  return <button className={styles.myButton}>{text}</button>;
}
```
<!-- .element: style="font-size: 1rem;" -->

--
## CSS Modules

Pros and Cons:
- Scoped styles prevent conflicts
- More maintainable than inline styles

---

## Styling Libraries

--

#### Styled Components

- Utilize tagged template literals to style your components
- Code example:

```jsx []
import styled from 'styled-components';
import { FC } from 'react';

const ButtonProps = {
  text: string;
}
const StyledButton = styled.button`
  background-color: purple;
  color: white;
  padding: 8px 12px;
  border-radius: 5px;
  border: none;
`;

export const Button: FC<ButtonProps> = ({text}) => {
  return <StyledButton>{text}</StyledButton>;
}
```

--

#### Material UI

- A popular React UI framework that follows Google's Material Design.
- Code example:

```jsx []
import Button from '@mui/material/Button';

const App = () => {
  return <Button variant="contained" color="primary">Hello World</Button>;
}

```

--

#### Tailwind CSS

- One of my favorite libaries. A utility-first CSS framework packed with classes that can be composed to build any design, directly in your markup.
- Code example:

```jsx []
import { FC } from 'react';

const ButtonProps = {
  text: string;
}
export const Button: FC<ButtonProps> = ({text}) => {
  return <button class="h-10 px-6 font-semibold rounded-md bg-black text-white" type="submit">
    {text}
  </button>
}
```