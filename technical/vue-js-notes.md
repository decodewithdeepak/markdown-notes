# Vue.js Master Notes By Deepak Modi

> Latest Version: Vue 3.5.24 (2024) | Recommended: Vue.js Official Docs

## Table of Contents

1. [Introduction to Vue.js](#1-introduction-to-vuejs)

   - [1.1 What is Vue.js?](#11-what-is-vuejs)
   - [1.2 Why Vue.js?](#12-why-vuejs)
   - [1.3 Vue 3 Features](#13-vue-3-features)
   - [1.4 Vue vs React vs Angular](#14-vue-vs-react-vs-angular)

2. [Installation and Setup](#2-installation-and-setup)

   - [2.1 Installation Methods](#21-installation-methods)
   - [2.2 Project Structure](#22-project-structure)
   - [2.3 Development Tools](#23-development-tools)
   - [2.4 Configuration](#24-configuration)
   - [2.5 First Vue Application](#25-first-vue-application)

3. [Core Concepts](#3-core-concepts)

   - [3.1 Reactivity System](#31-reactivity-system)
   - [3.2 Template Syntax](#32-template-syntax)
   - [3.3 Directives](#33-directives)
   - [3.4 Data Binding](#34-data-binding)
   - [3.5 Event Handling](#35-event-handling)
   - [3.6 Computed Properties](#36-computed-properties)
   - [3.7 Watchers](#37-watchers)

4. [Component System](#4-component-system)

   - [3.1 Component Basics](#31-component-basics)
   - [3.2 Props](#32-props)
   - [3.3 Events](#33-events)
   - [3.4 Slots](#34-slots)
   - [3.5 Component Communication](#35-component-communication)

5. [Composition API](#5-composition-api)

   - [4.1 Setup Function](#41-setup-function)
   - [4.2 Reactive State (ref vs reactive)](#42-reactive-state-ref-vs-reactive)
   - [4.3 Lifecycle Hooks](#43-lifecycle-hooks)
   - [4.4 Composables](#44-composables)
   - [4.5 Options API vs Composition API](#45-options-api-vs-composition-api)

6. [Vue Router](#6-vue-router)

   - [5.1 Routing Basics](#51-routing-basics)
   - [5.2 Dynamic Routes](#52-dynamic-routes)
   - [5.3 Navigation Guards](#53-navigation-guards)
   - [5.4 Nested Routes](#54-nested-routes)

7. [State Management (Pinia)](#7-state-management-pinia)

   - [6.1 Why State Management?](#61-why-state-management)
   - [6.2 Pinia vs Vuex](#62-pinia-vs-vuex)
   - [6.3 Stores](#63-stores)
   - [6.4 State, Getters, Actions](#64-state-getters-actions)

8. [Advanced Concepts](#8-advanced-concepts)

   - [7.1 Teleport](#71-teleport)
   - [7.2 Suspense](#72-suspense)
   - [7.3 Provide/Inject](#73-provideinject)
   - [7.4 Custom Directives](#74-custom-directives)
   - [7.5 Plugins](#75-plugins)

9. [Performance Optimization](#9-performance-optimization)

   - [8.1 Lazy Loading](#81-lazy-loading)
   - [8.2 Code Splitting](#82-code-splitting)
   - [8.3 Keep-Alive](#83-keep-alive)
   - [8.4 Virtual Scrolling](#84-virtual-scrolling)
   - [8.5 Production Optimization](#85-production-optimization)

10. [Testing](#10-testing)

- [9.1 Unit Testing](#91-unit-testing)
- [9.2 Component Testing](#92-component-testing)
- [9.3 E2E Testing](#93-e2e-testing)

11. [Interview Questions](#11-interview-questions)
    - [10.1 Fundamental Questions](#101-fundamental-questions)
    - [10.2 Advanced Questions](#102-advanced-questions)
    - [10.3 Practical Questions](#103-practical-questions)

---

## 1. Introduction to Vue.js

### 1.1 What is Vue.js?

Vue.js is a **progressive JavaScript framework** for building user interfaces. Unlike monolithic frameworks, Vue is designed to be incrementally adoptable. The core library focuses on the view layer only, making it easy to integrate with other libraries or existing projects.

#### Key Characteristics

- **Progressive Framework:** Start small, scale as needed
- **Declarative Rendering:** Describe what you want, not how to do it
- **Component-Based:** Build encapsulated, reusable components
- **Reactive:** Automatic UI updates when data changes
- **Versatile:** Library for simple pages, framework for complex SPAs

#### Philosophy

Vue's design philosophy emphasizes:

- **Approachability:** Easy to learn, gentle learning curve
- **Versatility:** Scales between library and full framework
- **Performance:** Fast virtual DOM, optimized updates
- **Maintainability:** Clear structure, good tooling

### 1.2 Why Vue.js?

#### Advantages

**1. Easy Learning Curve**

- Simple, intuitive API
- HTML-based template syntax
- Clear documentation
- Gradual complexity

**2. Flexibility**

- Can be used as a library or framework
- Works with any backend
- Multiple ways to structure code
- No strict conventions

**3. Great Performance**

- Small bundle size (~33KB)
- Fast virtual DOM
- Efficient reactivity system
- Optimized updates

**4. Rich Ecosystem**

- Vue Router for routing
- Pinia for state management
- Vue DevTools for debugging
- Large community plugins

**5. Developer Experience**

- Hot Module Replacement
- Single File Components
- Excellent tooling (Vite)
- Great IDE support

**6. Documentation**

- Comprehensive official docs
- Well-maintained guides
- Active community
- Many tutorials

#### Disadvantages

**1. Smaller Ecosystem**

- Fewer third-party libraries than React
- Less enterprise adoption
- Smaller job market

**2. Language Barrier**

- Some resources in Chinese
- Community split between languages

**3. Over-Flexibility**

- Multiple ways to do things
- Can lead to inconsistent codebases
- Requires discipline in large teams

**4. Less Corporate Backing**

- Community-driven (not backed by big tech)
- Slower adoption in enterprises

### 1.3 Vue 3 Features

#### Major Improvements

**1. Composition API**

- Better code organization
- Improved logic reuse
- Better TypeScript support
- More flexible than Options API
- Easier to extract and share logic

**2. Performance Enhancements**

- Faster mounting and patching
- Smaller bundle size
- Better memory usage
- Tree-shaking support
- Optimized reactivity system

**3. Better TypeScript Support**

- Complete TypeScript rewrite
- Better type inference
- Improved IDE support
- Type-safe props and emits

**4. New Built-in Components**

- **Teleport:** Render content elsewhere in DOM
- **Suspense:** Handle async components
- **Fragments:** Multiple root elements

**5. Improved Reactivity**

- Proxy-based reactivity (vs Object.defineProperty)
- Better performance
- Can detect property addition/deletion
- Works with arrays, Maps, Sets

**6. Script Setup**

- Less boilerplate code
- Better performance
- Cleaner syntax
- Auto-imported components

**7. Custom Renderer API**

- Create custom renderers
- Render to different targets (Canvas, WebGL, Native)

### 1.4 Vue vs React vs Angular

| Feature               | Vue.js                | React           | Angular            |
| --------------------- | --------------------- | --------------- | ------------------ |
| **Type**              | Progressive Framework | Library         | Full Framework     |
| **Learning Curve**    | Easy                  | Moderate        | Steep              |
| **Size**              | ~33KB                 | ~40KB           | ~100KB+            |
| **Performance**       | Fast                  | Fast            | Fast               |
| **Template**          | HTML-based            | JSX             | HTML-based         |
| **State Management**  | Pinia/Vuex            | Redux/Context   | RxJS/NgRx          |
| **Routing**           | Vue Router            | React Router    | Built-in           |
| **Two-Way Binding**   | Built-in (v-model)    | Manual          | Built-in           |
| **TypeScript**        | Optional              | Optional        | Required           |
| **Mobile**            | Ionic/NativeScript    | React Native    | Ionic/NativeScript |
| **Corporate Backing** | Community             | Meta (Facebook) | Google             |
| **Job Market**        | Growing               | Large           | Large              |
| **Flexibility**       | High                  | Very High       | Moderate           |
| **Opinionated**       | Moderate              | Low             | High               |

---

## 2. Installation and Setup

### 2.1 Installation Methods

#### Method 1: Using Vite (Recommended)

Vite is the recommended build tool for Vue 3 projects. It provides fast development server and optimized builds.

```bash
# Create new Vue project
npm create vue@latest

# Follow interactive prompts:
# - Project name
# - TypeScript? (Yes/No)
# - JSX Support? (Yes/No)
# - Vue Router? (Yes/No)
# - Pinia? (Yes/No)
# - Vitest? (Yes/No)
# - ESLint? (Yes/No)
# - Prettier? (Yes/No)

cd project-name
npm install
npm run dev
```

**Why Vite?**

- Lightning-fast HMR (Hot Module Replacement)
- Optimized production builds
- Native ES modules
- Better developer experience
- Official Vue recommendation

#### Method 2: Using CDN (Quick Start)

For learning or simple projects, use CDN to include Vue directly in HTML.

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
  </head>
  <body>
    <div id="app">{{ message }}</div>

    <script>
      const { createApp } = Vue;

      createApp({
        data() {
          return {
            message: "Hello Vue!",
          };
        },
      }).mount("#app");
    </script>
  </body>
</html>
```

**When to use CDN:**

- Learning Vue basics
- Simple prototypes
- Adding Vue to existing pages
- No build step needed

#### Method 3: Using Vue CLI (Legacy)

Vue CLI is the older tool, now in maintenance mode. Use Vite for new projects.

```bash
npm install -g @vue/cli
vue create my-project
cd my-project
npm run serve
```

### 2.2 Project Structure

Standard Vue project structure created by Vite:

```
my-vue-app/
├── public/              # Static assets
│   └── favicon.ico
├── src/
│   ├── assets/          # Images, styles, fonts
│   ├── components/      # Vue components
│   ├── composables/     # Reusable composition functions
│   ├── router/          # Vue Router configuration
│   │   └── index.js
│   ├── stores/          # Pinia stores
│   │   └── counter.js
│   ├── views/           # Page components
│   │   ├── HomeView.vue
│   │   └── AboutView.vue
│   ├── App.vue          # Root component
│   └── main.js          # Application entry point
├── index.html           # HTML entry point
├── package.json         # Dependencies and scripts
├── vite.config.js       # Vite configuration
└── README.md
```

**Key Directories:**

- **components/**: Reusable UI components
- **views/**: Page-level components (used with router)
- **composables/**: Shared composition functions
- **stores/**: State management with Pinia
- **assets/**: Static files processed by build tool

### 2.3 Development Tools

#### VS Code Extensions

**Essential:**

1. **Volar** (Vue Language Features)

   - Syntax highlighting
   - IntelliSense
   - Type checking
   - Error detection
   - Replaces Vetur for Vue 3

2. **TypeScript Vue Plugin (Volar)**
   - Better TypeScript support
   - Type checking in templates

**Recommended:** 3. **Vue VSCode Snippets**

- Code snippets for faster development
- Common patterns

4. **ESLint**

   - Code linting
   - Style enforcement
   - Error prevention

5. **Prettier**
   - Code formatting
   - Consistent style

#### Browser Extensions

**Vue DevTools**

- Inspect component hierarchy
- View component data and props
- Debug Vuex/Pinia stores
- Track events
- Performance profiling
- Time-travel debugging

Available for:

- Chrome
- Firefox
- Edge

### 2.4 Configuration

#### Vite Configuration

```javascript
// vite.config.js
import { defineConfig } from "vite";
import vue from "@vitejs/plugin-vue";
import { fileURLToPath, URL } from "node:url";

export default defineConfig({
  plugins: [vue()],
  resolve: {
    alias: {
      "@": fileURLToPath(new URL("./src", import.meta.url)),
    },
  },
  server: {
    port: 3000,
    open: true,
  },
  build: {
    sourcemap: true,
    rollupOptions: {
      output: {
        manualChunks: {
          vendor: ["vue", "vue-router", "pinia"],
        },
      },
    },
  },
});
```

#### ESLint Configuration

```javascript
// .eslintrc.cjs
module.exports = {
  extends: [
    "plugin:vue/vue3-recommended",
    "eslint:recommended",
    "@vue/eslint-config-prettier",
  ],
  rules: {
    "vue/multi-word-component-names": "off",
  },
};
```

#### Package.json Scripts

```json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "lint": "eslint . --ext .vue,.js,.jsx,.cjs,.mjs --fix",
    "format": "prettier --write src/"
  }
}
```

### 2.5 First Vue Application

#### main.js (Entry Point)

```javascript
import { createApp } from "vue";
import { createPinia } from "pinia";
import App from "./App.vue";
import router from "./router";
import "./assets/main.css";

const app = createApp(App);

app.use(createPinia());
app.use(router);

app.mount("#app");
```

#### App.vue (Root Component)

```vue
<template>
  <div id="app">
    <header>
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </header>
    <main>
      <RouterView />
    </main>
  </div>
</template>

<style scoped>
header {
  padding: 1rem;
  background: #42b883;
}
</style>
```

---

## 3. Core Concepts

### 3.1 Reactivity System

Vue's reactivity system is the core of its functionality. It automatically tracks dependencies and updates the DOM when data changes.

#### How Reactivity Works

**Vue 3 Reactivity (Proxy-based)**

- Uses JavaScript Proxy API
- Intercepts property access and modification
- Tracks which components depend on which data
- Automatically updates dependent components

**Key Concepts:**

1. **Reactive Data:** Data that triggers updates when changed
2. **Dependencies:** Components/computed properties that use reactive data
3. **Effects:** Functions that re-run when dependencies change
4. **Tracking:** System records which data is accessed
5. **Triggering:** System notifies dependents when data changes

#### ref vs reactive

**ref:**

- For primitive values (strings, numbers, booleans)
- Requires `.value` to access/modify
- Can hold any value type
- Creates a reactive reference

**reactive:**

- For objects and arrays
- No `.value` needed
- Only works with objects
- Creates a reactive proxy

**When to use what:**

- Use `ref` for primitives and single values
- Use `reactive` for objects with multiple properties
- Use `ref` when you need to reassign entire object
- Use `reactive` for complex nested structures

### 3.2 Template Syntax

Vue uses HTML-based template syntax that allows declaratively binding the rendered DOM to the underlying component data.

#### Text Interpolation

Uses "Mustache" syntax (double curly braces) to display data. Expressions inside are evaluated as JavaScript.

#### Raw HTML

The `v-html` directive renders raw HTML. **Warning:** Never use on user-provided content (XSS vulnerability).

#### Attribute Binding

The `v-bind` directive (or `:` shorthand) dynamically binds attributes to expressions.

#### JavaScript Expressions

Templates support full JavaScript expressions, but only single expressions (no statements or control flow).

### 3.3 Directives

Directives are special attributes with the `v-` prefix that apply reactive behavior to the DOM.

#### Common Directives

**v-if / v-else-if / v-else**

- Conditionally render elements
- Elements are added/removed from DOM
- Higher toggle cost
- Use for infrequent changes

**v-show**

- Toggle visibility with CSS display
- Element always in DOM
- Higher initial render cost
- Use for frequent toggles

**v-for**

- Render lists of items
- Requires `:key` for tracking
- Can iterate arrays, objects, ranges
- Supports destructuring

**v-on (@)**

- Attach event listeners
- Supports modifiers (.prevent, .stop, .once)
- Can pass arguments
- Access event object with $event

**v-bind (:)**

- Dynamically bind attributes
- Can bind multiple attributes
- Supports shorthand syntax
- Works with class and style

**v-model**

- Two-way data binding
- Works with form inputs
- Supports modifiers (.lazy, .number, .trim)
- Syntactic sugar for :value and @input

### 3.4 Data Binding

#### One-Way Binding

Data flows from component to template. Changes in component update the view, but not vice versa.

#### Two-Way Binding

Data flows both ways. Changes in component update view, and changes in view update component. Achieved with `v-model`.

#### Class Binding

Dynamically toggle CSS classes based on data. Supports object syntax, array syntax, and computed classes.

#### Style Binding

Dynamically apply inline styles. Supports object syntax, array syntax, and auto-prefixing.

### 3.5 Event Handling

Vue provides `v-on` directive (or `@` shorthand) to listen to DOM events.

#### Event Modifiers

- `.stop` - Stop event propagation
- `.prevent` - Prevent default behavior
- `.capture` - Use capture mode
- `.self` - Only trigger if event.target is element itself
- `.once` - Trigger only once
- `.passive` - Improve scroll performance

#### Key Modifiers

- `.enter`, `.tab`, `.delete`, `.esc`, `.space`
- `.up`, `.down`, `.left`, `.right`
- `.ctrl`, `.alt`, `.shift`, `.meta`

#### Mouse Modifiers

- `.left`, `.right`, `.middle`

### 3.6 Computed Properties

Computed properties are cached based on their reactive dependencies. They only re-evaluate when dependencies change.

#### Benefits

- **Caching:** Only recalculates when needed
- **Declarative:** Describe what, not how
- **Readable:** Clear data transformations
- **Efficient:** Better than methods for expensive operations

#### Computed vs Methods

- Computed properties are cached, methods are not
- Computed properties are reactive, methods are not
- Use computed for derived state
- Use methods for actions/events

#### Writable Computed

Computed properties can have both getter and setter, enabling two-way computed properties.

### 3.7 Watchers

Watchers observe reactive data and perform side effects when data changes.

#### Use Cases

- Async operations in response to data changes
- Expensive operations that shouldn't run on every change
- Performing actions when data changes
- Debouncing/throttling

#### Watch Options

- **immediate:** Run immediately on creation
- **deep:** Watch nested properties in objects
- **flush:** Control when callback runs (pre, post, sync)

#### When to Use

- Use computed for synchronous derived state
- Use watchers for async operations or side effects
- Use watchers when you need to perform actions in response to changes

---

## 3. Component System

### 3.1 Component Basics

Components are reusable Vue instances with a name. They accept the same options as the root Vue instance.

#### Single File Components (SFC)

Vue's SFC format combines template, script, and style in one `.vue` file.

**Benefits:**

- Encapsulation
- Syntax highlighting
- Scoped CSS
- Better organization
- Easier to maintain

#### Component Naming

- **PascalCase:** For registration (MyComponent)
- **kebab-case:** For templates (<my-component>)
- Multi-word names recommended (avoid conflicts with HTML elements)

### 3.2 Props

Props are custom attributes for passing data from parent to child components.

#### Prop Types

Vue supports type checking for props:

- String, Number, Boolean, Array, Object, Date, Function, Symbol

#### Prop Validation

- **type:** Expected type(s)
- **required:** Whether prop is required
- **default:** Default value
- **validator:** Custom validation function

#### Prop Casing

- Use camelCase in JavaScript
- Use kebab-case in templates
- Vue automatically converts between them

#### One-Way Data Flow

Props follow one-way data flow (parent to child). Child should never mutate props directly.

### 3.3 Events

Components can emit custom events to communicate with parent components.

#### Emitting Events

Child components use `$emit` to send events to parent. Parent listens with `v-on` or `@`.

#### Event Validation

Vue 3 allows declaring and validating emitted events, improving component documentation and type safety.

#### Event Naming

- Use kebab-case for event names
- Be descriptive about what happened
- Follow naming conventions (update:modelValue for v-model)

### 3.4 Slots

Slots allow parent components to pass content into child component templates.

#### Default Slots

Basic slot for passing content. Can have fallback content if nothing is provided.

#### Named Slots

Multiple slots with different names for more complex content distribution.

#### Scoped Slots

Slots that receive data from child component, allowing parent to customize rendering based on child's data.

#### Slot Props

Data passed from child to parent through slot, enabling flexible content rendering.

### 3.5 Component Communication

#### Parent to Child

- **Props:** Pass data down
- **Refs:** Direct access to child instance

#### Child to Parent

- **Events:** Emit custom events
- **v-model:** Two-way binding
- **Callbacks:** Pass functions as props

#### Sibling Components

- **Parent as intermediary:** Lift state up
- **Event bus:** (Not recommended in Vue 3)
- **State management:** Pinia/Vuex

#### Any to Any

- **Provide/Inject:** Dependency injection
- **State management:** Global state with Pinia
- **Composables:** Shared reactive state

---

## 4. Composition API

### 4.1 Setup Function

The `setup` function is the entry point for Composition API. It runs before component is created.

#### Characteristics

- Runs once during component initialization
- Has access to props and context
- Returns data/methods to template
- No access to `this`
- Runs before created hook

#### Script Setup

`<script setup>` is syntactic sugar for `setup()` function. It's more concise and performant.

**Benefits:**

- Less boilerplate
- Better performance
- Auto-imported components
- Cleaner syntax
- Better TypeScript inference

### 4.2 Reactive State (ref vs reactive)

#### ref

Creates a reactive reference to a value. Requires `.value` to access/modify.

**Use cases:**

- Primitive values
- Single values that might be reassigned
- When you need to pass reactive value to composables

#### reactive

Creates a reactive proxy of an object. No `.value` needed.

**Use cases:**

- Objects with multiple properties
- Complex nested structures
- When you won't reassign entire object

#### toRef and toRefs

- **toRef:** Create ref from reactive object property
- **toRefs:** Convert all properties of reactive object to refs
- Useful for destructuring while maintaining reactivity

#### readonly

Creates a readonly proxy. Prevents modifications while maintaining reactivity.

### 4.3 Lifecycle Hooks

Composition API provides lifecycle hooks as functions.

#### Available Hooks

- **onBeforeMount:** Before component is mounted
- **onMounted:** After component is mounted (DOM available)
- **onBeforeUpdate:** Before component updates
- **onUpdated:** After component updates
- **onBeforeUnmount:** Before component is unmounted
- **onUnmounted:** After component is unmounted
- **onErrorCaptured:** When error is captured from descendant
- **onActivated:** When kept-alive component is activated
- **onDeactivated:** When kept-alive component is deactivated

#### Lifecycle Flow

1. Setup runs
2. onBeforeMount
3. Component mounted to DOM
4. onMounted
5. Data changes → onBeforeUpdate → onUpdated
6. onBeforeUnmount
7. Component unmounted
8. onUnmounted

### 4.4 Composables

Composables are reusable functions that leverage Composition API to encapsulate stateful logic.

#### Benefits

- **Reusability:** Share logic across components
- **Organization:** Group related code
- **Testability:** Easier to test isolated logic
- **Type Safety:** Better TypeScript support

#### Naming Convention

Use `use` prefix (e.g., `useCounter`, `useFetch`, `useAuth`)

#### Best Practices

- Return reactive state and functions
- Keep composables focused and single-purpose
- Document inputs and outputs
- Handle cleanup in onUnmounted
- Make composables pure when possible

### 4.5 Options API vs Composition API

#### Options API

**Pros:**

- Easier for beginners
- Clear structure
- Familiar to Vue 2 users
- Good for simple components

**Cons:**

- Logic scattered across options
- Harder to reuse logic
- Less TypeScript support
- Difficult to organize complex logic

#### Composition API

**Pros:**

- Better code organization
- Easier logic reuse
- Better TypeScript support
- More flexible
- Better for complex components

**Cons:**

- Steeper learning curve
- More boilerplate (without script setup)
- Requires understanding of reactivity

#### When to Use What

- **Options API:** Simple components, beginners, Vue 2 migration
- **Composition API:** Complex logic, reusable logic, TypeScript, large applications

---

## 5. Vue Router

### 5.1 Routing Basics

Vue Router is the official routing library for Vue.js. It enables navigation between different views in a Single Page Application.

#### Core Concepts

- **Routes:** Map URLs to components
- **Router:** Manages navigation and history
- **Router View:** Displays matched component
- **Router Link:** Navigation component

#### History Modes

**HTML5 History Mode:**

- Clean URLs (no hash)
- Requires server configuration
- Better for SEO

**Hash Mode:**

- URLs with # (e.g., /#/about)
- Works without server configuration
- Fallback for older browsers

### 5.2 Dynamic Routes

Routes with dynamic segments that match patterns.

#### Route Parameters

Capture parts of URL as parameters. Accessible via `$route.params`.

#### Parameter Matching

- Required parameters: `/user/:id`
- Optional parameters: `/user/:id?`
- Catch-all: `/path/:pathMatch(.*)*`
- Regex: `/user/:id(\\d+)` (only numbers)

#### Reacting to Parameter Changes

When navigating between routes with same component, component is reused. Use watchers or navigation guards to react to parameter changes.

### 5.3 Navigation Guards

Functions that control navigation flow. Used for authentication, authorization, data fetching, etc.

#### Global Guards

- **beforeEach:** Runs before every navigation
- **beforeResolve:** Runs after all in-component guards
- **afterEach:** Runs after navigation is confirmed

#### Per-Route Guards

- **beforeEnter:** Runs before entering specific route

#### In-Component Guards

- **beforeRouteEnter:** Before component is created
- **beforeRouteUpdate:** When route changes but component is reused
- **beforeRouteLeave:** Before leaving current route

#### Guard Parameters

- **to:** Target route
- **from:** Current route
- **next:** Function to resolve navigation (Vue Router 3)

In Vue Router 4, return values control navigation instead of `next()`.

### 5.4 Nested Routes

Routes can have child routes, creating nested view hierarchies.

#### Use Cases

- Layouts with multiple sections
- Dashboards with sidebar navigation
- Multi-step forms
- Tabbed interfaces

#### Router View

Nested routes require `<router-view>` in parent component to render child routes.

---

## 6. State Management (Pinia)

### 6.1 Why State Management?

As applications grow, managing state across components becomes complex.

#### Problems Without State Management

- Prop drilling (passing props through many levels)
- Scattered state across components
- Difficult to track state changes
- Hard to debug
- Inconsistent state

#### Benefits of State Management

- Centralized state
- Predictable state changes
- Easier debugging
- Time-travel debugging
- Better organization

### 6.2 Pinia vs Vuex

Pinia is the official state management library for Vue 3, replacing Vuex.

#### Pinia Advantages

- Simpler API (no mutations)
- Better TypeScript support
- Modular by design
- Smaller bundle size
- DevTools support
- Composition API friendly

#### Key Differences

| Feature        | Pinia        | Vuex       |
| -------------- | ------------ | ---------- |
| Mutations      | No           | Yes        |
| Actions        | Sync & Async | Async only |
| Modules        | Built-in     | Manual     |
| TypeScript     | Excellent    | Good       |
| DevTools       | Yes          | Yes        |
| Learning Curve | Easy         | Moderate   |

### 6.3 Stores

Stores hold application state and logic. Each store is a reactive object.

#### Store Types

**Options Stores:**

- Similar to Options API
- Define state, getters, actions separately
- Familiar structure

**Setup Stores:**

- Similar to Composition API
- More flexible
- Better for complex logic

### 6.4 State, Getters, Actions

#### State

The data stored in the store. Should be a function returning an object.

**Characteristics:**

- Reactive
- Accessed directly from store
- Can be modified directly (unlike Vuex)

#### Getters

Computed properties of the store. Cached based on dependencies.

**Use cases:**

- Derived state
- Filtering/sorting
- Computed values
- Reusable logic

#### Actions

Methods that can modify state. Can be synchronous or asynchronous.

**Use cases:**

- API calls
- Complex state updates
- Business logic
- Side effects

---

## 7. Advanced Concepts

### 7.1 Teleport

Teleport allows rendering content in a different part of the DOM tree while maintaining component hierarchy.

#### Use Cases

- Modals
- Tooltips
- Notifications
- Full-screen overlays
- Dropdowns

#### Benefits

- Proper component structure
- Avoid z-index issues
- Better accessibility
- Cleaner DOM structure

### 7.2 Suspense

Suspense handles async dependencies in component tree, showing fallback content while waiting.

#### Use Cases

- Async components
- Async setup
- Data fetching
- Code splitting
- Loading states

#### Benefits

- Declarative loading states
- Cleaner async code
- Better UX
- Nested async handling

**Note:** Still experimental in Vue 3

### 7.3 Provide/Inject

Dependency injection system for passing data through component tree without props.

#### Use Cases

- Theme configuration
- User authentication
- Plugin data
- Shared utilities
- Avoiding prop drilling

#### Benefits

- Avoid prop drilling
- Cleaner component interfaces
- Flexible data sharing
- Good for plugins

#### Considerations

- Makes dependencies less explicit
- Harder to track data flow
- Should be documented
- Use sparingly

### 7.4 Custom Directives

Create reusable DOM manipulation logic as directives.

#### Directive Hooks

- **created:** Before element attributes applied
- **beforeMount:** Before element inserted into DOM
- **mounted:** After element inserted
- **beforeUpdate:** Before element updates
- **updated:** After element updates
- **beforeUnmount:** Before element removed
- **unmounted:** After element removed

#### Use Cases

- DOM manipulation
- Third-party library integration
- Focus management
- Click outside detection
- Tooltips

### 7.5 Plugins

Plugins add global-level functionality to Vue applications.

#### Plugin Capabilities

- Add global properties
- Add global components
- Add directives
- Provide/inject
- Add app config options

#### Use Cases

- Third-party libraries
- Utility functions
- Global components
- App-wide features

---

## 8. Performance Optimization

### 8.1 Lazy Loading

Load components only when needed, reducing initial bundle size.

#### Benefits

- Faster initial load
- Smaller bundle size
- Better performance
- On-demand loading

#### When to Use

- Route components
- Heavy components
- Rarely used components
- Modal/dialog components

### 8.2 Code Splitting

Automatically split code into smaller chunks loaded on demand.

#### Benefits

- Smaller initial bundle
- Parallel loading
- Better caching
- Faster page loads

#### Strategies

- Route-based splitting
- Component-based splitting
- Vendor splitting
- Dynamic imports

### 8.3 Keep-Alive

Cache component instances to avoid re-rendering.

#### Use Cases

- Tabs that shouldn't reset
- Forms with unsaved data
- Expensive components
- List with scroll position

#### Options

- **include:** Which components to cache
- **exclude:** Which components not to cache
- **max:** Maximum cached instances

#### Lifecycle Hooks

- **onActivated:** When cached component is activated
- **onDeactivated:** When cached component is deactivated

### 8.4 Virtual Scrolling

Render only visible items in large lists.

#### Benefits

- Handle thousands of items
- Smooth scrolling
- Low memory usage
- Better performance

#### When to Use

- Large lists (1000+ items)
- Infinite scroll
- Data tables
- Chat messages

### 8.5 Production Optimization

#### Best Practices

**1. Production Build**

- Minification
- Tree-shaking
- Dead code elimination
- Source maps (optional)

**2. Component Optimization**

- Use v-once for static content
- Use v-memo for conditional caching
- Avoid unnecessary re-renders
- Use computed properties

**3. Bundle Optimization**

- Code splitting
- Lazy loading
- Vendor chunking
- Asset optimization

**4. Runtime Optimization**

- Use production mode
- Disable DevTools
- Use functional components when possible
- Optimize watchers

---

## 9. Testing

### 9.1 Unit Testing

Test individual functions and composables in isolation.

#### Tools

- **Vitest:** Fast unit test framework
- **Jest:** Popular testing framework
- **Vue Test Utils:** Official testing library

#### What to Test

- Composables
- Utility functions
- Business logic
- Computed properties
- Watchers

### 9.2 Component Testing

Test component behavior and rendering.

#### What to Test

- Component rendering
- Props
- Events
- User interactions
- Conditional rendering
- Slots

#### Best Practices

- Test user behavior, not implementation
- Use data-testid for selectors
- Test accessibility
- Mock external dependencies
- Keep tests simple and focused

### 9.3 E2E Testing

Test complete user flows in a real browser.

#### Tools

- **Playwright:** Modern E2E testing
- **Cypress:** Popular E2E framework
- **Nightwatch:** Vue-specific E2E

#### What to Test

- Critical user paths
- Authentication flows
- Form submissions
- Navigation
- Integration with backend

---

## 10. Interview Questions

### 10.1 Fundamental Questions

**Q: What is Vue.js?**
A: Vue.js is a progressive JavaScript framework for building user interfaces. It focuses on the view layer and can be incrementally adopted, scaling from a library to a full-featured framework.

**Q: What is the Virtual DOM?**
A: A lightweight JavaScript representation of the actual DOM. Vue uses it to efficiently update the real DOM by comparing changes (diffing) and only updating what's necessary, improving performance.

**Q: What is Vue's reactivity system?**
A: A system that automatically tracks dependencies and updates the DOM when data changes. Vue 3 uses JavaScript Proxy to intercept property access and modifications, enabling automatic reactivity.

**Q: What is the difference between v-if and v-show?**
A: `v-if` conditionally renders elements (adds/removes from DOM) with higher toggle cost. `v-show` toggles CSS display property with higher initial render cost. Use `v-if` for infrequent changes, `v-show` for frequent toggles.

**Q: What are directives in Vue?**
A: Special attributes with the `v-` prefix that apply reactive behavior to the DOM. Examples: `v-if`, `v-for`, `v-bind`, `v-on`, `v-model`.

**Q: What is v-model?**
A: A directive that creates two-way data binding on form inputs. It's syntactic sugar for `:value` and `@input`, automatically syncing input values with component data.

**Q: What are props?**
A: Custom attributes for passing data from parent to child components. They follow one-way data flow and should not be mutated in child components.

**Q: What is the difference between computed and methods?**
A: Computed properties are cached based on dependencies and only re-evaluate when dependencies change. Methods run every time they're called. Use computed for derived state, methods for actions.

**Q: What are watchers?**
A: Functions that observe reactive data and perform side effects when data changes. Useful for async operations, expensive operations, or actions in response to data changes.

**Q: What is a Single File Component (SFC)?**
A: A `.vue` file that combines template, script, and style in one file. It provides better organization, scoped CSS, syntax highlighting, and encapsulation.

### 10.2 Advanced Questions

**Q: Explain Vue 3's reactivity system in detail.**
A: Vue 3 uses Proxy-based reactivity. When you create reactive data, Vue wraps it in a Proxy that intercepts property access (get) and modifications (set). During rendering, Vue tracks which properties are accessed (dependency tracking). When properties change, Vue notifies all dependent components to re-render (trigger updates). This is more efficient than Vue 2's Object.defineProperty approach.

**Q: What is the difference between ref and reactive?**
A: `ref` is for primitive values and requires `.value` to access/modify. It can hold any value type and creates a reactive reference. `reactive` is for objects, doesn't need `.value`, and only works with objects. Use `ref` for primitives and when you need to reassign entire objects. Use `reactive` for complex nested structures.

**Q: What is the Composition API and why was it introduced?**
A: The Composition API is a set of APIs for organizing component logic by logical concerns rather than options. It was introduced to solve issues with Options API: better code organization, improved logic reuse, better TypeScript support, and more flexibility for complex components.

**Q: What are lifecycle hooks in Composition API?**
A: Functions that run at specific stages of component lifecycle: `onBeforeMount`, `onMounted`, `onBeforeUpdate`, `onUpdated`, `onBeforeUnmount`, `onUnmounted`, `onErrorCaptured`, `onActivated`, `onDeactivated`. They replace Options API lifecycle hooks.

**Q: What are composables?**
A: Reusable functions that leverage Composition API to encapsulate stateful logic. They follow the `use*` naming convention and return reactive state and functions. They enable better code reuse and organization.

**Q: What is Teleport and when would you use it?**
A: A built-in component that renders content in a different part of the DOM tree while maintaining component hierarchy. Used for modals, tooltips, notifications, and overlays to avoid z-index issues and maintain proper DOM structure.

**Q: What is Suspense?**
A: A component for handling async dependencies, showing fallback content while waiting for async components to load. It enables declarative loading states and cleaner async code. Still experimental in Vue 3.

**Q: What is Provide/Inject?**
A: A dependency injection system for passing data through component tree without props. Useful for theme configuration, authentication, and avoiding prop drilling. Makes dependencies less explicit, so should be used sparingly.

**Q: How does Vue Router work?**
A: Vue Router maps URLs to components, enabling SPA navigation. It uses HTML5 History API or hash mode for routing without page reloads. It provides navigation guards for controlling access and data fetching.

**Q: What are navigation guards?**
A: Functions that control navigation flow in Vue Router. Types include global guards (`beforeEach`, `afterEach`), per-route guards (`beforeEnter`), and in-component guards (`beforeRouteEnter`, `beforeRouteUpdate`, `beforeRouteLeave`). Used for authentication, authorization, and data fetching.

**Q: What is Pinia and how is it different from Vuex?**
A: Pinia is the official state management library for Vue 3. It's simpler than Vuex (no mutations), has better TypeScript support, is modular by design, and is Composition API friendly. It's the recommended state management solution for Vue 3.

**Q: How do you optimize Vue application performance?**
A: Use lazy loading, code splitting, keep-alive for caching components, virtual scrolling for large lists, computed properties instead of methods, v-once for static content, production builds with minification, and avoid unnecessary re-renders.

**Q: What is the difference between Options API and Composition API?**
A: Options API organizes code by options (data, methods, computed) and is easier for beginners but scatters related logic. Composition API organizes by logical concerns, offers better code organization, logic reuse, and TypeScript support, but has a steeper learning curve.

**Q: How does Vue's Virtual DOM work?**
A: Vue creates a JavaScript representation of the DOM. When data changes, Vue creates a new virtual DOM tree, compares it with the old one (diffing), calculates minimal changes needed, and efficiently updates only changed parts of the real DOM.

**Q: What are slots and when would you use them?**
A: Slots allow parent components to pass content into child component templates. Types include default slots, named slots, and scoped slots. Used for flexible, reusable components that need customizable content.

### 10.3 Practical Questions

**Q: How do you pass data from child to parent component?**
A: Using custom events with `$emit`. Child emits an event with data, parent listens with `@event-name` and handles it. Can also use v-model for two-way binding or callbacks passed as props.

**Q: How do you share data between sibling components?**
A: Options include: using parent component as intermediary (lift state up), provide/inject for dependency injection, or state management (Pinia) for global state. Event bus is not recommended in Vue 3.

**Q: How do you handle forms in Vue?**
A: Use `v-model` for two-way binding with form inputs. Handle submit events with `@submit.prevent`. Validate data before submission. Manage form state (loading, errors, success). Use computed properties for validation.

**Q: How do you make API calls in Vue?**
A: Use `fetch` or `axios` in lifecycle hooks (onMounted) or composables. Handle loading states, errors, and update reactive data. Consider using composables like `useFetch` for reusable API logic.

**Q: How do you implement authentication in Vue?**
A: Store auth token in localStorage/cookies. Create auth store with Pinia for user state. Use route guards to protect routes. Implement login/logout actions. Add token to API requests. Handle token refresh.

**Q: How do you handle errors in Vue?**
A: Use try-catch blocks for async operations. Use `onErrorCaptured` hook for component errors. Set global error handler with `app.config.errorHandler`. Display user-friendly error messages. Log errors for debugging.

**Q: How do you implement lazy loading in Vue?**
A: Use dynamic imports with `defineAsyncComponent` for components or in router with `() => import('./Component.vue')`. This creates separate chunks loaded on demand, reducing initial bundle size.

**Q: How do you create a custom directive?**
A: Define an object with lifecycle hooks (mounted, updated, unmounted) and register it globally with `app.directive()` or locally in component. Use for DOM manipulation, focus management, or third-party library integration.

**Q: How do you test Vue components?**
A: Use Vue Test Utils with Vitest or Jest. Test component rendering, props, events, user interactions, and conditional rendering. Mock external dependencies. Focus on testing user behavior, not implementation details.

**Q: How do you optimize large lists in Vue?**
A: Use virtual scrolling libraries like `vue-virtual-scroller` to render only visible items. Implement pagination or infinite scroll. Use `v-show` instead of `v-if` when appropriate. Add `:key` for efficient updates.

**Q: How do you implement internationalization (i18n)?**
A: Use `vue-i18n` library. Define translations for each language. Create composable for accessing translations. Switch locale based on user preference. Handle pluralization and date/number formatting.

**Q: How do you handle route transitions?**
A: Use Vue's `<transition>` component with `<router-view>`. Define CSS transitions or animations. Use transition modes (in-out, out-in). Handle async components with Suspense.

**Q: How do you implement dark mode in Vue?**
A: Store theme preference in localStorage. Use provide/inject or Pinia for theme state. Apply CSS classes or CSS variables based on theme. Toggle theme with button. Respect system preference with `prefers-color-scheme`.

**Q: How do you prevent memory leaks in Vue?**
A: Clean up event listeners in `onUnmounted`. Clear timers and intervals. Unsubscribe from observables. Remove global event listeners. Cancel pending API requests. Avoid circular references.

**Q: How do you implement infinite scroll?**
A: Use Intersection Observer API to detect when user reaches bottom. Load more data when triggered. Update list with new items. Handle loading and error states. Consider virtual scrolling for very large lists.

---

## Additional Resources

### Official Documentation

- [Vue.js Official Docs](https://vuejs.org)
- [Vue Router Docs](https://router.vuejs.org)
- [Pinia Docs](https://pinia.vuejs.org)
- [Vue Test Utils](https://test-utils.vuejs.org)

### Tools

- **Volar** - VS Code extension for Vue 3
- **Vue DevTools** - Browser extension for debugging
- **Vite** - Fast build tool
- **Vitest** - Fast unit testing

### Learning Resources

- Vue Mastery
- Vue School
- Official Vue YouTube Channel
- VueUse - Collection of Vue Composables

### Popular Libraries

- **VueUse** - Collection of essential Vue Composition Utilities
- **Headless UI** - Unstyled, accessible components
- **Naive UI** - Vue 3 Component Library
- **Element Plus** - Vue 3 UI Library

---

**Happy Coding with Vue.js! 🚀**

_These notes cover Vue.js 3.5 concepts, features, and interview questions. Practice building projects to master Vue development._
