# Virtual DOM in React

---

## What is DOM?

--

` DOM` stands for "Document Object Model". Which in simple words represents the UI of the application. Whenever the UI changes, the DOM gets updated.

--

As web developers, we usually end up using JavaScript to update/_manipulate_ <!-- .element: class="fragment" --> the DOM.

---

## What is Virtual DOM?

The Virtual DOM is an in-memory representation of the real DOM elements. It's like a lightweight copy of the actual DOM, and it allows React to do its magic behind the scenes, optimizing updates and rendering speed.

--
<!-- .slide: data-auto-animate -->

![Virtual Dom1](assets/images/virtual-dom/virtual-dom-1.png)
<!-- .element data-id="vdom-img" -->

--
<!-- .slide: data-auto-animate -->

![Virtual Dom2](assets/images/virtual-dom/virtual-dom-2.png)
<!-- .element data-id="vdom-img" -->


--
<!-- .slide: data-auto-animate -->

![Virtual Dom3](assets/images/virtual-dom/virtual-dom-3.png)
<!-- .element data-id="vdom-img" -->


--
<!-- .slide: data-auto-animate -->

![Virtual Dom4](assets/images/virtual-dom/virtual-dom-4.png)
<!-- .element data-id="vdom-img" -->


--
<!-- .slide: data-auto-animate -->

![Virtual Dom5](assets/images/virtual-dom/virtual-dom-5.png)
<!-- .element data-id="vdom-img" -->

---

To recap, the Virtual DOM allows React to perform efficient updates by only redrawing nodes that have changed. This results in a significant performance gain, especially in complex applications.

---

## Recap and best practices

- Recap: Virtual DOM updates only what is necessary
- Best Practice: Minimize state updates to optimize React's performance better
- Remember: Virtual DOM is not just a performance feature, it is a programming model that simplifies UI logic for React
