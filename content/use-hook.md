## Three usages of the `useEffect` hook

---
<!-- .slide: data-auto-animate -->
#### Run on component mount

```jsx []
useEffect(() => {
  // runs on component mount
  // you can make API calls here
}, [])
```
<!-- .element: data-id="on-mount" -->

--
<!-- .slide: data-auto-animate -->

#### Run on component mount

```jsx []
useEffect(() => {
  // runs on component mount
  // you can make API calls here

  return () => {
    // runs on component unmount
    // run cleanup tasks here
  }
}, [])
```
<!-- .element: data-id="on-mount" -->

---

## Run when a depdency changes

Runs when a state, or prop changes

```jsx []
  useEffect(() => {
    // runs every time the value of `todos` or `count` changes
  }, [todos, count])
```

---

## Run whenever the component rerenders

![Alert](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExbGZ5YWtleDV3cDUyOTd3bzk2bmExZjViYWZvd2p5anc1dXAyemV1aCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/2oUfvvUgQHnLsQWFMW/giphy.gif) <!-- .element: class="fragment" -->

--
<!-- .slide: data-auto-animate -->

```jsx []
  useEffect(() => {
    // runs every time component rerenders
  })
```
<!-- .element data-id="run-always" -->
--
<!-- .slide: data-auto-animate -->

```jsx []
  useEffect(() => {
    // runs every time component rerenders
  }) // 👈🏽 notice the missing dependency array
```
<!-- .element data-id="run-always" -->

---

## Common mistakes with `useEffect`

--
<!-- .slide: data-auto-animate -->

1. Making API calls on every component rerender
```jsx []
  useEffect(() => {
    // runs every time component rerenders
    fetch('myApiUrl').then(() =>{
      // do something
    })
  }) // 👈🏽 notice the missing dependency array
```
<!-- .element data-id="run-always" -->

--
<!-- .slide: data-auto-animate -->

1. Making API calls on every component rerender
```jsx []
  useEffect(() => {
    // runs every time component rerenders
    fetch('myApiUrl').then(() =>{
      // do something
      setStateVariable();
      // ☝🏽 this triggers the useEffect again
      // causing an INFINITE loop
    })
  }) // 👈🏽 notice the missing dependency array
```
<!-- .element data-id="run-always" -->

--
<!-- .slide: data-auto-animate -->

2. Updating the state variable

<small>(the one in `dependencies`)</small>

```jsx []
  useEffect(() => {
    // runs every time users is updated
    fetch('getUsers').then(() =>{
      // do something
    })
  }, [users])
```
<!-- .element data-id="on-users-change" -->

--
<!-- .slide: data-auto-animate -->
2. Updating the state variable

<small>(the one in `dependencies`)</small>

```jsx []
  useEffect(() => {
    // runs every time users is updated
    fetch('getUsers').then((usersFromBackend) =>{
      // do something
      setUsers(usersFromBackend);
      // ☝🏽 this triggers the useEffect again
      // causing an INFINITE loop
    })
  }, [users])
```
<!-- .element data-id="on-users-change" -->