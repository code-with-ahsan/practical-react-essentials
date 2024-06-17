## Custom React Hooks

--

## What are hooks?

Custom hooks are functions that let you tap into React’s state and lifecycle features from function components. They’re like your personal toolkit for sharing logic with a beautiful twist — no component inheritance or messy chains of props.
<!-- .element: class="fragment" style="font-size: 2rem" -->

--

## Benefits of a Custom hook?

- Reusability of _stateful_ logic
- Cleaner and more maintainable code
- Easier to test and isolate

---
<!-- .slide: data-auto-animate -->
## Creating a custom hook

```jsx []
import { useState, useEffect } from 'react';

function useWindowSize() {
  
}
```
<!-- .element: data-id="custom-hook" -->

--
<!-- .slide: data-auto-animate -->

#### Creating a custom hook

```jsx []
import { useState, useEffect } from 'react';

function useWindowSize() {
  const [size, setSize] = useState({
    width: window.innerWidth,
    height: window.innerHeight
  });

  return size; // a value has to return (almost always)
}
```
<!-- .element: data-id="custom-hook" -->

--
<!-- .slide: data-auto-animate -->

#### Creating a custom hook

```jsx []
import { useState, useEffect } from 'react';

function useWindowSize() {
  const [size, setSize] = useState({
    width: window.innerWidth,
    height: window.innerHeight
  });

  useEffect(() => {
    const handleResize = () => {
      setSize({width: window.innerWidth, height: window.innerHeight});
    };

    window.addEventListener('resize', handleResize);
  }, []);

  return size;
}
```
<!-- .element: data-id="custom-hook" style="font-size: 1.2rem" -->

--
<!-- .slide: data-auto-animate -->

#### Creating a custom hook

```jsx []
import { useState, useEffect } from 'react';

function useWindowSize() {
  const [size, setSize] = useState({
    width: window.innerWidth,
    height: window.innerHeight
  });

  useEffect(() => {
    const handleResize = () => {
      setSize({width: window.innerWidth, height: window.innerHeight});
    };

    window.addEventListener('resize', handleResize);
    return () => {
      return window.removeEventListener('resize', handleResize);
    };
  }, []);

  return size;
}
```
<!-- .element: data-id="custom-hook" style="font-size: 1.2rem" -->
 
---

#### Yet another custom hook:
#### `useFetch`

```jsx []
import { useState, useEffect } from 'react';

const useFetch = (url) => {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    const fetchData = async () => {
      const response = await fetch(url);
      const result = await response.json();
      setData(result);
      setLoading(false);
    };

    fetchData();
  }, [url]);

  return { data, loading };
}

```
<!-- .element: style="font-size: 1rem" -->

---

## Best practices for Custom Hooks

- Encapsulate only related logic <!-- .element: class="fragment" -->
- Name hooks with the `use` prefix 
<!-- .element: class="fragment" -->

- Keep hooks small and focused <!-- .element: class="fragment" -->