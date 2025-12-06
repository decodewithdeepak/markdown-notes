# React.js Master Notes By Deepak Modi

> Recommended Resources: React Official Docs, FreeCodeCamp, Namaste React Series

## Table of Contents

1. [Introduction to React](#1-introduction-to-react)

   - [1.1 What is React?](#11-what-is-react)
   - [1.2 Why React?](#12-why-react)
   - [1.3 React vs Other Frameworks](#13-react-vs-other-frameworks)
   - [1.4 Setting Up React Environment](#14-setting-up-react-environment)
   - [1.5 Create React App vs Vite](#15-create-react-app-vs-vite)

2. [Core Concepts](#2-core-concepts)

   - [2.1 JSX (JavaScript XML)](#21-jsx-javascript-xml)
   - [2.2 Components](#22-components)
   - [2.3 Props](#23-props)
   - [2.4 State](#24-state)
   - [2.5 Virtual DOM](#25-virtual-dom)
   - [2.6 Reconciliation Algorithm](#26-reconciliation-algorithm)
   - [2.7 React Fiber Architecture](#27-react-fiber-architecture)

3. [React Hooks](#3-react-hooks)

   - [3.1 Introduction to Hooks](#31-introduction-to-hooks)
   - [3.2 useState Hook](#32-usestate-hook)
   - [3.3 useEffect Hook](#33-useeffect-hook)
   - [3.4 useContext Hook](#34-usecontext-hook)
   - [3.5 useReducer Hook](#35-usereducer-hook)
   - [3.6 useRef Hook](#36-useref-hook)
   - [3.7 useMemo Hook](#37-usememo-hook)
   - [3.8 useCallback Hook](#38-usecallback-hook)
   - [3.9 useLayoutEffect Hook](#39-uselayouteffect-hook)
   - [3.10 useImperativeHandle Hook](#310-useimperativehandle-hook)
   - [3.11 Custom Hooks](#311-custom-hooks)

4. [Component Lifecycle](#4-component-lifecycle)

   - [4.1 Class Component Lifecycle](#41-class-component-lifecycle)
   - [4.2 Lifecycle Methods](#42-lifecycle-methods)
   - [4.3 Lifecycle with Hooks](#43-lifecycle-with-hooks)

5. [State Management](#5-state-management)

   - [5.1 Lifting State Up](#51-lifting-state-up)
   - [5.2 Context API](#52-context-api)
   - [5.3 Redux Fundamentals](#53-redux-fundamentals)
   - [5.4 Redux Toolkit](#54-redux-toolkit)
   - [5.5 Zustand](#55-zustand)
   - [5.6 Recoil](#56-recoil)
   - [5.7 State Management Comparison](#57-state-management-comparison)

6. [Routing](#6-routing)

   - [6.1 React Router Basics](#61-react-router-basics)
   - [6.2 Dynamic Routing](#62-dynamic-routing)
   - [6.3 Nested Routes](#63-nested-routes)
   - [6.4 Protected Routes](#64-protected-routes)
   - [6.5 Programmatic Navigation](#65-programmatic-navigation)

7. [Forms and Validation](#7-forms-and-validation)

   - [7.1 Controlled Components](#71-controlled-components)
   - [7.2 Uncontrolled Components](#72-uncontrolled-components)
   - [7.3 Form Libraries (Formik, React Hook Form)](#73-form-libraries-formik-react-hook-form)
   - [7.4 Form Validation](#74-form-validation)

8. [Performance Optimization](#8-performance-optimization)

   - [8.1 React.memo](#81-reactmemo)
   - [8.2 Code Splitting](#82-code-splitting)
   - [8.3 Lazy Loading](#83-lazy-loading)
   - [8.4 Suspense](#84-suspense)
   - [8.5 Profiler and DevTools](#85-profiler-and-devtools)
   - [8.6 Debouncing and Throttling](#86-debouncing-and-throttling)
   - [8.7 Virtualization](#87-virtualization)

9. [Advanced Patterns](#9-advanced-patterns)

   - [9.1 Higher-Order Components (HOC)](#91-higher-order-components-hoc)
   - [9.2 Render Props](#92-render-props)
   - [9.3 Compound Components](#93-compound-components)
   - [9.4 Controlled vs Uncontrolled Components](#94-controlled-vs-uncontrolled-components)
   - [9.5 Error Boundaries](#95-error-boundaries)
   - [9.6 Portals](#96-portals)
   - [9.7 Refs and Forward Refs](#97-refs-and-forward-refs)

10. [API Integration](#10-api-integration)

    - [10.1 Fetch API](#101-fetch-api)
    - [10.2 Axios](#102-axios)
    - [10.3 React Query (TanStack Query)](#103-react-query-tanstack-query)
    - [10.4 SWR](#104-swr)
    - [10.5 Error Handling](#105-error-handling)

11. [Testing](#11-testing)

    - [11.1 Testing Philosophy](#111-testing-philosophy)
    - [11.2 Jest](#112-jest)
    - [11.3 React Testing Library](#113-react-testing-library)
    - [11.4 Component Testing](#114-component-testing)
    - [11.5 Integration Testing](#115-integration-testing)
    - [11.6 E2E Testing with Cypress](#116-e2e-testing-with-cypress)

12. [TypeScript with React](#12-typescript-with-react)

    - [12.1 Why TypeScript?](#121-why-typescript)
    - [12.2 Setting Up TypeScript](#122-setting-up-typescript)
    - [12.3 Typing Components](#123-typing-components)
    - [12.4 Typing Hooks](#124-typing-hooks)
    - [12.5 Generic Components](#125-generic-components)

13. [Styling in React](#13-styling-in-react)

    - [13.1 CSS Modules](#131-css-modules)
    - [13.2 Styled Components](#132-styled-components)
    - [13.3 Emotion](#133-emotion)
    - [13.4 Tailwind CSS](#134-tailwind-css)
    - [13.5 Material-UI / Chakra UI](#135-material-ui--chakra-ui)

14. [React 18+ Features](#14-react-18-features)

    - [14.1 Concurrent Rendering](#141-concurrent-rendering)
    - [14.2 Automatic Batching](#142-automatic-batching)
    - [14.3 Transitions](#143-transitions)
    - [14.4 Suspense for Data Fetching](#144-suspense-for-data-fetching)
    - [14.5 Server Components](#145-server-components)

15. [Interview Questions](#15-interview-questions)
    - [15.1 Fundamental Questions](#151-fundamental-questions)
    - [15.2 Hooks Questions](#152-hooks-questions)
    - [15.3 Performance Questions](#153-performance-questions)
    - [15.4 Advanced Questions](#154-advanced-questions)
    - [15.5 Coding Challenges](#155-coding-challenges)

---

## 1. Introduction to React

### 1.1 What is React?

React is a **JavaScript library** for building user interfaces, developed and maintained by Facebook (Meta). Released in 2013, React revolutionized frontend development by introducing a component-based architecture and declarative programming model.

> **Key Point:** React is a library, not a framework. It focuses solely on the view layer (UI), giving developers freedom to choose other tools for routing, state management, etc.

#### Core Philosophy

- **Component-Based:** Build encapsulated components that manage their own state
- **Declarative:** Describe what the UI should look like, React handles the updates
- **Learn Once, Write Anywhere:** Use React for web, mobile (React Native), VR, and more

#### Real-World Usage

Companies using React: Facebook, Instagram, Netflix, Airbnb, Uber, WhatsApp, Dropbox, Reddit, Discord

### 1.2 Why React?

#### Advantages

1. **Reusable Components:** Write once, use everywhere in your application
2. **Virtual DOM:** Efficient updates and rendering
3. **One-Way Data Flow:** Predictable data management
4. **Rich Ecosystem:** Huge community, libraries, and tools
5. **SEO Friendly:** With SSR (Server-Side Rendering) via Next.js
6. **Strong Community:** Massive support, tutorials, and resources
7. **React Native:** Share code between web and mobile
8. **Developer Experience:** Great tooling, DevTools, hot reloading

#### Disadvantages

1. **Learning Curve:** JSX, hooks, and concepts can be overwhelming initially
2. **Rapid Changes:** Ecosystem evolves quickly
3. **Just a View Library:** Need additional libraries for complete solution
4. **JSX Barrier:** Some developers find JSX syntax confusing at first

### 1.3 React vs Other Frameworks

| Feature          | React                  | Angular         | Vue          |
| ---------------- | ---------------------- | --------------- | ------------ |
| Type             | Library                | Framework       | Framework    |
| Learning Curve   | Moderate               | Steep           | Easy         |
| Language         | JavaScript/JSX         | TypeScript      | JavaScript   |
| DOM              | Virtual DOM            | Real DOM        | Virtual DOM  |
| Data Binding     | One-way                | Two-way         | Two-way      |
| State Management | External (Redux, etc.) | Built-in (RxJS) | Vuex/Pinia   |
| Mobile           | React Native           | Ionic           | NativeScript |
| Company          | Meta                   | Google          | Independent  |
| Bundle Size      | Small                  | Large           | Smallest     |

### 1.4 Setting Up React Environment

#### Prerequisites

- Node.js (v14 or higher)
- npm or yarn package manager
- Code editor (VS Code recommended)

#### VS Code Extensions

- ES7+ React/Redux/React-Native snippets
- Prettier - Code formatter
- ESLint
- Auto Rename Tag
- Bracket Pair Colorizer

### 1.5 Create React App vs Vite

#### Create React App (CRA)

**Pros:**

- Official React tool
- Zero configuration
- Includes testing setup
- Well documented

**Cons:**

- Slower build times
- Larger bundle size
- Uses Webpack (slower HMR)

#### Vite

**Pros:**

- Lightning fast HMR (Hot Module Replacement)
- Faster build times
- Smaller bundle size
- Modern tooling (esbuild, Rollup)
- Better developer experience

**Cons:**

- Newer, smaller community
- Some plugins may not be available

**Recommendation:** Use Vite for new projects in 2024+

---

## 2. Core Concepts

### 2.1 JSX (JavaScript XML)

JSX is a syntax extension for JavaScript that looks similar to HTML. It allows you to write HTML-like code in JavaScript files.

#### Why JSX?

- **Intuitive:** Looks like HTML, easy to visualize UI
- **Type-Safe:** Catch errors at compile time
- **Powerful:** Full JavaScript expressions inside markup
- **Optimized:** React compiles JSX to optimized JavaScript

#### JSX Rules

1. **Single Parent Element:** Must return one root element
2. **Close All Tags:** Self-closing tags must end with `/>`
3. **camelCase Properties:** Use `className` instead of `class`, `onClick` instead of `onclick`
4. **JavaScript Expressions:** Use `{}` to embed expressions

#### JSX vs HTML Differences

| HTML                 | JSX                        |
| -------------------- | -------------------------- |
| `class`              | `className`                |
| `for`                | `htmlFor`                  |
| `onclick`            | `onClick`                  |
| `tabindex`           | `tabIndex`                 |
| `style="color: red"` | `style={{ color: 'red' }}` |

#### JSX Compilation

JSX is not valid JavaScript. It gets transpiled by Babel:

```javascript
// JSX
const element = <h1>Hello, World!</h1>;

// Compiled to
const element = React.createElement("h1", null, "Hello, World!");
```

#### Interview Questions on JSX

**Q: Is JSX mandatory in React?**
A: No, but it's highly recommended. You can use `React.createElement()` directly, but it's verbose and less readable.

**Q: Can browsers read JSX?**
A: No, browsers cannot read JSX directly. It must be transpiled to JavaScript using tools like Babel.

**Q: Why use className instead of class?**
A: Because `class` is a reserved keyword in JavaScript. JSX is JavaScript, so it uses `className`.

**Q: Can you write if-else in JSX?**
A: No, you cannot use if-else statements directly in JSX. Use ternary operators or logical && operator instead.

### 2.2 Components

Components are the building blocks of React applications. They are independent, reusable pieces of UI.

#### Types of Components

**1. Functional Components (Modern Approach)**

- Simple JavaScript functions
- Can use hooks
- Recommended for all new code

**2. Class Components (Legacy)**

- ES6 classes extending React.Component
- Have lifecycle methods
- Being phased out in favor of functional components

#### Functional Component Characteristics

- Pure JavaScript functions
- Return JSX
- Can accept props
- Can use hooks for state and side effects
- Simpler and more concise

#### Component Naming Convention

- Always start with a capital letter
- Use PascalCase: `UserProfile`, `NavBar`, `ProductCard`
- File name should match component name

#### Component Best Practices

1. **Single Responsibility:** One component, one purpose
2. **Small and Focused:** Keep components under 200 lines
3. **Reusability:** Design for reuse
4. **Props Validation:** Use PropTypes or TypeScript
5. **Consistent Naming:** Follow naming conventions
6. **File Organization:** One component per file

#### Interview Questions on Components

**Q: What is the difference between functional and class components?**
A: Functional components are simple functions that return JSX and can use hooks. Class components are ES6 classes with lifecycle methods. Functional components are now preferred as they're simpler and hooks provide all the functionality of class components.

**Q: Can functional components have state?**
A: Yes, with the `useState` hook introduced in React 16.8, functional components can have state.

**Q: What are Pure Components?**
A: Pure Components are components that render the same output for the same props and state. They implement `shouldComponentUpdate()` with shallow prop and state comparison to avoid unnecessary re-renders.

**Q: When should you use a class component?**
A: In modern React (16.8+), there's rarely a need for class components. Use them only when working with legacy code or when you need Error Boundaries (though this may change).

### 2.3 Props

Props (short for properties) are arguments passed to React components. They allow data to flow from parent to child components.

#### Props Characteristics

- **Read-Only:** Cannot be modified by the receiving component
- **Unidirectional:** Flow from parent to child (one-way data flow)
- **Any Data Type:** Can pass strings, numbers, objects, arrays, functions
- **Immutable:** Props should never be mutated

#### Props vs State

| Props                    | State                        |
| ------------------------ | ---------------------------- |
| Passed from parent       | Managed within component     |
| Immutable                | Mutable                      |
| Controlled by parent     | Controlled by component      |
| Can be changed by parent | Changed by setState/useState |

#### Default Props

You can set default values for props.

#### Props Destructuring

Cleaner way to access props.

#### Props Validation with PropTypes

Validate prop types in development.

#### Children Prop

Special prop that contains content between component tags.

#### Interview Questions on Props

**Q: Can you modify props inside a component?**
A: No, props are read-only. Modifying props directly is an anti-pattern. If you need to modify data, use state instead.

**Q: What is prop drilling?**
A: Prop drilling is passing props through multiple levels of components to reach a deeply nested component. It can be solved using Context API or state management libraries.

**Q: How to pass data from child to parent?**
A: Pass a callback function from parent to child as a prop. The child can call this function with data, effectively sending data back to parent.

**Q: What are render props?**
A: Render props is a pattern where a component receives a function as a prop that returns a React element, allowing code reuse and sharing logic between components.

### 2.4 State

State is a built-in object that stores component data that can change over time. When state changes, the component re-renders.

#### State Characteristics

- **Mutable:** Can be changed using setState or useState
- **Local:** Belongs to the component
- **Asynchronous:** State updates may be batched
- **Triggers Re-render:** Changing state causes component to re-render

#### useState Hook

The primary way to manage state in functional components.

#### State Update Rules

1. **Never Mutate State Directly:** Always use setState or the setter function
2. **State Updates May Be Asynchronous:** React may batch multiple updates
3. **State Updates Are Merged:** In class components, setState merges objects
4. **Use Functional Updates:** When new state depends on previous state

#### Multiple State Variables

You can use multiple useState hooks in a single component.

#### State with Objects and Arrays

When updating objects or arrays, create new copies.

#### Interview Questions on State

**Q: What is the difference between state and props?**
A: State is managed within the component and can be changed. Props are passed from parent and are read-only.

**Q: Why is state immutable?**
A: Immutability helps React detect changes efficiently, enables time-travel debugging, and prevents bugs from unexpected mutations.

**Q: Can you use state in functional components?**
A: Yes, using the useState hook introduced in React 16.8.

**Q: What happens when you call setState?**
A: React schedules a re-render of the component. The update may be batched with other updates for performance. The component re-renders with the new state.

**Q: How to update state based on previous state?**
A: Use the functional form of setState: `setState(prevState => prevState + 1)` to ensure you're working with the latest state.

### 2.5 Virtual DOM

The Virtual DOM is a lightweight copy of the actual DOM kept in memory. React uses it to optimize updates and improve performance.

#### How Virtual DOM Works

1. **Initial Render:** React creates a Virtual DOM tree
2. **State/Props Change:** React creates a new Virtual DOM tree
3. **Diffing:** React compares new Virtual DOM with previous one
4. **Reconciliation:** React calculates minimal changes needed
5. **Update:** React updates only changed parts in real DOM

#### Virtual DOM vs Real DOM

| Virtual DOM                | Real DOM                 |
| -------------------------- | ------------------------ |
| Lightweight copy           | Heavy, browser-rendered  |
| Fast to update             | Slow to update           |
| Can't directly update HTML | Can directly update HTML |
| Updates are batched        | Updates are expensive    |
| Memory efficient           | Memory intensive         |

#### Why Virtual DOM is Fast

- **Batching:** Multiple updates are batched together
- **Minimal Updates:** Only changed elements are updated
- **Efficient Diffing:** Smart algorithm to find differences
- **No Layout Thrashing:** Avoids multiple reflows/repaints

#### Interview Questions on Virtual DOM

**Q: What is Virtual DOM?**
A: Virtual DOM is a lightweight JavaScript representation of the real DOM. React uses it to optimize updates by comparing versions and updating only what changed.

**Q: How does Virtual DOM improve performance?**
A: By minimizing direct DOM manipulations, batching updates, and updating only changed elements rather than re-rendering the entire page.

**Q: What is the difference between Shadow DOM and Virtual DOM?**
A: Shadow DOM is a browser technology for scoping CSS and markup in web components. Virtual DOM is a concept implemented by libraries like React for optimizing DOM updates.

**Q: Does Virtual DOM make React faster than direct DOM manipulation?**
A: Not always. For simple updates, direct DOM manipulation can be faster. Virtual DOM shines in complex applications with frequent updates.

### 2.6 Reconciliation Algorithm

Reconciliation is the process React uses to diff the Virtual DOM trees and determine what needs to be updated in the real DOM.

#### Diffing Algorithm

React uses a heuristic O(n) algorithm based on two assumptions:

1. **Different Types = Different Trees:** Elements of different types produce different trees
2. **Keys:** Developers can hint which children are stable across renders using keys

#### Reconciliation Process

1. **Element Type Comparison**

   - Different types: Destroy old tree, build new tree
   - Same type: Keep DOM node, update changed attributes

2. **Component Comparison**

   - Same type: Instance stays same, update props
   - Different type: Unmount old, mount new

3. **Recursion on Children**
   - React iterates over children simultaneously
   - Uses keys to match children in old and new lists

#### Keys in React

Keys help React identify which items have changed, been added, or removed.

**Key Rules:**

- Must be unique among siblings
- Should be stable (not random or index-based for dynamic lists)
- Should not change between renders

**Bad Practice:**

```javascript
// Using index as key (problematic with dynamic lists)
items.map((item, index) => <li key={index}>{item}</li>);
```

**Good Practice:**

```javascript
// Using unique ID
items.map((item) => <li key={item.id}>{item.name}</li>);
```

#### Interview Questions on Reconciliation

**Q: What is reconciliation in React?**
A: Reconciliation is the algorithm React uses to diff Virtual DOM trees and determine the minimal set of changes needed to update the real DOM.

**Q: Why are keys important in React?**
A: Keys help React identify which items have changed, been added, or removed in lists. They optimize re-rendering by helping React match elements between renders.

**Q: Can you use index as a key?**
A: It's not recommended for dynamic lists where items can be reordered, added, or removed. It can cause performance issues and bugs. Use stable unique IDs instead.

**Q: What happens if you don't provide keys?**
A: React will use the index as a key by default and show a warning. This can lead to performance issues and incorrect behavior with dynamic lists.

### 2.7 React Fiber Architecture

React Fiber is a complete rewrite of React's core algorithm, introduced in React 16. It enables incremental rendering and better handling of updates.

#### What is Fiber?

Fiber is a reimplementation of React's reconciliation algorithm that:

- Breaks rendering work into chunks
- Prioritizes updates
- Pauses and resume work
- Reuses previously completed work
- Aborts work if not needed

#### Key Features

1. **Incremental Rendering:** Split work into chunks and spread over multiple frames
2. **Prioritization:** Different types of updates have different priorities
3. **Concurrency:** Ability to work on multiple tasks simultaneously
4. **Better Error Handling:** Error boundaries

#### Fiber Phases

**1. Render Phase (Asynchronous)**

- Can be paused, aborted, or restarted
- Builds the work-in-progress tree
- No side effects

**2. Commit Phase (Synchronous)**

- Cannot be interrupted
- Updates the DOM
- Runs lifecycle methods and effects

#### Priority Levels

- **Immediate:** Text input, user interactions
- **User-Blocking:** Hover effects, scrolling
- **Normal:** Data fetching, animations
- **Low:** Analytics, logging
- **Idle:** Background tasks

#### Interview Questions on Fiber

**Q: What is React Fiber?**
A: React Fiber is a reimplementation of React's core algorithm that enables incremental rendering, allowing React to split work into chunks and prioritize updates.

**Q: Why was Fiber introduced?**
A: To improve React's ability to handle animations, layout, gestures, and to enable features like Suspense and Concurrent Mode by making rendering interruptible.

**Q: What is the difference between Stack Reconciler and Fiber Reconciler?**
A: Stack Reconciler (old) was synchronous and couldn't be interrupted. Fiber Reconciler is asynchronous, can pause/resume work, and prioritizes updates.

**Q: How does Fiber improve performance?**
A: By breaking work into chunks, prioritizing important updates, and avoiding blocking the main thread for long periods, resulting in smoother user experiences.

---

## 3. React Hooks

### 3.1 Introduction to Hooks

Hooks are functions that let you "hook into" React state and lifecycle features from functional components. Introduced in React 16.8.

#### Why Hooks?

**Problems with Class Components:**

- Complex lifecycle methods
- `this` keyword confusion
- Difficult to reuse stateful logic
- Large components hard to maintain
- Classes don't minify well

**Benefits of Hooks:**

- Use state without classes
- Reuse stateful logic easily
- Organize code by feature, not lifecycle
- Simpler and more readable
- Better code splitting

#### Rules of Hooks

1. **Only Call at Top Level:** Don't call hooks inside loops, conditions, or nested functions
2. **Only Call from React Functions:** Call from functional components or custom hooks
3. **Use ESLint Plugin:** `eslint-plugin-react-hooks` enforces these rules

#### Built-in Hooks

**Basic Hooks:**

- useState
- useEffect
- useContext

**Additional Hooks:**

- useReducer
- useCallback
- useMemo
- useRef
- useImperativeHandle
- useLayoutEffect
- useDebugValue

### 3.2 useState Hook

`useState` allows you to add state to functional components.

#### Syntax

```javascript
const [state, setState] = useState(initialValue);
```

#### Key Points

- Returns array with current state and setter function
- Initial value is used only on first render
- Can have multiple useState calls
- State updates trigger re-renders
- Setter function can accept value or updater function

#### Lazy Initial State

For expensive computations, pass a function to useState.

#### Functional Updates

When new state depends on previous state, use functional form.

#### Interview Questions on useState

**Q: What does useState return?**
A: An array with two elements: current state value and a function to update it.

**Q: Can you use useState conditionally?**
A: No, hooks must be called at the top level. Conditional logic should be inside the component, not around the hook call.

**Q: What happens if you call setState with the same value?**
A: React may skip re-rendering the component and its children (bailout optimization).

**Q: Is setState synchronous or asynchronous?**
A: State updates are asynchronous and may be batched for performance. Use functional updates or useEffect to work with updated state.

### 3.3 useEffect Hook

`useEffect` lets you perform side effects in functional components. It combines `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

#### Syntax

```javascript
useEffect(() => {
  // Side effect code
  return () => {
    // Cleanup code
  };
}, [dependencies]);
```

#### Use Cases

- Data fetching
- Subscriptions
- Manually changing DOM
- Timers
- Logging
- Event listeners

#### Dependency Array

- **No array:** Runs after every render
- **Empty array []:** Runs once after initial render
- **[dep1, dep2]:** Runs when dependencies change

#### Cleanup Function

Return a function from useEffect to clean up side effects.

#### Common Patterns

**1. Run Once (Component Mount)**

```javascript
useEffect(() => {
  // Runs once
}, []);
```

**2. Run on Dependency Change**

```javascript
useEffect(() => {
  // Runs when count changes
}, [count]);
```

**3. Run on Every Render**

```javascript
useEffect(() => {
  // Runs after every render
});
```

#### Interview Questions on useEffect

**Q: What is useEffect used for?**
A: For performing side effects in functional components like data fetching, subscriptions, or manually changing the DOM.

**Q: When does useEffect run?**
A: By default, after every render. You can control this with the dependency array.

**Q: What is the cleanup function in useEffect?**
A: A function returned from useEffect that runs before the component unmounts or before the effect runs again. Used to clean up subscriptions, timers, etc.

**Q: Can you use async/await in useEffect?**
A: Not directly. useEffect expects a cleanup function or nothing. Create an async function inside useEffect and call it.

**Q: What's the difference between useEffect and useLayoutEffect?**
A: useEffect runs asynchronously after paint. useLayoutEffect runs synchronously after DOM mutations but before paint. Use useLayoutEffect when you need to read layout or synchronously re-render.

### 3.4 useContext Hook

`useContext` lets you subscribe to React context without nesting.

#### Context API Flow

1. Create context with `createContext()`
2. Provide value with `Context.Provider`
3. Consume value with `useContext()`

#### When to Use Context

- Theme data (dark/light mode)
- User authentication
- Language/locale
- UI state (modals, notifications)

**Don't Use for:**

- Frequent updates (performance issues)
- All state management (overkill for local state)

#### Interview Questions on useContext

**Q: What is useContext?**
A: A hook that lets you subscribe to React context and access its value without prop drilling.

**Q: When should you use Context API?**
A: For global data that many components need, like theme, user info, or language settings.

**Q: What are the performance implications of Context?**
A: All consumers re-render when context value changes. For frequently changing values, consider state management libraries or splitting contexts.

**Q: Can you have multiple contexts?**
A: Yes, you can create and use multiple contexts in the same application.

### 3.5 useReducer Hook

`useReducer` is an alternative to useState for complex state logic. Similar to Redux reducers.

#### When to Use useReducer

- Complex state logic with multiple sub-values
- Next state depends on previous state
- State transitions need to be predictable
- Want to optimize performance with deep updates

#### useReducer vs useState

| useState            | useReducer           |
| ------------------- | -------------------- |
| Simple state        | Complex state        |
| Independent updates | Related updates      |
| Few state variables | Many state variables |
| Direct updates      | Action-based updates |

#### Interview Questions on useReducer

**Q: When should you use useReducer over useState?**
A: When state logic is complex, involves multiple sub-values, or when next state depends on previous state.

**Q: What is a reducer function?**
A: A pure function that takes current state and an action, and returns new state: `(state, action) => newState`

**Q: Can you use useReducer with useContext?**
A: Yes, this is a common pattern for state management, similar to Redux but with React's built-in tools.

### 3.6 useRef Hook

`useRef` returns a mutable ref object whose `.current` property persists across renders.

#### Use Cases

1. **Accessing DOM elements**
2. **Storing mutable values** that don't trigger re-renders
3. **Keeping previous values**
4. **Storing timers/intervals**

#### useRef vs useState

| useRef                    | useState             |
| ------------------------- | -------------------- |
| Doesn't trigger re-render | Triggers re-render   |
| Mutable                   | Immutable            |
| Synchronous updates       | Asynchronous updates |
| For DOM/values            | For UI state         |

#### Interview Questions on useRef

**Q: What is useRef used for?**
A: To access DOM elements directly or to store mutable values that persist across renders without causing re-renders.

**Q: What's the difference between useRef and useState?**
A: useRef doesn't trigger re-renders when updated, while useState does. useRef is synchronous, useState is asynchronous.

**Q: Can you use useRef for storing previous values?**
A: Yes, it's a common pattern to store previous props or state values using useRef.

### 3.7 useMemo Hook

`useMemo` memoizes expensive computations and returns cached value until dependencies change.

#### When to Use useMemo

- Expensive calculations
- Referential equality needed
- Preventing unnecessary child re-renders
- Optimizing performance

#### When NOT to Use useMemo

- Simple calculations (overhead not worth it)
- Every computation (premature optimization)
- As a semantic guarantee (React may discard cached values)

#### Interview Questions on useMemo

**Q: What is useMemo?**
A: A hook that memoizes the result of an expensive computation and only recalculates when dependencies change.

**Q: When should you use useMemo?**
A: For expensive calculations or when you need referential equality for objects/arrays passed as props.

**Q: What's the difference between useMemo and useCallback?**
A: useMemo memoizes a computed value, useCallback memoizes a function.

### 3.8 useCallback Hook

`useCallback` memoizes functions and returns cached function until dependencies change.

#### When to Use useCallback

- Passing callbacks to optimized child components
- Dependencies in useEffect
- Preventing unnecessary re-renders
- Event handlers in lists

#### useCallback vs useMemo

```javascript
// These are equivalent:
useCallback(fn, deps);
useMemo(() => fn, deps);
```

#### Interview Questions on useCallback

**Q: What is useCallback?**
A: A hook that returns a memoized version of a callback function that only changes if dependencies change.

**Q: Why use useCallback?**
A: To prevent unnecessary re-renders of child components that depend on reference equality, and to optimize performance.

**Q: When is useCallback useful?**
A: When passing callbacks to optimized child components wrapped in React.memo, or when functions are dependencies in useEffect.

### 3.9 useLayoutEffect Hook

`useLayoutEffect` is identical to useEffect but fires synchronously after all DOM mutations.

#### useEffect vs useLayoutEffect

| useEffect      | useLayoutEffect  |
| -------------- | ---------------- |
| Asynchronous   | Synchronous      |
| After paint    | Before paint     |
| Non-blocking   | Blocking         |
| Most use cases | DOM measurements |

#### When to Use useLayoutEffect

- Reading layout from DOM
- Synchronously re-rendering
- Preventing visual flickering
- Measuring DOM nodes

#### Interview Questions on useLayoutEffect

**Q: What's the difference between useEffect and useLayoutEffect?**
A: useLayoutEffect fires synchronously after DOM mutations but before paint, while useEffect fires asynchronously after paint.

**Q: When should you use useLayoutEffect?**
A: When you need to read layout from the DOM and synchronously re-render, or to prevent visual flickering.

### 3.10 useImperativeHandle Hook

`useImperativeHandle` customizes the instance value exposed when using ref with forwardRef.

#### When to Use

- Exposing specific methods to parent
- Abstracting DOM operations
- Creating reusable components with imperative APIs

#### Interview Questions

**Q: What is useImperativeHandle?**
A: A hook that customizes the instance value exposed to parent components when using ref.

**Q: When should you use useImperativeHandle?**
A: When you need to expose specific methods to parent components while keeping implementation details hidden.

### 3.11 Custom Hooks

Custom hooks let you extract component logic into reusable functions.

#### Rules for Custom Hooks

1. Name must start with "use"
2. Can call other hooks
3. Must follow hooks rules
4. Each call has isolated state

#### Common Custom Hooks

- useLocalStorage
- useFetch
- useDebounce
- useToggle
- useWindowSize
- usePrevious
- useOnClickOutside

#### Interview Questions on Custom Hooks

**Q: What are custom hooks?**
A: JavaScript functions that use React hooks and can be reused across components to share stateful logic.

**Q: Why create custom hooks?**
A: To extract and reuse component logic, making code more maintainable and reducing duplication.

**Q: Can custom hooks call other hooks?**
A: Yes, custom hooks can call any React hooks or other custom hooks.

**Q: Do custom hooks share state?**
A: No, each call to a custom hook has completely isolated state.

---

## 4. Component Lifecycle

### 4.1 Class Component Lifecycle

Class components have lifecycle methods that run at specific points in a component's life.

#### Lifecycle Phases

1. **Mounting:** Component is being created and inserted into DOM
2. **Updating:** Component is being re-rendered due to changes in props or state
3. **Unmounting:** Component is being removed from DOM
4. **Error Handling:** Error occurred during rendering, in lifecycle method, or in constructor

### 4.2 Lifecycle Methods

#### Mounting Phase

1. **constructor()**

   - Initialize state
   - Bind event handlers
   - Don't call setState here

2. **static getDerivedStateFromProps()**

   - Sync state with props
   - Rarely used
   - Returns object to update state or null

3. **render()**

   - Required method
   - Returns JSX
   - Should be pure

4. **componentDidMount()**
   - Runs after component is mounted
   - Perfect for API calls, subscriptions
   - Can call setState (triggers re-render)

#### Updating Phase

1. **static getDerivedStateFromProps()**

   - Called before every render

2. **shouldComponentUpdate()**

   - Performance optimization
   - Return false to skip render
   - Not called for initial render

3. **render()**

   - Re-renders component

4. **getSnapshotBeforeUpdate()**

   - Capture information before DOM changes
   - Return value passed to componentDidUpdate

5. **componentDidUpdate()**
   - Runs after update
   - Good for API calls based on prop changes
   - Can call setState (with condition)

#### Unmounting Phase

**componentWillUnmount()**

- Cleanup subscriptions, timers
- Cancel network requests
- Don't call setState

#### Error Handling

1. **static getDerivedStateFromError()**

   - Update state to show fallback UI
   - Called during render phase

2. **componentDidCatch()**
   - Log error information
   - Called during commit phase

### 4.3 Lifecycle with Hooks

Hooks equivalent to lifecycle methods:

| Class Component          | Hooks Equivalent                          |
| ------------------------ | ----------------------------------------- |
| constructor              | useState                                  |
| componentDidMount        | useEffect(() => {}, [])                   |
| componentDidUpdate       | useEffect(() => {}, [deps])               |
| componentWillUnmount     | useEffect cleanup function                |
| shouldComponentUpdate    | React.memo                                |
| getDerivedStateFromProps | useState + useEffect                      |
| componentDidCatch        | No direct equivalent (use Error Boundary) |

#### Interview Questions on Lifecycle

**Q: What are lifecycle methods?**
A: Special methods in class components that run at specific points in a component's life: mounting, updating, and unmounting.

**Q: What is componentDidMount used for?**
A: For side effects that should run once after the component is mounted, like API calls, subscriptions, or DOM manipulations.

**Q: What's the difference between componentDidMount and componentDidUpdate?**
A: componentDidMount runs once after initial render. componentDidUpdate runs after every update (except initial render).

**Q: How do you implement componentDidMount with hooks?**
A: Use `useEffect(() => { /* code */ }, [])` with empty dependency array.

**Q: Why is componentWillMount deprecated?**
A: It caused confusion and bugs. Most use cases are better handled in componentDidMount or constructor.

---

## 5. State Management

### 5.1 Lifting State Up

Lifting state up is moving state to the closest common ancestor of components that need it.

#### When to Lift State Up

- Multiple components need same data
- Components need to communicate
- Shared state between siblings

#### Prop Drilling Problem

Passing props through many levels of components becomes cumbersome.

**Solutions:**

- Context API
- State management libraries (Redux, Zustand)
- Component composition

### 5.2 Context API

Context provides a way to pass data through component tree without prop drilling.

#### Context Best Practices

1. **Split Contexts:** Don't put everything in one context
2. **Memoize Values:** Prevent unnecessary re-renders
3. **Use with useReducer:** For complex state logic
4. **Don't Overuse:** Not all state needs context

#### Performance Optimization

Context consumers re-render when value changes. Optimize by:

- Splitting contexts
- Memoizing context value
- Using composition
- Using selectors

### 5.3 Redux Fundamentals

Redux is a predictable state container for JavaScript apps.

#### Core Principles

1. **Single Source of Truth:** One store for entire app
2. **State is Read-Only:** Only way to change state is dispatch action
3. **Changes Made with Pure Functions:** Reducers are pure functions

#### Redux Flow

1. Component dispatches action
2. Action sent to reducer
3. Reducer updates state
4. Store notifies subscribers
5. Component re-renders with new state

#### Key Concepts

**Store:** Holds application state
**Actions:** Plain objects describing what happened
**Reducers:** Pure functions that specify how state changes
**Dispatch:** Method to send actions to store
**Selectors:** Functions to extract data from store

#### When to Use Redux

- Large applications
- Shared state across many components
- State changes frequently
- Complex state update logic
- Need for time-travel debugging

#### When NOT to Use Redux

- Small applications
- State is mostly local
- Simple state logic
- Learning React (learn React first)

### 5.4 Redux Toolkit

Redux Toolkit (RTK) is the official, opinionated toolset for Redux development.

#### Why Redux Toolkit?

- Less boilerplate
- Built-in best practices
- Simplified store setup
- Immutability with Immer
- Better TypeScript support

#### Key APIs

**configureStore:** Simplified store setup
**createSlice:** Combines actions and reducers
**createAsyncThunk:** Handle async logic
**createEntityAdapter:** CRUD operations for normalized state

### 5.5 Zustand

Zustand is a small, fast, and scalable state management solution.

#### Why Zustand?

- Minimal boilerplate
- No providers needed
- Easy to learn
- Great TypeScript support
- Small bundle size (~1KB)

#### Zustand vs Redux

| Zustand        | Redux            |
| -------------- | ---------------- |
| Minimal setup  | More boilerplate |
| No providers   | Needs provider   |
| Simple API     | Complex API      |
| Smaller bundle | Larger bundle    |
| Less tooling   | Rich ecosystem   |

### 5.6 Recoil

Recoil is a state management library for React by Facebook.

#### Key Concepts

**Atoms:** Units of state
**Selectors:** Derived state
**RecoilRoot:** Provider component

#### Why Recoil?

- React-like API
- Minimal boilerplate
- Excellent performance
- Built for React
- Async support

### 5.7 State Management Comparison

| Feature        | Context | Redux      | Zustand   | Recoil    |
| -------------- | ------- | ---------- | --------- | --------- |
| Learning Curve | Easy    | Steep      | Easy      | Moderate  |
| Boilerplate    | Low     | High       | Minimal   | Low       |
| Bundle Size    | 0KB     | ~12KB      | ~1KB      | ~14KB     |
| DevTools       | No      | Yes        | Yes       | Yes       |
| Async          | Manual  | Middleware | Built-in  | Built-in  |
| TypeScript     | Good    | Excellent  | Excellent | Good      |
| Performance    | Good    | Excellent  | Excellent | Excellent |

#### Interview Questions on State Management

**Q: What is state management?**
A: The process of managing and synchronizing state across multiple components in an application.

**Q: When should you use a state management library?**
A: When you have complex state logic, many components sharing state, or need features like time-travel debugging.

**Q: What is the difference between local and global state?**
A: Local state is managed within a component. Global state is shared across multiple components.

**Q: What is Redux?**
A: A predictable state container that implements Flux architecture with a single store, actions, and reducers.

**Q: What are Redux middleware?**
A: Functions that intercept actions before they reach reducers, used for async logic, logging, etc.

**Q: What is the difference between Redux and Context API?**
A: Redux is a full state management library with middleware, DevTools, and time-travel. Context is a React feature for passing data without prop drilling.

---

## 6. Routing

### 6.1 React Router Basics

React Router is the standard routing library for React.

#### Core Components

**BrowserRouter:** Uses HTML5 history API
**HashRouter:** Uses URL hash
**Routes:** Container for Route components
**Route:** Defines path and component mapping
**Link:** Navigation without page reload
**NavLink:** Link with active state styling

#### React Router v6 Changes

- `<Routes>` replaces `<Switch>`
- `element` prop instead of `component`
- Nested routes simplified
- Relative paths by default
- `useNavigate` instead of `useHistory`

### 6.2 Dynamic Routing

Dynamic routes use URL parameters to render different content.

#### URL Parameters

Access with `useParams()` hook.

#### Query Parameters

Access with `useSearchParams()` hook.

### 6.3 Nested Routes

Routes can be nested to create complex layouts.

#### Outlet Component

Renders child routes inside parent route.

### 6.4 Protected Routes

Routes that require authentication.

### 6.5 Programmatic Navigation

Navigate programmatically using `useNavigate` hook.

#### Interview Questions on Routing

**Q: What is React Router?**
A: A library for handling routing in React applications, enabling navigation without page reloads.

**Q: What's the difference between Link and NavLink?**
A: NavLink has additional features like active state styling and aria-current attribute.

**Q: How do you implement protected routes?**
A: Create a wrapper component that checks authentication and redirects to login if not authenticated.

**Q: What's the difference between BrowserRouter and HashRouter?**
A: BrowserRouter uses HTML5 history API (clean URLs). HashRouter uses URL hash (works without server configuration).

**Q: How do you access URL parameters?**
A: Use the `useParams()` hook to access dynamic route parameters.

---

## 7. Forms and Validation

### 7.1 Controlled Components

Components where form data is handled by React state.

#### Characteristics

- React state is source of truth
- Value controlled by React
- Updates via onChange handler
- Predictable and testable

### 7.2 Uncontrolled Components

Components where form data is handled by DOM itself.

#### When to Use Uncontrolled

- File inputs
- Integration with non-React code
- Simple forms
- Performance optimization

#### Controlled vs Uncontrolled

| Controlled            | Uncontrolled         |
| --------------------- | -------------------- |
| React manages state   | DOM manages state    |
| Value from state      | Value from ref       |
| More code             | Less code            |
| Instant validation    | Validation on submit |
| Conditional rendering | Limited control      |

### 7.3 Form Libraries (Formik, React Hook Form)

#### Formik

Popular form library with validation support.

**Features:**

- Form state management
- Validation (Yup integration)
- Error handling
- Touched fields tracking

#### React Hook Form

Performance-focused form library using uncontrolled components.

**Features:**

- Minimal re-renders
- Smaller bundle size
- Better performance
- Easy integration

#### Formik vs React Hook Form

| Feature        | Formik   | React Hook Form |
| -------------- | -------- | --------------- |
| Performance    | Good     | Excellent       |
| Bundle Size    | ~13KB    | ~9KB            |
| Re-renders     | More     | Minimal         |
| Learning Curve | Moderate | Easy            |
| Validation     | Yup      | Built-in + Yup  |

### 7.4 Form Validation

#### Client-Side Validation

**Built-in HTML5:**

- required
- pattern
- min/max
- type

**Custom Validation:**

- Manual validation logic
- Validation libraries (Yup, Zod)

#### Validation Libraries

**Yup:** Schema-based validation
**Zod:** TypeScript-first validation
**Joi:** Object schema validation

#### Interview Questions on Forms

**Q: What are controlled components?**
A: Components where form data is handled by React state, making React the single source of truth.

**Q: When should you use uncontrolled components?**
A: For file inputs, simple forms, or when integrating with non-React code.

**Q: What is the difference between Formik and React Hook Form?**
A: React Hook Form uses uncontrolled components and has better performance with fewer re-renders. Formik uses controlled components and has more re-renders but simpler API.

**Q: How do you handle file uploads in React?**
A: Use uncontrolled components with useRef to access file input, or use FormData API to send files to server.

---

## 8. Performance Optimization

### 8.1 React.memo

`React.memo` is a higher-order component that memoizes component output.

#### When to Use React.memo

- Pure functional components
- Component renders often with same props
- Component is expensive to render
- Parent re-renders frequently

#### When NOT to Use

- Component always renders with different props
- Optimization overhead > render cost
- Premature optimization

#### Shallow Comparison

React.memo does shallow comparison of props by default.

### 8.2 Code Splitting

Code splitting breaks bundle into smaller chunks loaded on demand.

#### Benefits

- Faster initial load
- Reduced bundle size
- Better user experience
- Improved performance

#### Route-Based Splitting

Split code by routes for optimal loading.

### 8.3 Lazy Loading

Lazy loading defers loading of components until needed.

#### React.lazy

Dynamic import for components.

### 8.4 Suspense

Suspense lets components "wait" for something before rendering.

#### Use Cases

- Code splitting
- Data fetching (experimental)
- Image loading
- Lazy components

### 8.5 Profiler and DevTools

#### React DevTools

Browser extension for debugging React applications.

**Features:**

- Component tree inspection
- Props and state viewing
- Performance profiling
- Hooks debugging

#### Profiler API

Measure rendering performance programmatically.

### 8.6 Debouncing and Throttling

#### Debouncing

Delay function execution until after wait time.

**Use Cases:**

- Search input
- Form validation
- Window resize

#### Throttling

Limit function execution to once per time period.

**Use Cases:**

- Scroll events
- Mouse move
- API calls

### 8.7 Virtualization

Render only visible items in large lists.

#### Libraries

**react-window:** Lightweight virtualization
**react-virtualized:** Feature-rich virtualization

#### Benefits

- Render only visible items
- Constant performance regardless of list size
- Reduced memory usage

#### Interview Questions on Performance

**Q: What is React.memo?**
A: A higher-order component that memoizes component output and only re-renders if props change.

**Q: What is code splitting?**
A: Breaking bundle into smaller chunks that can be loaded on demand, improving initial load time.

**Q: What's the difference between useMemo and React.memo?**
A: useMemo memoizes values, React.memo memoizes entire component output.

**Q: What is lazy loading?**
A: Deferring loading of components or resources until they're needed, reducing initial bundle size.

**Q: How do you optimize list rendering?**
A: Use keys, virtualization (react-window), memoization, and avoid inline functions in list items.

**Q: What's the difference between debouncing and throttling?**
A: Debouncing delays execution until after wait time. Throttling limits execution to once per time period.

---

## 9. Advanced Patterns

### 9.1 Higher-Order Components (HOC)

HOC is a function that takes a component and returns a new component.

#### Use Cases

- Code reuse
- Props manipulation
- State abstraction
- Render hijacking

#### HOC Best Practices

1. Don't mutate original component
2. Pass unrelated props through
3. Maximize composability
4. Wrap display name for debugging
5. Don't use HOCs in render method

#### HOC vs Hooks

Hooks are generally preferred over HOCs in modern React.

### 9.2 Render Props

Pattern for sharing code using a prop whose value is a function.

#### When to Use Render Props

- Sharing stateful logic
- Flexible rendering
- Cross-cutting concerns

#### Render Props vs Hooks

Hooks provide cleaner way to share logic without nesting.

### 9.3 Compound Components

Pattern where components work together to form a complete UI.

#### Benefits

- Flexible API
- Separation of concerns
- Implicit state sharing
- Better composition

### 9.4 Controlled vs Uncontrolled Components

#### Controlled Components

- React controls the value
- Single source of truth
- More predictable

#### Uncontrolled Components

- DOM controls the value
- Use refs to access value
- Less code

### 9.5 Error Boundaries

Components that catch JavaScript errors in child component tree.

#### Limitations

Error boundaries don't catch:

- Event handlers
- Asynchronous code
- Server-side rendering
- Errors in error boundary itself

#### Best Practices

- Place error boundaries strategically
- Log errors to service
- Show user-friendly fallback
- Don't use for control flow

### 9.6 Portals

Portals render children into DOM node outside parent hierarchy.

#### Use Cases

- Modals
- Tooltips
- Dropdowns
- Notifications

### 9.7 Refs and Forward Refs

#### Refs

Access DOM nodes or React elements directly.

#### Forward Refs

Pass refs through component to child.

#### When to Use Refs

- Managing focus
- Text selection
- Media playback
- Triggering animations
- Integration with third-party DOM libraries

#### Interview Questions on Advanced Patterns

**Q: What is a Higher-Order Component?**
A: A function that takes a component and returns a new enhanced component, used for code reuse and logic abstraction.

**Q: What are render props?**
A: A pattern where a component receives a function as a prop that returns a React element, enabling code sharing.

**Q: What are error boundaries?**
A: Components that catch JavaScript errors in child component tree, log errors, and display fallback UI.

**Q: What are portals used for?**
A: Rendering children into a DOM node outside the parent component hierarchy, useful for modals and tooltips.

**Q: When should you use refs?**
A: For accessing DOM nodes directly, managing focus, text selection, or integrating with third-party DOM libraries.

---

## 10. API Integration

### 10.1 Fetch API

Built-in browser API for making HTTP requests.

#### Fetch Characteristics

- Promise-based
- Built-in to browsers
- No installation needed
- Requires manual error handling

### 10.2 Axios

Popular HTTP client library.

#### Axios vs Fetch

| Feature         | Axios     | Fetch           |
| --------------- | --------- | --------------- |
| Installation    | Required  | Built-in        |
| JSON Transform  | Automatic | Manual          |
| Error Handling  | Better    | Manual          |
| Interceptors    | Yes       | No              |
| Request Cancel  | Yes       | AbortController |
| Browser Support | Wider     | Modern browsers |

### 10.3 React Query (TanStack Query)

Powerful data fetching and caching library.

#### Features

- Automatic caching
- Background refetching
- Stale data management
- Pagination support
- Optimistic updates
- Request deduplication

#### Key Concepts

**Queries:** Fetch data
**Mutations:** Modify data
**Query Keys:** Unique identifiers
**Cache:** Stores fetched data

#### Benefits

- Less boilerplate
- Automatic caching
- Better UX
- Optimistic updates
- Background refetching

### 10.4 SWR

React hooks library for data fetching by Vercel.

#### Features

- Stale-while-revalidate strategy
- Fast page navigation
- Revalidation on focus
- Interval polling
- Request deduplication

#### SWR vs React Query

| Feature        | SWR     | React Query   |
| -------------- | ------- | ------------- |
| Bundle Size    | Smaller | Larger        |
| Features       | Focused | Comprehensive |
| Learning Curve | Easier  | Moderate      |
| DevTools       | No      | Yes           |
| Mutations      | Basic   | Advanced      |

### 10.5 Error Handling

#### Error Types

1. **Network Errors:** Failed requests
2. **HTTP Errors:** 4xx, 5xx status codes
3. **Parsing Errors:** Invalid JSON
4. **Timeout Errors:** Request took too long

#### Error Handling Strategies

- Try-catch blocks
- Error boundaries
- Error state management
- User-friendly messages
- Retry logic
- Logging

#### Interview Questions on API Integration

**Q: What's the difference between Fetch and Axios?**
A: Axios automatically transforms JSON, has better error handling, and includes interceptors. Fetch is built-in but requires more manual handling.

**Q: What is React Query?**
A: A data fetching and caching library that handles server state with features like automatic caching, background refetching, and optimistic updates.

**Q: What is the stale-while-revalidate strategy?**
A: Serving cached (stale) data immediately while fetching fresh data in the background, providing instant UI updates.

**Q: How do you handle loading states?**
A: Use state variables (isLoading, isError, data) or libraries like React Query that provide these states automatically.

**Q: What are optimistic updates?**
A: Updating UI immediately before server response, assuming success, then reverting if request fails.

---

## 11. Testing

### 11.1 Testing Philosophy

#### Testing Pyramid

1. **Unit Tests (70%):** Test individual functions/components
2. **Integration Tests (20%):** Test component interactions
3. **E2E Tests (10%):** Test complete user flows

#### Testing Principles

- Test behavior, not implementation
- Write tests that resemble user interaction
- Avoid testing implementation details
- Keep tests simple and readable

### 11.2 Jest

JavaScript testing framework.

#### Features

- Zero configuration
- Snapshot testing
- Mocking
- Code coverage
- Parallel test execution

### 11.3 React Testing Library

Testing library focused on user behavior.

#### Philosophy

"The more your tests resemble the way your software is used, the more confidence they can give you."

#### Key Principles

- Query by accessibility
- Test user behavior
- Avoid implementation details
- No shallow rendering

#### Query Priority

1. **getByRole:** Accessibility-first
2. **getByLabelText:** Form elements
3. **getByPlaceholderText:** Placeholder text
4. **getByText:** Non-interactive elements
5. **getByTestId:** Last resort

### 11.4 Component Testing

#### What to Test

- Rendering with different props
- User interactions
- Conditional rendering
- Error states
- Edge cases

#### What NOT to Test

- Implementation details
- Third-party libraries
- Styles (unless critical)
- Exact HTML structure

### 11.5 Integration Testing

Testing how components work together.

#### Focus Areas

- Component communication
- Data flow
- User workflows
- State management

### 11.6 E2E Testing with Cypress

End-to-end testing framework.

#### Features

- Real browser testing
- Time travel debugging
- Automatic waiting
- Network stubbing
- Screenshots and videos

#### Cypress vs Selenium

| Feature         | Cypress    | Selenium  |
| --------------- | ---------- | --------- |
| Setup           | Easy       | Complex   |
| Speed           | Fast       | Slower    |
| Debugging       | Excellent  | Good      |
| Browser Support | Limited    | Extensive |
| Language        | JavaScript | Multiple  |

#### Interview Questions on Testing

**Q: What is React Testing Library?**
A: A testing library that encourages testing components the way users interact with them, focusing on behavior over implementation.

**Q: What's the difference between unit and integration tests?**
A: Unit tests test individual components in isolation. Integration tests test how multiple components work together.

**Q: What is snapshot testing?**
A: Capturing component output and comparing it to saved snapshot to detect unexpected changes.

**Q: How do you test async code?**
A: Use async utilities like waitFor, findBy queries, or act() to handle asynchronous updates.

**Q: What is the testing pyramid?**
A: A testing strategy with many unit tests at the base, fewer integration tests in the middle, and few E2E tests at the top.

---

## 12. TypeScript with React

### 12.1 Why TypeScript?

#### Benefits

- Type safety
- Better IDE support
- Catch errors early
- Self-documenting code
- Refactoring confidence
- Better team collaboration

#### Drawbacks

- Learning curve
- More code to write
- Build step required
- Type definitions needed

### 12.2 Setting Up TypeScript

#### Create New Project

```bash
npx create-react-app my-app --template typescript
# or with Vite
npm create vite@latest my-app -- --template react-ts
```

#### Add to Existing Project

```bash
npm install --save typescript @types/react @types/react-dom
```

### 12.3 Typing Components

#### Functional Components

#### Props with Interface

#### Props with Type

#### Children Prop

### 12.4 Typing Hooks

#### useState

#### useEffect

#### useRef

#### useContext

### 12.5 Generic Components

Components that work with multiple types.

#### Interview Questions on TypeScript

**Q: Why use TypeScript with React?**
A: For type safety, better IDE support, catching errors early, and improved code maintainability.

**Q: What's the difference between interface and type?**
A: Interfaces can be extended and merged, types are more flexible with unions and intersections. Use interfaces for objects, types for unions/intersections.

**Q: How do you type props?**
A: Using interface or type, then passing to component: `const MyComponent: React.FC<Props> = ({ prop1, prop2 }) => { ... }`

**Q: How do you type useState with objects?**
A: Provide type parameter: `useState<User | null>(null)` or let TypeScript infer from initial value.

---

## 13. Styling in React

### 13.1 CSS Modules

CSS files scoped locally to component.

#### Benefits

- Scoped styles
- No naming conflicts
- Composable
- Works with CSS preprocessors

### 13.2 Styled Components

CSS-in-JS library using tagged template literals.

#### Benefits

- Dynamic styling
- Automatic vendor prefixing
- No class name bugs
- Easy theming

### 13.3 Emotion

CSS-in-JS library similar to Styled Components.

#### Benefits

- Better performance
- Smaller bundle
- Source maps
- Framework agnostic

### 13.4 Tailwind CSS

Utility-first CSS framework.

#### Benefits

- Rapid development
- Consistent design
- Small production bundle
- No naming classes

#### Drawbacks

- HTML can look cluttered
- Learning curve
- Customization needed

### 13.5 Material-UI / Chakra UI

Component libraries with built-in styling.

#### Material-UI (MUI)

- Google's Material Design
- Comprehensive components
- Customizable theming

#### Chakra UI

- Accessible components
- Composable
- Dark mode support
- Great DX

#### Interview Questions on Styling

**Q: What are CSS Modules?**
A: CSS files where class names are scoped locally by default, preventing naming conflicts.

**Q: What is CSS-in-JS?**
A: Writing CSS styles in JavaScript files, enabling dynamic styling and component-scoped styles.

**Q: What's the difference between Styled Components and Emotion?**
A: Both are CSS-in-JS libraries. Emotion has better performance and smaller bundle, while Styled Components has larger community.

**Q: When should you use Tailwind CSS?**
A: For rapid development, consistent design systems, and when you prefer utility classes over custom CSS.

---

## 14. React 18+ Features

### 14.1 Concurrent Rendering

React can work on multiple tasks simultaneously and prioritize updates.

#### Benefits

- Better responsiveness
- Smoother animations
- Improved UX
- Interruptible rendering

### 14.2 Automatic Batching

React 18 batches all state updates automatically, even in promises and timeouts.

#### React 17 vs React 18

**React 17:** Only batched in event handlers
**React 18:** Batches everywhere

### 14.3 Transitions

Mark updates as non-urgent to keep UI responsive.

#### useTransition Hook

#### startTransition API

### 14.4 Suspense for Data Fetching

Suspense can now be used for data fetching (with compatible libraries).

#### Benefits

- Declarative loading states
- Better code organization
- Avoid loading state management

### 14.5 Server Components

Components that render on server and send HTML to client.

#### Benefits

- Zero bundle size
- Direct backend access
- Automatic code splitting
- Better performance

#### Server vs Client Components

| Server Components  | Client Components  |
| ------------------ | ------------------ |
| Render on server   | Render on client   |
| No JavaScript sent | JavaScript sent    |
| Can access backend | No backend access  |
| No interactivity   | Full interactivity |
| No hooks           | Can use hooks      |

#### Interview Questions on React 18

**Q: What is concurrent rendering?**
A: A new rendering mechanism where React can work on multiple tasks simultaneously and prioritize updates.

**Q: What is automatic batching?**
A: React 18 feature that batches all state updates automatically, even in promises and timeouts, reducing re-renders.

**Q: What are transitions?**
A: A way to mark updates as non-urgent, allowing React to keep UI responsive during heavy updates.

**Q: What are Server Components?**
A: Components that render on the server and send HTML to client, with zero JavaScript bundle size.

---

## 15. Interview Questions

### 15.1 Fundamental Questions

**Q: What is React?**
A: A JavaScript library for building user interfaces using a component-based architecture and declarative programming model.

**Q: What is JSX?**
A: JavaScript XML - a syntax extension that allows writing HTML-like code in JavaScript files.

**Q: What is the Virtual DOM?**
A: A lightweight JavaScript representation of the real DOM that React uses to optimize updates.

**Q: What are components?**
A: Independent, reusable pieces of UI that can be functional or class-based.

**Q: What is the difference between props and state?**
A: Props are passed from parent and immutable. State is managed within component and mutable.

**Q: What is one-way data flow?**
A: Data flows from parent to child through props, making data flow predictable and easier to debug.

**Q: What is the difference between controlled and uncontrolled components?**
A: Controlled components have form data handled by React state. Uncontrolled have data handled by DOM.

**Q: What are keys in React?**
A: Unique identifiers that help React identify which items have changed, been added, or removed in lists.

**Q: What is prop drilling?**
A: Passing props through multiple levels of components to reach a deeply nested component.

**Q: How do you prevent re-renders?**
A: Use React.memo, useMemo, useCallback, proper key usage, and avoid inline functions/objects.

### 15.2 Hooks Questions

**Q: What are React Hooks?**
A: Functions that let you use state and lifecycle features in functional components.

**Q: What are the rules of hooks?**
A: Only call at top level, only call from React functions, use ESLint plugin to enforce.

**Q: What is useState?**
A: A hook that adds state to functional components, returning current state and setter function.

**Q: What is useEffect?**
A: A hook for performing side effects in functional components, combining mount, update, and unmount lifecycles.

**Q: What is the cleanup function in useEffect?**
A: A function returned from useEffect that runs before component unmounts or before effect runs again.

**Q: What's the difference between useEffect and useLayoutEffect?**
A: useEffect runs asynchronously after paint. useLayoutEffect runs synchronously before paint.

**Q: What is useContext?**
A: A hook that lets you subscribe to React context without nesting.

**Q: What is useReducer?**
A: A hook for managing complex state logic with a reducer function, similar to Redux.

**Q: What is useRef?**
A: A hook that returns a mutable ref object persisting across renders without causing re-renders.

**Q: What's the difference between useMemo and useCallback?**
A: useMemo memoizes computed values, useCallback memoizes functions.

**Q: What are custom hooks?**
A: JavaScript functions that use React hooks and can be reused across components.

**Q: Can you use hooks conditionally?**
A: No, hooks must be called at the top level, not inside conditions, loops, or nested functions.

### 15.3 Performance Questions

**Q: How do you optimize React performance?**
A: Use React.memo, useMemo, useCallback, code splitting, lazy loading, virtualization, and proper key usage.

**Q: What is React.memo?**
A: A higher-order component that memoizes component output and only re-renders if props change.

**Q: What is code splitting?**
A: Breaking bundle into smaller chunks loaded on demand to reduce initial load time.

**Q: What is lazy loading?**
A: Deferring loading of components until they're needed using React.lazy and Suspense.

**Q: What is virtualization?**
A: Rendering only visible items in large lists to improve performance.

**Q: What's the difference between debouncing and throttling?**
A: Debouncing delays execution until after wait time. Throttling limits execution to once per time period.

**Q: How does React Fiber improve performance?**
A: By enabling incremental rendering, prioritizing updates, and making rendering interruptible.

**Q: What causes unnecessary re-renders?**
A: State/props changes, parent re-renders, context changes, inline functions/objects, and improper key usage.

**Q: How do you profile React performance?**
A: Use React DevTools Profiler, Chrome DevTools Performance tab, and Profiler API.

### 15.4 Advanced Questions

**Q: What is reconciliation?**
A: The algorithm React uses to diff Virtual DOM trees and determine minimal changes needed for real DOM.

**Q: What is React Fiber?**
A: A reimplementation of React's core algorithm enabling incremental rendering and prioritization.

**Q: What are Higher-Order Components?**
A: Functions that take a component and return a new enhanced component for code reuse.

**Q: What are render props?**
A: A pattern where a component receives a function as a prop that returns a React element.

**Q: What are error boundaries?**
A: Components that catch JavaScript errors in child component tree and display fallback UI.

**Q: What are portals?**
A: A way to render children into a DOM node outside the parent component hierarchy.

**Q: What is Context API?**
A: A way to pass data through component tree without prop drilling.

**Q: What is Redux?**
A: A predictable state container implementing Flux architecture with single store, actions, and reducers.

**Q: What are Server Components?**
A: Components that render on server and send HTML to client with zero JavaScript bundle.

**Q: What is Suspense?**
A: A component that lets you display fallback content while waiting for something to load.

**Q: What is concurrent rendering?**
A: A rendering mechanism where React can work on multiple tasks simultaneously and prioritize updates.

**Q: What are transitions?**
A: A way to mark updates as non-urgent to keep UI responsive during heavy updates.

### 15.5 Coding Challenges

**Common React Coding Questions:**

1. **Build a Counter Component**

   - Increment/decrement buttons
   - Reset functionality
   - Step value customization

2. **Todo List Application**

   - Add/remove todos
   - Mark as complete
   - Filter (all/active/completed)
   - Local storage persistence

3. **Fetch and Display Data**

   - API call with useEffect
   - Loading state
   - Error handling
   - Display data in list

4. **Search/Filter Component**

   - Input field
   - Filter list in real-time
   - Debouncing
   - Highlight matches

5. **Form with Validation**

   - Multiple input fields
   - Validation rules
   - Error messages
   - Submit handling

6. **Custom Hook**

   - useLocalStorage
   - useDebounce
   - useFetch
   - useToggle

7. **Accordion Component**

   - Expand/collapse sections
   - Only one open at a time
   - Smooth animations

8. **Infinite Scroll**

   - Load more on scroll
   - Loading indicator
   - End of list detection

9. **Modal Component**

   - Open/close functionality
   - Click outside to close
   - Keyboard accessibility
   - Portal usage

10. **Tabs Component**
    - Multiple tab panels
    - Active state
    - Keyboard navigation
    - Accessible

**Tips for Coding Interviews:**

1. **Clarify Requirements:** Ask questions before coding
2. **Think Out Loud:** Explain your approach
3. **Start Simple:** Build basic version first
4. **Handle Edge Cases:** Consider errors, empty states
5. **Write Clean Code:** Proper naming, structure
6. **Test Your Code:** Walk through different scenarios
7. **Optimize:** Discuss performance improvements
8. **Accessibility:** Consider keyboard navigation, ARIA

---

## Additional Resources

### Official Documentation

- [React Docs](https://react.dev)
- [React Router Docs](https://reactrouter.com)
- [Redux Toolkit Docs](https://redux-toolkit.js.org)

### Learning Platforms

- FreeCodeCamp React Course
- Scrimba React Course
- React Official Tutorial
- Namaste React Series

### Practice Platforms

- LeetCode (React questions)
- Frontend Mentor
- CodeSandbox
- StackBlitz

### YouTube Channels

- Traversy Media
- Web Dev Simplified
- Codevolution
- Academind

### Books

- "Learning React" by Alex Banks & Eve Porcello
- "React Design Patterns and Best Practices"
- "Fullstack React"

---

**Happy Learning! 🚀**

_These notes cover core React concepts and common interview questions. Practice building projects to solidify your understanding._
