## State management with `useState` hook

--

#### What does the `useState` hook help with?

- Allows functional components to hold state <!-- .element class="fragment" -->
- Returns a state variable and a function to update it <!-- .element class="fragment" -->

--

### Syntax

```jsx []
const [stateValue, setStateValue] = useState(initialStateValue);
```

--

#### Detailed Example:

```jsx []
import { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div className="flex flex-col gap-4">
      <p className="text-xl">You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

```