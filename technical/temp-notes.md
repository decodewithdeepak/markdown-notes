# Vue.js & Nuxt.js Master Notes By Deepak Modi

> Latest Versions: Vue 3.5.24 | Nuxt 4.2.1 (2024) | Recommended: Vue.js & Nuxt Official Docs

---

# Part 1: Vue.js

## Table of Contents - Vue.js

1. [Introduction to Vue.js](#1-introduction-to-vuejs)

   - [1.1 What is Vue.js?](#11-what-is-vuejs)
   - [1.2 Why Vue.js?](#12-why-vuejs)
   - [1.3 Vue 3 New Features](#13-vue-3-new-features)
   - [1.4 Vue vs React vs Angular](#14-vue-vs-react-vs-angular)

2. [Installation and Setup](#2-installation-and-setup)

   - [2.1 Installation Methods](#21-installation-methods)
   - [2.2 Project Structure](#22-project-structure)
   - [2.3 Development Tools](#23-development-tools)

3. [Vue Fundamentals](#3-vue-fundamentals)

   - [3.1 Template Syntax](#31-template-syntax)
   - [3.2 Data Binding](#32-data-binding)
   - [3.3 Directives](#33-directives)
   - [3.4 Event Handling](#34-event-handling)
   - [3.5 Computed Properties](#35-computed-properties)
   - [3.6 Watchers](#36-watchers)

4. [Components](#4-components)

   - [4.1 Component Basics](#41-component-basics)
   - [4.2 Props](#42-props)
   - [4.3 Events](#43-events)
   - [4.4 Slots](#44-slots)
   - [4.5 Component Registration](#45-component-registration)

5. [Composition API](#5-composition-api)

   - [5.1 Setup Function](#51-setup-function)
   - [5.2 Reactive State](#52-reactive-state)
   - [5.3 Computed and Watch](#53-computed-and-watch)
   - [5.4 Lifecycle Hooks](#54-lifecycle-hooks)
   - [5.5 Composables](#55-composables)

6. [Vue Router](#6-vue-router)

   - [6.1 Router Setup](#61-router-setup)
   - [6.2 Navigation](#62-navigation)
   - [6.3 Dynamic Routes](#63-dynamic-routes)
   - [6.4 Route Guards](#64-route-guards)
   - [6.5 Nested Routes](#65-nested-routes)

7. [State Management (Pinia)](#7-state-management-pinia)

   - [7.1 Pinia Setup](#71-pinia-setup)
   - [7.2 Stores](#72-stores)
   - [7.3 State, Getters, Actions](#73-state-getters-actions)
   - [7.4 Store Composition](#74-store-composition)

8. [Advanced Features](#8-advanced-features)

   - [8.1 Teleport](#81-teleport)
   - [8.2 Suspense](#82-suspense)
   - [8.3 Provide/Inject](#83-provideinject)
   - [8.4 Custom Directives](#84-custom-directives)
   - [8.5 Plugins](#85-plugins)

9. [Performance Optimization](#9-performance-optimization)

   - [9.1 Lazy Loading](#91-lazy-loading)
   - [9.2 Keep-Alive](#92-keep-alive)
   - [9.3 Virtual Scrolling](#93-virtual-scrolling)
   - [9.4 Production Build](#94-production-build)

10. [Vue Interview Questions](#10-vue-interview-questions)
    - [10.1 Fundamental Questions](#101-fundamental-questions)
    - [10.2 Advanced Questions](#102-advanced-questions)
    - [10.3 Practical Questions](#103-practical-questions)

---

## 1. Introduction to Vue.js

### 1.1 What is Vue.js?

Vue.js is a **progressive JavaScript framework** for building user interfaces. It focuses on the view layer and is designed to be incrementally adoptable.

> **Key Point:** Vue is progressive - you can use as little or as much as you need. Start with a simple script tag or build a full SPA.

#### Core Features

- **Declarative Rendering:** Template-based syntax
- **Component System:** Reusable, composable components
- **Reactivity System:** Automatic UI updates
- **Virtual DOM:** Efficient rendering
- **Single File Components:** HTML, CSS, JS in one file
- **Composition API:** Better code organization

#### Real-World Usage

Companies using Vue.js: Alibaba, Xiaomi, GitLab, Adobe, Nintendo, Grammarly, Laravel

### 1.2 Why Vue.js?

#### Advantages

1. **Easy to Learn:** Simple, intuitive API
2. **Progressive Framework:** Use what you need
3. **Great Documentation:** Clear, comprehensive docs
4. **Small Bundle Size:** ~33KB min+gzip
5. **Fast Performance:** Optimized virtual DOM
6. **Flexible:** Works with any backend
7. **Great Tooling:** Vue DevTools, Vite, etc.
8. **Active Community:** Large ecosystem

#### Disadvantages

1. **Smaller Ecosystem:** Compared to React
2. **Language Barrier:** Some resources in Chinese
3. **Less Corporate Backing:** Compared to React/Angular
4. **Over-flexibility:** Multiple ways to do things

#### When to Use Vue.js

- Building SPAs (Single Page Applications)
- Progressive enhancement of existing apps
- Rapid prototyping
- Small to large scale applications
- Teams wanting gentle learning curve

### 1.3 Vue 3 New Features

#### Major Updates in Vue 3

**1. Composition API**

- Better code organization
- Improved TypeScript support
- Better logic reuse
- More flexible than Options API

**2. Performance Improvements**

- Faster mounting/patching
- Smaller bundle size
- Better memory usage
- Tree-shaking support

**3. Multiple Root Elements (Fragments)**

- No need for wrapper divs
- Cleaner templates
- Better component composition

**4. Teleport**

- Render content outside component hierarchy
- Great for modals, tooltips
- Better DOM structure control

**5. Suspense**

- Handle async components
- Better loading states
- Cleaner async code

**6. Better TypeScript Support**

- Full TypeScript rewrite
- Better type inference
- Improved IDE support

**7. Custom Renderer API**

- Create custom renderers
- Render to different targets
- More flexibility

**8. Script Setup (Vue 3.2+)**

- Less boilerplate
- Better performance
- Cleaner syntax

### 1.4 Vue vs React vs Angular

| Feature              | Vue.js         | React          | Angular        |
| -------------------- | -------------- | -------------- | -------------- |
| Type                 | Framework      | Library        | Framework      |
| Learning Curve       | Easy           | Moderate       | Steep          |
| Bundle Size          | Small (~33KB)  | Small (~40KB)  | Large (~100KB) |
| Performance          | Fast           | Fast           | Fast           |
| TypeScript           | Optional       | Optional       | Required       |
| State Management     | Pinia/Vuex     | Redux/Context  | RxJS/NgRx      |
| Routing              | Vue Router     | React Router   | Built-in       |
| Template Syntax      | HTML-based     | JSX            | HTML-based     |
| Two-Way Binding      | Built-in       | Manual         | Built-in       |
| Mobile               | Ionic/NativeScript | React Native | Ionic/NativeScript |
| Corporate Backing    | Community      | Meta           | Google         |
| Flexibility          | High           | Very High      | Moderate       |

---

## 2. Installation and Setup

### 2.1 Installation Methods

#### Method 1: Using Vite (Recommended)

```bash
# Create new Vue project
npm create vue@latest

# Follow prompts:
# - Project name
# - TypeScript? (Yes/No)
# - JSX? (Yes/No)
# - Vue Router? (Yes/No)
# - Pinia? (Yes/No)
# - Vitest? (Yes/No)
# - ESLint? (Yes/No)
# - Prettier? (Yes/No)

cd project-name
npm install
npm run dev
```

#### Method 2: Using CDN (Quick Start)

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

#### Method 3: Using Vue CLI (Legacy)

```bash
npm install -g @vue/cli
vue create my-project
cd my-project
npm run serve
```

### 2.2 Project Structure

```
my-vue-app/
├── public/
│   └── favicon.ico
├── src/
│   ├── assets/          # Static assets
│   ├── components/      # Vue components
│   ├── composables/     # Reusable composition functions
│   ├── router/          # Vue Router config
│   ├── stores/          # Pinia stores
│   ├── views/           # Page components
│   ├── App.vue          # Root component
│   └── main.js          # Entry point
├── index.html
├── package.json
└── vite.config.js
```

### 2.3 Development Tools

#### Vue DevTools

- Browser extension for Chrome/Firefox
- Inspect component hierarchy
- Debug Vuex/Pinia stores
- Track events and performance
- Time-travel debugging

#### VS Code Extensions

1. **Volar** (Essential for Vue 3)
   - Syntax highlighting
   - IntelliSense
   - Type checking

2. **Vue VSCode Snippets**
   - Code snippets
   - Faster development

3. **ESLint**
   - Code linting
   - Style enforcement

---

## 3. Vue Fundamentals

### 3.1 Template Syntax

#### Text Interpolation

```vue
<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ count + 1 }}</p>
    <p>{{ ok ? 'YES' : 'NO' }}</p>
    <p>{{ message.split('').reverse().join('') }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "Hello Vue!",
      count: 10,
      ok: true,
    };
  },
};
</script>
```

#### Raw HTML

```vue
<template>
  <div>
    <p>{{ rawHtml }}</p>
    <!-- Renders as text -->
    <p v-html="rawHtml"></p>
    <!-- Renders as HTML -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      rawHtml: "<span style='color: red'>Red Text</span>",
    };
  },
};
</script>
```

### 3.2 Data Binding

#### Attribute Binding

```vue
<template>
  <div>
    <!-- Bind attributes -->
    <img :src="imageSrc" :alt="imageAlt" />
    <button :disabled="isDisabled">Button</button>
    <div :class="className">Styled div</div>
    <div :style="styleObject">Inline styles</div>

    <!-- Shorthand -->
    <img v-bind:src="imageSrc" />
    <!-- Full syntax -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      imageSrc: "image.jpg",
      imageAlt: "Description",
      isDisabled: false,
      className: "active",
      styleObject: {
        color: "red",
        fontSize: "14px",
      },
    };
  },
};
</script>
```

#### Class Binding

```vue
<template>
  <div>
    <!-- Object syntax -->
    <div :class="{ active: isActive, 'text-danger': hasError }">Text</div>

    <!-- Array syntax -->
    <div :class="[activeClass, errorClass]">Text</div>

    <!-- Mixed -->
    <div :class="[{ active: isActive }, errorClass]">Text</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: true,
      hasError: false,
      activeClass: "active",
      errorClass: "text-danger",
    };
  },
};
</script>
```

#### Style Binding

```vue
<template>
  <div>
    <!-- Object syntax -->
    <div :style="{ color: activeColor, fontSize: fontSize + 'px' }">Text</div>

    <!-- Array syntax -->
    <div :style="[baseStyles, overridingStyles]">Text</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeColor: "red",
      fontSize: 14,
      baseStyles: {
        color: "blue",
      },
      overridingStyles: {
        fontSize: "16px",
      },
    };
  },
};
</script>
```

### 3.3 Directives

#### v-if, v-else-if, v-else

```vue
<template>
  <div>
    <p v-if="score >= 90">Grade: A</p>
    <p v-else-if="score >= 80">Grade: B</p>
    <p v-else-if="score >= 70">Grade: C</p>
    <p v-else>Grade: F</p>

    <!-- v-show (always rendered, just hidden) -->
    <p v-show="isVisible">This can be toggled</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      score: 85,
      isVisible: true,
    };
  },
};
</script>
```

#### v-for

```vue
<template>
  <div>
    <!-- Array iteration -->
    <ul>
      <li v-for="(item, index) in items" :key="item.id">
        {{ index }}: {{ item.name }}
      </li>
    </ul>

    <!-- Object iteration -->
    <ul>
      <li v-for="(value, key, index) in user" :key="key">
        {{ index }}. {{ key }}: {{ value }}
      </li>
    </ul>

    <!-- Range -->
    <span v-for="n in 10" :key="n">{{ n }} </span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { id: 1, name: "Item 1" },
        { id: 2, name: "Item 2" },
      ],
      user: {
        name: "John",
        age: 30,
        city: "New York",
      },
    };
  },
};
</script>
```

#### v-model (Two-Way Binding)

```vue
<template>
  <div>
    <!-- Text input -->
    <input v-model="message" placeholder="Enter text" />
    <p>Message: {{ message }}</p>

    <!-- Checkbox -->
    <input type="checkbox" v-model="checked" />
    <p>Checked: {{ checked }}</p>

    <!-- Radio -->
    <input type="radio" value="One" v-model="picked" />
    <input type="radio" value="Two" v-model="picked" />
    <p>Picked: {{ picked }}</p>

    <!-- Select -->
    <select v-model="selected">
      <option disabled value="">Please select</option>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
    <p>Selected: {{ selected }}</p>

    <!-- Modifiers -->
    <input v-model.lazy="msg" />
    <!-- Update on change, not input -->
    <input v-model.number="age" type="number" />
    <!-- Auto type conversion -->
    <input v-model.trim="text" />
    <!-- Trim whitespace -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "",
      checked: false,
      picked: "",
      selected: "",
      msg: "",
      age: 0,
      text: "",
    };
  },
};
</script>
```

### 3.4 Event Handling

```vue
<template>
  <div>
    <!-- Basic event -->
    <button @click="count++">Count: {{ count }}</button>

    <!-- Method handler -->
    <button @click="greet">Greet</button>

    <!-- Inline handler with argument -->
    <button @click="say('hello')">Say Hello</button>

    <!-- Event object -->
    <button @click="handleClick">Click Me</button>

    <!-- Event modifiers -->
    <form @submit.prevent="onSubmit">
      <button type="submit">Submit</button>
    </form>

    <a @click.stop="doThis">Stop Propagation</a>
    <div @click.self="doThat">Only self</div>
    <button @click.once="doOnce">Click once</button>

    <!-- Key modifiers -->
    <input @keyup.enter="submit" />
    <input @keyup.esc="cancel" />
    <input @keyup.ctrl.enter="send" />

    <!-- Mouse modifiers -->
    <button @click.left="leftClick">Left Click</button>
    <button @click.right="rightClick">Right Click</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    greet() {
      alert("Hello!");
    },
    say(message) {
      alert(message);
    },
    handleClick(event) {
      console.log(event.target);
    },
    onSubmit() {
      console.log("Form submitted");
    },
    doThis() {},
    doThat() {},
    doOnce() {},
    submit() {},
    cancel() {},
    send() {},
    leftClick() {},
    rightClick() {},
  },
};
</script>
```

### 3.5 Computed Properties

```vue
<template>
  <div>
    <p>Original: {{ message }}</p>
    <p>Reversed: {{ reversedMessage }}</p>
    <p>Full Name: {{ fullName }}</p>

    <!-- Computed vs Method -->
    <p>{{ computedValue }}</p>
    <!-- Cached -->
    <p>{{ methodValue() }}</p>
    <!-- Not cached -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "Hello",
      firstName: "John",
      lastName: "Doe",
    };
  },
  computed: {
    // Getter only
    reversedMessage() {
      return this.message.split("").reverse().join("");
    },

    // Getter and Setter
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const names = value.split(" ");
        this.firstName = names[0];
        this.lastName = names[names.length - 1];
      },
    },

    computedValue() {
      return Date.now(); // Cached until dependencies change
    },
  },
  methods: {
    methodValue() {
      return Date.now(); // Called every time
    },
  },
};
</script>
```

### 3.6 Watchers

```vue
<template>
  <div>
    <input v-model="question" placeholder="Ask a yes/no question" />
    <p>{{ answer }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      question: "",
      answer: "Questions usually contain a question mark. ;-)",
      user: {
        name: "John",
        age: 30,
      },
    };
  },
  watch: {
    // Simple watcher
    question(newValue, oldValue) {
      if (newValue.includes("?")) {
        this.getAnswer();
      }
    },

    // Deep watcher for objects
    user: {
      handler(newValue, oldValue) {
        console.log("User changed:", newValue);
      },
      deep: true,
      immediate: true, // Run immediately on component creation
    },

    // Watch specific nested property
    "user.name"(newValue) {
      console.log("Name changed:", newValue);
    },
  },
  methods: {
    async getAnswer() {
      this.answer = "Thinking...";
      // Simulate API call
      setTimeout(() => {
        this.answer = Math.random() > 0.5 ? "Yes" : "No";
      }, 1000);
    },
  },
};
</script>
```

---

## 4. Components

### 4.1 Component Basics

#### Single File Component (SFC)

```vue
<!-- MyComponent.vue -->
<template>
  <div class="component">
    <h2>{{ title }}</h2>
    <p>{{ description }}</p>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data() {
    return {
      title: "Component Title",
      description: "Component description",
    };
  },
  methods: {
    handleClick() {
      console.log("Button clicked");
    },
  },
};
</script>

<style scoped>
.component {
  padding: 20px;
  border: 1px solid #ccc;
}
</style>
```

#### Using Components

```vue
<template>
  <div>
    <MyComponent />
    <MyComponent />
  </div>
</template>

<script>
import MyComponent from "./components/MyComponent.vue";

export default {
  components: {
    MyComponent,
  },
};
</script>
```

### 4.2 Props

```vue
<!-- ChildComponent.vue -->
<template>
  <div>
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <p>Count: {{ count }}</p>
  </div>
</template>

<script>
export default {
  name: "ChildComponent",
  props: {
    // Simple type check
    title: String,

    // Multiple types
    description: [String, Number],

    // Required prop
    count: {
      type: Number,
      required: true,
    },

    // With default value
    status: {
      type: String,
      default: "active",
    },

    // Object with default
    user: {
      type: Object,
      default: () => ({ name: "Guest" }),
    },

    // Custom validator
    age: {
      type: Number,
      validator: (value) => value >= 0 && value <= 150,
    },
  },
};
</script>
```

```vue
<!-- ParentComponent.vue -->
<template>
  <div>
    <ChildComponent
      title="Hello"
      description="Description"
      :count="10"
      status="active"
      :user="userData"
      :age="25"
    />
  </div>
</template>

<script>
import ChildComponent from "./ChildComponent.vue";

export default {
  components: { ChildComponent },
  data() {
    return {
      userData: { name: "John" },
    };
  },
};
</script>
```

### 4.3 Events

```vue
<!-- ChildComponent.vue -->
<template>
  <div>
    <button @click="handleClick">Click Me</button>
    <input @input="handleInput" />
  </div>
</template>

<script>
export default {
  name: "ChildComponent",
  emits: ["custom-event", "update-value"],
  methods: {
    handleClick() {
      // Emit event without data
      this.$emit("custom-event");
    },
    handleInput(event) {
      // Emit event with data
      this.$emit("update-value", event.target.value);
    },
  },
};
</script>
```

```vue
<!-- ParentComponent.vue -->
<template>
  <div>
    <ChildComponent @custom-event="onCustomEvent" @update-value="onUpdateValue" />
    <p>Value: {{ value }}</p>
  </div>
</template>

<script>
import ChildComponent from "./ChildComponent.vue";

export default {
  components: { ChildComponent },
  data() {
    return {
      value: "",
    };
  },
  methods: {
    onCustomEvent() {
      console.log("Custom event received");
    },
    onUpdateValue(newValue) {
      this.value = newValue;
    },
  },
};
</script>
```

### 4.4 Slots

#### Default Slot

```vue
<!-- CardComponent.vue -->
<template>
  <div class="card">
    <slot>Default content if no slot provided</slot>
  </div>
</template>
```

```vue
<!-- Usage -->
<template>
  <CardComponent>
    <h2>Card Title</h2>
    <p>Card content</p>
  </CardComponent>
</template>
```

#### Named Slots

```vue
<!-- LayoutComponent.vue -->
<template>
  <div class="layout">
    <header>
      <slot name="header">Default Header</slot>
    </header>
    <main>
      <slot>Default Content</slot>
    </main>
    <footer>
      <slot name="footer">Default Footer</slot>
    </footer>
  </div>
</template>
```

```vue
<!-- Usage -->
<template>
  <LayoutComponent>
    <template #header>
      <h1>Page Title</h1>
    </template>

    <p>Main content</p>

    <template #footer>
      <p>Footer content</p>
    </template>
  </LayoutComponent>
</template>
```

#### Scoped Slots

```vue
<!-- ListComponent.vue -->
<template>
  <ul>
    <li v-for="item in items" :key="item.id">
      <slot :item="item" :index="item.id">{{ item.name }}</slot>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    items: Array,
  },
};
</script>
```

```vue
<!-- Usage -->
<template>
  <ListComponent :items="users">
    <template #default="{ item, index }">
      <span>{{ index }}: {{ item.name }} ({{ item.age }})</span>
    </template>
  </ListComponent>
</template>
```

### 4.5 Component Registration

#### Global Registration

```javascript
// main.js
import { createApp } from "