# Intro to React & Components

![](https://bs-uploads.toptal.io/blackfish-uploads/blog/article/content/cover_image_file/cover_image/16967/cover-0322-how-react-components-make-ui-testing-easy-Waldek_Newsletter-b1f3c0ca0ff823b504d7c8fa84a3b6c2.png)

## Overview

In this lesson, we'll learn about the fundamentals of building and utilizing components in React. By utilizing what's known as components, we can easily break up our UI into modular pieces of code that we can reuse in multiple places.

## What is React?

- An open-source JavaScript library used to **build and render user interfaces** in the browser.
- It was open-sourced in May of 2013.
- Created by Jordan Walke, a Facebook engineer.
- Now being used by companies such as Netflix, Imgur, Airbnb, Walmart, and many more.
- React Native, a separate library, can be used to develop native iOS and Android mobile apps.

In short, React gives us the ability to rapidly build applications that are highly interactive in a quick and efficient manner. It uses something called the `virtual DOM` which is an abstraction layer over the native browser DOM. By using the the `virtual DOM`, React facilitates the communication between our code and the actual DOM. React uses a `modular` **`component`** based approach.

## Why would we use React?

[React](https://reactjs.org/) is the most popular (by far) front-end library for building highly dynamic user interfaces used in today's modern single-page applications.

> 👀 A single-page application (SPA) updates its UI "in-place" vs. the traditional multi-page web apps we've built thus far where the browser replaces the entire web page each time the user interacts with it.

Most importantly, you want to learn to use React because...

<figure>
  <img src="https://i.imgur.com/vGlFRHq.png">
</figure>
<figure>
  <img src="https://i.imgur.com/FfSLt6b.png">
  <figcaption>Source: <a href="https://www.devjobsscanner.com/blog/the-most-demanded-frontend-frameworks-in-2022/">devjobsscanner.com</a></figcaption>
</figure>

I think that answers that question...

-----

## Creating a New React App with Vite

The primary method for creating a brand new React app from scratch is by utilizing **[Vite](https://vitejs.dev/)**. This is the recommended approach for creating a React app from scratch since React stopped support for a package called `create-react-app` (2023).

In short, it is a tool that streamlines the process of working with React and gives us some really neat tools and built-in functionality that we would otherwise have to set up ourselves.

If you want to create a new React App with Vite, see the instructions [here](https://github.com/SEI-R-4-24/u4_lesson_new_vite_app).

-----

You will not be running `npm create vite@latest` for React applications that have been previously created and you are cloning down (like many of our lessons).  Rather, the application has already been created and you will want to install the dependencies that are needed for the app.  In order to do that you will just run `npm install` in the directory of the React app. Let's do that now for the starter code of this lesson...

## Getting Started

- `Fork` and `Clone` the repository
- `cd` into our newly created directory
- `npm install` to install our dependencies
- `npm run dev` to spin up our app

## What Are React Components?

By [John Kagga](https://medium.com/the-andela-way/understanding-react-components-37f841c1f3bb)

> Components are the building blocks of any React app and a typical React app will have many of these. Simply put, a component is a JavaScript class or function that optionally accepts inputs i.e. properties(props) and returns a React element that describes how a section of the UI (User Interface) should appear.

From [Educative.io](https://www.educative.io/edpresso/what-is-a-react-component):

> React components let you break up the user interface into separate pieces that can then be reused and handled independently.
> A React component takes an optional input and returns a React element which is rendered on the screen.
> A React component can be either “stateful” or "stateless."

In summary, a React component is a function or class that can receive or handle some kind of information (props/state) and give us back an interactive element in the DOM.

There are two ways of writing a component:

- `class` syntax
- `function` syntax (aka functional components)

Class components are the old (and original) way of writing components in React. You may see them in the wild and they will look very familiar. Think about the JavaScript classes we used when we learned Object Oriented Programming. It's the same concept!

<details>
<summary>Example of a class-based Component</summary>

```jsx
import React from "react"
 
class App extends React.Component {

  render() {
    return <div></div>
  }
}
 
export default App
```

</details>

However, the modern way of writing components in React is something much more familiar: `functions`.

### Functional Components

Functional components were always a popular way of writing of writing components and typically used to build UI elements that were controlled by a class component. With the release of React hooks (2019), we are now able to write all of our components using only the function syntax and manage some kind of state at the same time.

Pros

- easy to set up
- less boilerplate code
- no more confusion on which component should handle logic (for newer developers)

Cons

- most methods now perform more than one thing to control our components behavior
- looser syntax can lead to more bugs
- can cause confusion when writing other functions inside of the component

## Writing Our First Component

Now that we've talked about different kinds of components, it's time to actually write one!

Throughout this course, we'll be using functional components. Lets start with a basic skeleton of what a functional component would look like:

```jsx
const App = () => {

  return (
    <div></div>
  )
}

export default App
```

There are lots of ways of writing this exact same thing (it is ***just*** JavaScript after all). Here's a few you might see:

<details>
<summary>As an ES5 Function</summary>

```jsx
function App () {

  return (
    <div></div>
  )
}

export default App
```

</details>

<details>
<summary>As an ES5 Function Exported on the Same Line</summary>

```jsx
export default function App () {

  return (
    <div></div>
  )
}
```

</details>

<details>
<summary>As an ES6 Arrow Function Exported on the Same Line</summary>

```jsx
export const App = () => {

  return (
    <div></div>
  )
}
```

** *Note: when exporting on the same line the export is packaged differently. So, imports will be done differently as well. If you choose to use this, speak with an instructor about how to make it work!*

</details>

None of these different ways are *right* or *wrong*, but you may see them all in real-world scenarios. So it's good to be aware of them...

We'll be using the first ES6 Arrow Function example for most of the course, as it is the most modern and simple.

In your text editor, let's create a folder called `components` inside of the `src` folder. **All of the code you write will always go in the `src` folder.**

Inside of the `components` folder, create a file called `Button.jsx`.

**Pay special attention to the casing of the file name, all component files will use the `PascalCased` convention.**

**All JavaScript filenames in Vite React Apps must end in .jsx**


The `import` syntax uses the following structure:

```jsx
import NameForComponent from '../components/FileOfComponent'
```

**Note: This syntax is only used for component files or libraries such as `React`. When importing stylesheets you do not need a variable name**.

Next we'll set up the function for our component. Add the following to `Button.jsx`:

```js
const Button = () => {}
```

Next, we'll return a `button` element from our `Button` component:

```jsx
const Button = () => {

  return (
    <button>Click Me</button>
  )
}
```

And last step! In order to utilize this component somewhere else in our application, we need to `export` it:

```jsx
export default Button
```

Final `Button` component:

```jsx
const Button = () => {

  return (
    <button>Click Me</button>
  )
}

export default Button
```


### Utilizing Our Component

Now that we've successfully created a `Button` component, let's display it in our UI!

Open the `App.jsx` file. Add an `import` statement to the top, this `import` statement is going to handle bringing in our `Button` component:

```js
import Button from './components/Button'
```

**Note: You do not need to use file extensions for `.js` and `.jsx` files in React when importing!**

Next we'll add our `Button` to the current markup in `App.jsx`:

```jsx
const App = () => {

  return (
    <div>
      <Button />
    </div>
  )
}
```

**Note: Notice the use of `()` in the return statement! This syntax is used when returning multiple elements from a component! Also, notice how we do not use an opening and closing tag for the component itself.**

At this point, check your browser and you should see the following button:

![button-element](images/button-element.png)

### Re-using Components

At this point, we should have a beautiful button displayed on our page. What if we wanted multiple buttons? With React, this is pretty straightforward. We can simply add more of the `Button` component to our markup!

Add the following to the `App.jsx`:

```jsx
const App = () => {
  
  return (
    <div>
      <Button />
      <Button />
      <Button />
      <Button />
    </div>
  )
}
```

We should now see `4` buttons on our page:

![multiple-buttons](images/multiple-buttons.png)

## Recap

In this lesson, we learned how to:

- Create a component
- How a component is structured
- How to import a component
- How to use a component multiple times

Components are crucial building blocks in React. They allow us to build amazing UI's by reusing most of our code. Gone are the days of writing a button over and over again. By using React, we can create one component and utilize it multiple times. Our current button although simple, is a critical foundation going forward.

## Resources

- [Vite](https://vitejs.dev/)
- [React Components](https://react.dev/learn/your-first-component)
- [Understanding React Components](https://medium.com/the-andela-way/understanding-react-components-37f841c1f3bb)
