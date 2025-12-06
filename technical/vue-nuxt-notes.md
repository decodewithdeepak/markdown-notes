# Vue.js & Nuxt.js Master Notes By Deepak Modi

> Latest Versions: Vue 3.5.24 | Nuxt 4.2.1 (2025) | Recommended: Vue.js & Nuxt Official Docs

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

| Feature           | Vue.js             | React         | Angular            |
| ----------------- | ------------------ | ------------- | ------------------ |
| Type              | Framework          | Library       | Framework          |
| Learning Curve    | Easy               | Moderate      | Steep              |
| Bundle Size       | Small (~33KB)      | Small (~40KB) | Large (~100KB)     |
| Performance       | Fast               | Fast          | Fast               |
| TypeScript        | Optional           | Optional      | Required           |
| State Management  | Pinia/Vuex         | Redux/Context | RxJS/NgRx          |
| Routing           | Vue Router         | React Router  | Built-in           |
| Template Syntax   | HTML-based         | JSX           | HTML-based         |
| Two-Way Binding   | Built-in           | Manual        | Built-in           |
| Mobile            | Ionic/NativeScript | React Native  | Ionic/NativeScript |
| Corporate Backing | Community          | Meta          | Google             |
| Flexibility       | High               | Very High     | Moderate           |

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
    <p>{{ ok ? "YES" : "NO" }}</p>
    <p>{{ message.split("").reverse().join("") }}</p>
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
    <ChildComponent
      @custom-event="onCustomEvent"
      @update-value="onUpdateValue"
    />
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
import { createApp } from "vue";
import App from "./App.vue";
import MyComponent from "./components/MyComponent.vue";

const app = createApp(App);
app.component("MyComponent", MyComponent);
app.mount("#app");
```

#### Local Registration

```vue
<script>
import MyComponent from "./components/MyComponent.vue";

export default {
  components: {
    MyComponent,
  },
};
</script>
```

---

## 5. Composition API

### 5.1 Setup Function

```vue
<template>
  <div>
    <p>Count: {{ count }}</p>
    <button @click="increment">Increment</button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    // Reactive state
    const count = ref(0);

    // Methods
    function increment() {
      count.value++;
    }

    // Expose to template
    return {
      count,
      increment,
    };
  },
};
</script>
```

#### Script Setup (Recommended)

```vue
<template>
  <div>
    <p>Count: {{ count }}</p>
    <button @click="increment">Increment</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Everything is automatically exposed to template
const count = ref(0);

function increment() {
  count.value++;
}
</script>
```

### 5.2 Reactive State

```vue
<script setup>
import { ref, reactive, computed, readonly } from "vue";

// ref - for primitives
const count = ref(0);
const message = ref("Hello");

// Access/modify with .value
count.value++;

// reactive - for objects
const state = reactive({
  name: "John",
  age: 30,
  hobbies: ["reading", "coding"],
});

// Access directly (no .value)
state.name = "Jane";

// readonly - prevent modifications
const readonlyState = readonly(state);

// toRef - create ref from reactive property
import { toRef } from "vue";
const nameRef = toRef(state, "name");

// toRefs - convert all properties to refs
import { toRefs } from "vue";
const { name, age } = toRefs(state);
</script>
```

### 5.3 Computed and Watch

```vue
<script setup>
import { ref, computed, watch, watchEffect } from "vue";

const count = ref(0);
const multiplier = ref(2);

// Computed
const doubled = computed(() => count.value * multiplier.value);

// Computed with getter and setter
const fullName = computed({
  get: () => `${firstName.value} ${lastName.value}`,
  set: (value) => {
    [firstName.value, lastName.value] = value.split(" ");
  },
});

// Watch single source
watch(count, (newValue, oldValue) => {
  console.log(`Count changed from ${oldValue} to ${newValue}`);
});

// Watch multiple sources
watch([count, multiplier], ([newCount, newMultiplier]) => {
  console.log(`Count: ${newCount}, Multiplier: ${newMultiplier}`);
});

// Watch with options
watch(
  count,
  (newValue) => {
    console.log(newValue);
  },
  {
    immediate: true, // Run immediately
    deep: true, // Deep watch for objects
  }
);

// watchEffect - automatically tracks dependencies
watchEffect(() => {
  console.log(`Count is ${count.value}`);
  // Automatically re-runs when count changes
});
</script>
```

### 5.4 Lifecycle Hooks

```vue
<script setup>
import {
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
  onErrorCaptured,
  onActivated,
  onDeactivated,
} from "vue";

// Before component is mounted
onBeforeMount(() => {
  console.log("Before mount");
});

// After component is mounted
onMounted(() => {
  console.log("Mounted");
  // DOM is available here
});

// Before component updates
onBeforeUpdate(() => {
  console.log("Before update");
});

// After component updates
onUpdated(() => {
  console.log("Updated");
});

// Before component is unmounted
onBeforeUnmount(() => {
  console.log("Before unmount");
  // Cleanup here
});

// After component is unmounted
onUnmounted(() => {
  console.log("Unmounted");
});

// Error handling
onErrorCaptured((err, instance, info) => {
  console.error("Error captured:", err);
  return false; // Prevent propagation
});

// Keep-alive hooks
onActivated(() => {
  console.log("Component activated");
});

onDeactivated(() => {
  console.log("Component deactivated");
});
</script>
```

### 5.5 Composables

Composables are reusable composition functions.

```javascript
// composables/useCounter.js
import { ref, computed } from "vue";

export function useCounter(initialValue = 0) {
  const count = ref(initialValue);

  const doubled = computed(() => count.value * 2);

  function increment() {
    count.value++;
  }

  function decrement() {
    count.value--;
  }

  function reset() {
    count.value = initialValue;
  }

  return {
    count,
    doubled,
    increment,
    decrement,
    reset,
  };
}
```

```vue
<!-- Usage in component -->
<template>
  <div>
    <p>Count: {{ count }}</p>
    <p>Doubled: {{ doubled }}</p>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
    <button @click="reset">Reset</button>
  </div>
</template>

<script setup>
import { useCounter } from "@/composables/useCounter";

const { count, doubled, increment, decrement, reset } = useCounter(10);
</script>
```

#### Common Composables

```javascript
// composables/useFetch.js
import { ref } from "vue";

export function useFetch(url) {
  const data = ref(null);
  const error = ref(null);
  const loading = ref(false);

  async function fetchData() {
    loading.value = true;
    try {
      const response = await fetch(url);
      data.value = await response.json();
    } catch (err) {
      error.value = err;
    } finally {
      loading.value = false;
    }
  }

  return { data, error, loading, fetchData };
}
```

```javascript
// composables/useLocalStorage.js
import { ref, watch } from "vue";

export function useLocalStorage(key, defaultValue) {
  const storedValue = localStorage.getItem(key);
  const value = ref(storedValue ? JSON.parse(storedValue) : defaultValue);

  watch(
    value,
    (newValue) => {
      localStorage.setItem(key, JSON.stringify(newValue));
    },
    { deep: true }
  );

  return value;
}
```

---

## 6. Vue Router

### 6.1 Router Setup

```bash
npm install vue-router@4
```

```javascript
// router/index.js
import { createRouter, createWebHistory } from "vue-router";
import Home from "@/views/Home.vue";
import About from "@/views/About.vue";

const routes = [
  {
    path: "/",
    name: "Home",
    component: Home,
  },
  {
    path: "/about",
    name: "About",
    component: About,
  },
  {
    path: "/user/:id",
    name: "User",
    component: () => import("@/views/User.vue"), // Lazy loading
    props: true, // Pass route params as props
  },
];

const router = createRouter({
  history: createWebHistory(),
  routes,
});

export default router;
```

```javascript
// main.js
import { createApp } from "vue";
import App from "./App.vue";
import router from "./router";

createApp(App).use(router).mount("#app");
```

```vue
<!-- App.vue -->
<template>
  <div>
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </nav>
    <router-view />
  </div>
</template>
```

### 6.2 Navigation

```vue
<script setup>
import { useRouter, useRoute } from "vue-router";

const router = useRouter();
const route = useRoute();

// Programmatic navigation
function goToAbout() {
  router.push("/about");
}

function goToUser() {
  router.push({ name: "User", params: { id: 123 } });
}

function goBack() {
  router.go(-1);
}

function replace() {
  router.replace("/about"); // No history entry
}

// Access current route
console.log(route.path); // Current path
console.log(route.params); // Route parameters
console.log(route.query); // Query parameters
</script>
```

### 6.3 Dynamic Routes

```javascript
// router/index.js
const routes = [
  {
    path: "/user/:id",
    component: User,
  },
  {
    path: "/post/:id(\\d+)", // Regex: only numbers
    component: Post,
  },
  {
    path: "/files/:path(.*)", // Catch-all
    component: Files,
  },
];
```

```vue
<!-- User.vue -->
<template>
  <div>
    <h1>User {{ $route.params.id }}</h1>
    <!-- or -->
    <h1>User {{ id }}</h1>
  </div>
</template>

<script setup>
import { useRoute } from "vue-router";

const route = useRoute();
const id = route.params.id;

// Or with props
defineProps({
  id: String,
});
</script>
```

### 6.4 Route Guards

```javascript
// router/index.js
const router = createRouter({
  // ...
});

// Global before guard
router.beforeEach((to, from, next) => {
  const isAuthenticated = checkAuth();

  if (to.meta.requiresAuth && !isAuthenticated) {
    next("/login");
  } else {
    next();
  }
});

// Global after hook
router.afterEach((to, from) => {
  document.title = to.meta.title || "My App";
});

// Per-route guard
const routes = [
  {
    path: "/admin",
    component: Admin,
    beforeEnter: (to, from, next) => {
      if (checkAdminAuth()) {
        next();
      } else {
        next("/");
      }
    },
  },
];
```

```vue
<!-- Component guard -->
<script setup>
import { onBeforeRouteLeave, onBeforeRouteUpdate } from "vue-router";

// Before leaving this route
onBeforeRouteLeave((to, from) => {
  const answer = window.confirm("Do you really want to leave?");
  if (!answer) return false;
});

// When route changes but component is reused
onBeforeRouteUpdate((to, from) => {
  // Fetch new data
});
</script>
```

### 6.5 Nested Routes

```javascript
// router/index.js
const routes = [
  {
    path: "/user/:id",
    component: User,
    children: [
      {
        path: "", // Default child route
        component: UserHome,
      },
      {
        path: "profile",
        component: UserProfile,
      },
      {
        path: "posts",
        component: UserPosts,
      },
    ],
  },
];
```

```vue
<!-- User.vue -->
<template>
  <div>
    <h1>User {{ $route.params.id }}</h1>
    <nav>
      <router-link :to="`/user/${$route.params.id}`">Home</router-link>
      <router-link :to="`/user/${$route.params.id}/profile`"
        >Profile</router-link
      >
      <router-link :to="`/user/${$route.params.id}/posts`">Posts</router-link>
    </nav>
    <router-view />
    <!-- Nested routes render here -->
  </div>
</template>
```

---

## 7. State Management (Pinia)

### 7.1 Pinia Setup

```bash
npm install pinia
```

```javascript
// main.js
import { createApp } from "vue";
import { createPinia } from "pinia";
import App from "./App.vue";

const pinia = createPinia();
const app = createApp(App);

app.use(pinia);
app.mount("#app");
```

### 7.2 Stores

```javascript
// stores/counter.js
import { defineStore } from "pinia";

export const useCounterStore = defineStore("counter", {
  // State
  state: () => ({
    count: 0,
    name: "Counter",
  }),

  // Getters (like computed)
  getters: {
    doubleCount: (state) => state.count * 2,
    doubleCountPlusOne() {
      return this.doubleCount + 1;
    },
  },

  // Actions (like methods)
  actions: {
    increment() {
      this.count++;
    },
    decrement() {
      this.count--;
    },
    async fetchCount() {
      const response = await fetch("/api/count");
      this.count = await response.json();
    },
  },
});
```

#### Setup Stores (Composition API Style)

```javascript
// stores/counter.js
import { defineStore } from "pinia";
import { ref, computed } from "vue";

export const useCounterStore = defineStore("counter", () => {
  // State
  const count = ref(0);
  const name = ref("Counter");

  // Getters
  const doubleCount = computed(() => count.value * 2);

  // Actions
  function increment() {
    count.value++;
  }

  function decrement() {
    count.value--;
  }

  return {
    count,
    name,
    doubleCount,
    increment,
    decrement,
  };
});
```

### 7.3 State, Getters, Actions

```vue
<template>
  <div>
    <p>Count: {{ counter.count }}</p>
    <p>Double: {{ counter.doubleCount }}</p>
    <button @click="counter.increment()">+</button>
    <button @click="counter.decrement()">-</button>

    <!-- Destructure with storeToRefs -->
    <p>Count: {{ count }}</p>
    <p>Double: {{ doubleCount }}</p>
    <button @click="increment">+</button>
  </div>
</template>

<script setup>
import { useCounterStore } from "@/stores/counter";
import { storeToRefs } from "pinia";

// Use store
const counter = useCounterStore();

// Destructure (loses reactivity without storeToRefs)
const { count, doubleCount } = storeToRefs(counter);
const { increment, decrement } = counter;

// Direct state mutation
counter.count++;

// Patch multiple changes
counter.$patch({
  count: counter.count + 1,
  name: "New Name",
});

// Replace entire state
counter.$state = { count: 0, name: "Reset" };

// Reset to initial state
counter.$reset();
</script>
```

### 7.4 Store Composition

```javascript
// stores/user.js
import { defineStore } from "pinia";
import { useCartStore } from "./cart";

export const useUserStore = defineStore("user", {
  state: () => ({
    name: "John",
    email: "john@example.com",
  }),

  actions: {
    async checkout() {
      // Use another store
      const cart = useCartStore();
      await cart.purchase();
    },
  },
});
```

---

## 8. Advanced Features

### 8.1 Teleport

Render content in a different part of the DOM.

```vue
<template>
  <div>
    <button @click="showModal = true">Open Modal</button>

    <Teleport to="body">
      <div v-if="showModal" class="modal">
        <div class="modal-content">
          <h2>Modal Title</h2>
          <p>Modal content</p>
          <button @click="showModal = false">Close</button>
        </div>
      </div>
    </Teleport>
  </div>
</template>

<script setup>
import { ref } from "vue";

const showModal = ref(false);
</script>

<style>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
```

### 8.2 Suspense

Handle async components with loading states.

```vue
<template>
  <Suspense>
    <!-- Async component -->
    <template #default>
      <AsyncComponent />
    </template>

    <!-- Loading state -->
    <template #fallback>
      <div>Loading...</div>
    </template>
  </Suspense>
</template>

<script setup>
import { defineAsyncComponent } from "vue";

const AsyncComponent = defineAsyncComponent(() =>
  import("./AsyncComponent.vue")
);
</script>
```

```vue
<!-- AsyncComponent.vue -->
<script setup>
// Top-level await in setup
const data = await fetch("/api/data").then((r) => r.json());
</script>

<template>
  <div>{{ data }}</div>
</template>
```

### 8.3 Provide/Inject

Share data across component tree without props.

```vue
<!-- Parent.vue -->
<script setup>
import { provide, ref } from "vue";

const theme = ref("dark");
const updateTheme = (newTheme) => {
  theme.value = newTheme;
};

provide("theme", theme);
provide("updateTheme", updateTheme);
</script>
```

```vue
<!-- Child.vue (any level deep) -->
<script setup>
import { inject } from "vue";

const theme = inject("theme");
const updateTheme = inject("updateTheme");

// With default value
const user = inject("user", { name: "Guest" });
</script>

<template>
  <div :class="theme">
    <button @click="updateTheme('light')">Light</button>
    <button @click="updateTheme('dark')">Dark</button>
  </div>
</template>
```

### 8.4 Custom Directives

```javascript
// directives/focus.js
export const vFocus = {
  mounted: (el) => el.focus(),
};
```

```vue
<script setup>
import { vFocus } from "@/directives/focus";
</script>

<template>
  <input v-focus />
</template>
```

#### Advanced Directive

```javascript
// directives/clickOutside.js
export const vClickOutside = {
  mounted(el, binding) {
    el.clickOutsideEvent = (event) => {
      if (!(el === event.target || el.contains(event.target))) {
        binding.value(event);
      }
    };
    document.addEventListener("click", el.clickOutsideEvent);
  },
  unmounted(el) {
    document.removeEventListener("click", el.clickOutsideEvent);
  },
};
```

```vue
<template>
  <div v-click-outside="closeDropdown" class="dropdown">
    <!-- Dropdown content -->
  </div>
</template>

<script setup>
import { vClickOutside } from "@/directives/clickOutside";

function closeDropdown() {
  console.log("Clicked outside");
}
</script>
```

### 8.5 Plugins

```javascript
// plugins/myPlugin.js
export default {
  install(app, options) {
    // Global property
    app.config.globalProperties.$myMethod = () => {
      console.log("My method");
    };

    // Global component
    app.component("MyComponent", MyComponent);

    // Directive
    app.directive("my-directive", {
      /* ... */
    });

    // Provide
    app.provide("myKey", "myValue");
  },
};
```

```javascript
// main.js
import myPlugin from "./plugins/myPlugin";

app.use(myPlugin, {
  /* options */
});
```

---

## 9. Performance Optimization

### 9.1 Lazy Loading

```javascript
// router/index.js
const routes = [
  {
    path: "/about",
    component: () => import("@/views/About.vue"), // Lazy loaded
  },
];
```

```vue
<script setup>
import { defineAsyncComponent } from "vue";

// Lazy load component
const HeavyComponent = defineAsyncComponent(() =>
  import("./HeavyComponent.vue")
);
</script>
```

### 9.2 Keep-Alive

Cache component instances to avoid re-rendering.

```vue
<template>
  <keep-alive>
    <component :is="currentComponent" />
  </keep-alive>

  <!-- With include/exclude -->
  <keep-alive :include="['ComponentA', 'ComponentB']">
    <router-view />
  </keep-alive>

  <!-- With max instances -->
  <keep-alive :max="10">
    <router-view />
  </keep-alive>
</template>
```

### 9.3 Virtual Scrolling

For large lists, render only visible items.

```bash
npm install vue-virtual-scroller
```

```vue
<template>
  <RecycleScroller
    :items="items"
    :item-size="50"
    key-field="id"
    v-slot="{ item }"
  >
    <div class="item">{{ item.name }}</div>
  </RecycleScroller>
</template>

<script setup>
import { RecycleScroller } from "vue-virtual-scroller";
import "vue-virtual-scroller/dist/vue-virtual-scroller.css";

const items = ref(
  Array.from({ length: 10000 }, (_, i) => ({ id: i, name: `Item ${i}` }))
);
</script>
```

### 9.4 Production Build

```bash
# Build for production
npm run build

# Preview production build
npm run preview
```

```javascript
// vite.config.js
export default {
  build: {
    // Minify
    minify: "terser",
    terserOptions: {
      compress: {
        drop_console: true, // Remove console.log
      },
    },
    // Code splitting
    rollupOptions: {
      output: {
        manualChunks: {
          vendor: ["vue", "vue-router", "pinia"],
        },
      },
    },
  },
};
```

---

## 10. Vue Interview Questions

### 10.1 Fundamental Questions

**Q: What is Vue.js?**
A: Vue.js is a progressive JavaScript framework for building user interfaces. It focuses on the view layer and can be easily integrated into projects.

**Q: What are the key features of Vue.js?**
A: Reactive data binding, component-based architecture, virtual DOM, directives, computed properties, watchers, and easy integration.

**Q: What is the difference between v-if and v-show?**
A: `v-if` conditionally renders elements (adds/removes from DOM), while `v-show` toggles CSS display property. `v-if` has higher toggle cost, `v-show` has higher initial render cost.

**Q: What is the Virtual DOM?**
A: A lightweight JavaScript representation of the actual DOM. Vue uses it to efficiently update the real DOM by comparing changes and only updating what's necessary.

**Q: What are Vue directives?**
A: Special attributes with the `v-` prefix that apply reactive behavior to the DOM. Examples: `v-if`, `v-for`, `v-bind`, `v-on`, `v-model`.

**Q: What is v-model?**
A: A directive that creates two-way data binding on form inputs. It's syntactic sugar for `:value` and `@input`.

**Q: What are props?**
A: Props are custom attributes for passing data from parent to child components. They are read-only in the child component.

**Q: What is the difference between computed and methods?**
A: Computed properties are cached based on dependencies and only re-evaluate when dependencies change. Methods run every time they're called.

**Q: What are watchers?**
A: Watchers observe reactive data and perform actions when data changes. Useful for async operations or expensive operations in response to data changes.

**Q: What is the difference between Options API and Composition API?**
A: Options API organizes code by options (data, methods, computed), while Composition API organizes by logical concerns using composition functions. Composition API offers better TypeScript support and code reuse.

### 10.2 Advanced Questions

**Q: Explain Vue's reactivity system.**
A: Vue 3 uses Proxy-based reactivity. When you create reactive data, Vue wraps it in a Proxy that intercepts property access and modifications, tracking dependencies and triggering updates when data changes.

**Q: What is the difference between ref and reactive?**
A: `ref` is for primitive values and requires `.value` to access/modify. `reactive` is for objects and doesn't need `.value`. `ref` can hold any value type, `reactive` only works with objects.

**Q: What are lifecycle hooks?**
A: Functions called at specific stages of a component's lifecycle: `onBeforeMount`, `onMounted`, `onBeforeUpdate`, `onUpdated`, `onBeforeUnmount`, `onUnmounted`.

**Q: What is Teleport?**
A: A built-in component that renders its content in a different part of the DOM tree, useful for modals, tooltips, and notifications.

**Q: What is Suspense?**
A: A component for handling async dependencies, showing fallback content while waiting for async components to load.

**Q: What are composables?**
A: Reusable composition functions that encapsulate stateful logic. They follow the `use*` naming convention and return reactive state and functions.

**Q: How does Vue Router work?**
A: Vue Router maps URLs to components, enabling SPA navigation. It uses HTML5 History API or hash mode for routing without page reloads.

**Q: What are route guards?**
A: Functions that control navigation: `beforeEach`, `beforeEnter`, `beforeRouteEnter`, `beforeRouteUpdate`, `beforeRouteLeave`. Used for authentication, authorization, and data fetching.

**Q: What is Pinia?**
A: The official state management library for Vue 3. It's simpler than Vuex, with better TypeScript support and no mutations (only actions).

**Q: How do you optimize Vue app performance?**
A: Lazy loading, code splitting, keep-alive, virtual scrolling, computed properties, production builds, avoiding unnecessary re-renders, using v-once for static content.

### 10.3 Practical Questions

**Q: How do you pass data from child to parent?**
A: Using custom events with `$emit` in the child and `@event-name` in the parent.

**Q: How do you share data between sibling components?**
A: Using a parent component as intermediary, provide/inject, or state management (Pinia).

**Q: How do you handle forms in Vue?**
A: Using `v-model` for two-way binding, handling submit events with `@submit.prevent`, validating data, and managing form state.

**Q: How do you make API calls in Vue?**
A: Using `fetch` or `axios` in lifecycle hooks (onMounted) or composables. Handle loading states, errors, and update reactive data.

**Q: How do you implement authentication?**
A: Store auth token in localStorage/cookies, use route guards to protect routes, create auth store with Pinia, implement login/logout actions.

**Q: How do you handle errors in Vue?**
A: Using try-catch blocks, error boundaries with `onErrorCaptured`, global error handler `app.config.errorHandler`.

**Q: How do you test Vue components?**
A: Using Vitest or Jest with Vue Test Utils. Test component rendering, user interactions, props, events, and computed properties.

**Q: How do you implement lazy loading?**
A: Using dynamic imports with `defineAsyncComponent` or in router with `() => import('./Component.vue')`.

**Q: How do you create a custom directive?**
A: Define an object with lifecycle hooks (mounted, updated, unmounted) and register it globally or locally.

**Q: How do you optimize large lists?**
A: Use virtual scrolling libraries like `vue-virtual-scroller`, implement pagination, or use `v-show` instead of `v-if` when appropriate.

---

# Part 2: Nuxt.js

## Table of Contents - Nuxt.js

1. [Introduction to Nuxt.js](#1-introduction-to-nuxtjs)

   - [1.1 What is Nuxt.js?](#11-what-is-nuxtjs)
   - [1.2 Why Nuxt.js?](#12-why-nuxtjs)
   - [1.3 Nuxt 4 New Features](#13-nuxt-4-new-features)
   - [1.4 Nuxt vs Next.js](#14-nuxt-vs-nextjs)

2. [Installation and Setup](#2-installation-and-setup-nuxt)

   - [2.1 Installation](#21-installation-nuxt)
   - [2.2 Project Structure](#22-project-structure-nuxt)
   - [2.3 Configuration](#23-configuration-nuxt)

3. [Routing](#3-routing)

   - [3.1 File-Based Routing](#31-file-based-routing)
   - [3.2 Dynamic Routes](#32-dynamic-routes)
   - [3.3 Nested Routes](#33-nested-routes)
   - [3.4 Navigation](#34-navigation)
   - [3.5 Middleware](#35-middleware)

4. [Data Fetching](#4-data-fetching)

   - [4.1 useFetch](#41-usefetch)
   - [4.2 useAsyncData](#42-useasyncdata)
   - [4.3 useLazyFetch](#43-uselazyfetch)
   - [4.4 $fetch](#44-fetch)

5. [Rendering Modes](#5-rendering-modes)

   - [5.1 Universal Rendering (SSR)](#51-universal-rendering-ssr)
   - [5.2 Client-Side Rendering](#52-client-side-rendering)
   - [5.3 Static Site Generation](#53-static-site-generation)
   - [5.4 Hybrid Rendering](#54-hybrid-rendering)

6. [State Management](#6-state-management-nuxt)

   - [6.1 useState](#61-usestate)
   - [6.2 Pinia Integration](#62-pinia-integration)

7. [Server Routes](#7-server-routes)

   - [7.1 API Routes](#71-api-routes)
   - [7.2 Server Middleware](#72-server-middleware)
   - [7.3 Server Utils](#73-server-utils)

8. [Modules and Plugins](#8-modules-and-plugins)

   - [8.1 Nuxt Modules](#81-nuxt-modules)
   - [8.2 Plugins](#82-plugins)
   - [8.3 Auto Imports](#83-auto-imports)

9. [SEO and Meta](#9-seo-and-meta)

   - [9.1 useHead](#91-usehead)
   - [9.2 useSeoMeta](#92-useseometa)
   - [9.3 Dynamic Meta Tags](#93-dynamic-meta-tags)

10. [Deployment](#10-deployment)

    - [10.1 Build for Production](#101-build-for-production)
    - [10.2 Deployment Platforms](#102-deployment-platforms)

11. [Nuxt Interview Questions](#11-nuxt-interview-questions)
    - [11.1 Fundamental Questions](#111-fundamental-questions)
    - [11.2 Advanced Questions](#112-advanced-questions)
    - [11.3 Practical Questions](#113-practical-questions)

---

## 1. Introduction to Nuxt.js

### 1.1 What is Nuxt.js?

Nuxt.js is a **meta-framework built on top of Vue.js** that provides a higher-level structure for building production-ready applications with features like SSR, SSG, file-based routing, and more.

> **Key Point:** Nuxt is to Vue what Next.js is to React - a framework that adds structure, conventions, and powerful features.

#### Core Features

- **Server-Side Rendering (SSR):** Better SEO and performance
- **Static Site Generation (SSG):** Pre-render pages at build time
- **File-Based Routing:** Automatic route generation
- **Auto Imports:** Components, composables auto-imported
- **API Routes:** Built-in server routes
- **Module System:** Extend functionality easily
- **TypeScript Support:** First-class TypeScript support

### 1.2 Why Nuxt.js?

#### Advantages

1. **SEO-Friendly:** SSR for better search engine indexing
2. **Fast Performance:** Optimized builds and code splitting
3. **Developer Experience:** Auto imports, hot reload, DevTools
4. **Flexible Rendering:** SSR, SSG, CSR, or hybrid
5. **Built-in Features:** Routing, state, data fetching
6. **Large Ecosystem:** Many official and community modules
7. **Production-Ready:** Optimized for production out of the box

#### When to Use Nuxt.js

- SEO-critical applications
- E-commerce websites
- Content-heavy sites
- Landing pages
- Documentation sites
- Full-stack applications

### 1.3 Nuxt 4 New Features

#### Major Updates in Nuxt 4 (2025)

**1. Vue 3.5 Integration**

- Latest Vue.js features
- Better performance
- Improved TypeScript support

**2. Enhanced Performance**

- Faster build times
- Optimized hydration
- Better code splitting

**3. Improved Developer Experience**

- Better error messages
- Enhanced DevTools
- Faster HMR (Hot Module Replacement)

**4. New Composables**

- More utility composables
- Better data fetching
- Enhanced state management

**5. Better TypeScript Support**

- Improved type inference
- Better IDE integration
- Type-safe routing

**6. Module Improvements**

- Easier module creation
- Better module compatibility
- Enhanced module ecosystem

### 1.4 Nuxt vs Next.js

| Feature          | Nuxt.js        | Next.js      |
| ---------------- | -------------- | ------------ |
| Framework        | Vue.js         | React        |
| Routing          | File-based     | File-based   |
| SSR              | Built-in       | Built-in     |
| SSG              | Built-in       | Built-in     |
| API Routes       | Built-in       | Built-in     |
| Auto Imports     | Yes            | No (manual)  |
| State Management | Built-in       | External     |
| Learning Curve   | Easy           | Moderate     |
| TypeScript       | First-class    | First-class  |
| Module System    | Rich ecosystem | Plugin-based |

---

## 2. Installation and Setup (Nuxt)

### 2.1 Installation (Nuxt)

```bash
# Create new Nuxt project
npx nuxi@latest init my-nuxt-app

cd my-nuxt-app
npm install
npm run dev
```

### 2.2 Project Structure (Nuxt)

```
my-nuxt-app/
├── .nuxt/              # Build output (auto-generated)
├── assets/             # Uncompiled assets (CSS, images)
├── components/         # Vue components (auto-imported)
├── composables/        # Composables (auto-imported)
├── layouts/            # App layouts
├── middleware/         # Route middleware
├── pages/              # File-based routing
├── plugins/            # Plugins
├── public/             # Static files
├── server/             # Server-side code
│   ├── api/            # API routes
│   ├── middleware/     # Server middleware
│   └── utils/          # Server utilities
├── utils/              # Utilities (auto-imported)
├── app.vue             # Main app component
├── nuxt.config.ts      # Nuxt configuration
└── package.json
```

### 2.3 Configuration (Nuxt)

```typescript
// nuxt.config.ts
export default defineNuxtConfig({
  // App config
  app: {
    head: {
      title: "My Nuxt App",
      meta: [{ name: "description", content: "My amazing site" }],
      link: [{ rel: "icon", type: "image/x-icon", href: "/favicon.ico" }],
    },
  },

  // Modules
  modules: ["@nuxtjs/tailwindcss", "@pinia/nuxt"],

  // Runtime config
  runtimeConfig: {
    // Private keys (server-only)
    apiSecret: process.env.API_SECRET,
    // Public keys (client + server)
    public: {
      apiBase: process.env.API_BASE_URL,
    },
  },

  // Build config
  build: {
    transpile: [],
  },

  // Vite config
  vite: {
    css: {
      preprocessorOptions: {
        scss: {
          additionalData: '@use "@/assets/styles/variables.scss" as *;',
        },
      },
    },
  },

  // TypeScript
  typescript: {
    strict: true,
    typeCheck: true,
  },

  // Dev server
  devServer: {
    port: 3000,
  },
});
```

---

## 3. Routing

### 3.1 File-Based Routing

Nuxt automatically generates routes based on file structure in `pages/` directory.

```
pages/
├── index.vue           → /
├── about.vue           → /about
├── posts/
│   ├── index.vue       → /posts
│   └── [id].vue        → /posts/:id
└── users/
    └── [id]/
        ├── index.vue   → /users/:id
        └── profile.vue → /users/:id/profile
```

```vue
<!-- pages/index.vue -->
<template>
  <div>
    <h1>Home Page</h1>
  </div>
</template>
```

### 3.2 Dynamic Routes

```vue
<!-- pages/posts/[id].vue -->
<template>
  <div>
    <h1>Post {{ id }}</h1>
    <p>{{ post.title }}</p>
  </div>
</template>

<script setup>
const route = useRoute();
const id = route.params.id;

const { data: post } = await useFetch(`/api/posts/${id}`);
</script>
```

#### Catch-All Routes

```vue
<!-- pages/[...slug].vue -->
<template>
  <div>
    <h1>Path: {{ $route.params.slug }}</h1>
  </div>
</template>
```

### 3.3 Nested Routes

```
pages/
└── parent/
    ├── index.vue       → /parent
    ├── child.vue       → /parent/child
    └── [id].vue        → /parent/:id
```

```vue
<!-- pages/parent.vue -->
<template>
  <div>
    <h1>Parent Layout</h1>
    <NuxtPage />
    <!-- Child routes render here -->
  </div>
</template>
```

### 3.4 Navigation

```vue
<template>
  <div>
    <!-- NuxtLink component -->
    <NuxtLink to="/">Home</NuxtLink>
    <NuxtLink to="/about">About</NuxtLink>
    <NuxtLink :to="`/posts/${post.id}`">Post</NuxtLink>

    <!-- Programmatic navigation -->
    <button @click="goToAbout">Go to About</button>
  </div>
</template>

<script setup>
const router = useRouter();

function goToAbout() {
  router.push("/about");
}

// Other navigation methods
router.replace("/about"); // No history entry
router.back(); // Go back
router.forward(); // Go forward
</script>
```

### 3.5 Middleware

#### Route Middleware

```typescript
// middleware/auth.ts
export default defineNuxtRouteMiddleware((to, from) => {
  const user = useState("user");

  if (!user.value) {
    return navigateTo("/login");
  }
});
```

```vue
<!-- pages/dashboard.vue -->
<script setup>
definePageMeta({
  middleware: "auth",
});
</script>

<template>
  <div>
    <h1>Dashboard</h1>
  </div>
</template>
```

#### Global Middleware

```typescript
// middleware/analytics.global.ts
export default defineNuxtRouteMiddleware((to, from) => {
  // Runs on every route change
  console.log("Navigating to:", to.path);
});
```

---

## 4. Data Fetching

### 4.1 useFetch

Wrapper around `useAsyncData` and `$fetch`.

```vue
<script setup>
// Basic usage
const { data, pending, error, refresh } = await useFetch("/api/posts");

// With options
const { data: post } = await useFetch(`/api/posts/${id}`, {
  method: "GET",
  headers: {
    Authorization: `Bearer ${token}`,
  },
  query: {
    page: 1,
    limit: 10,
  },
  // Transform response
  transform: (data) => data.posts,
  // Pick specific fields
  pick: ["id", "title"],
});

// Watch reactive dependencies
const id = ref(1);
const { data } = await useFetch(`/api/posts/${id}`, {
  watch: [id], // Refetch when id changes
});
</script>

<template>
  <div>
    <div v-if="pending">Loading...</div>
    <div v-else-if="error">Error: {{ error.message }}</div>
    <div v-else>
      <div v-for="post in data" :key="post.id">{{ post.title }}</div>
      <button @click="refresh">Refresh</button>
    </div>
  </div>
</template>
```

### 4.2 useAsyncData

More flexible data fetching with custom fetcher function.

```vue
<script setup>
const { data, pending, error, refresh } = await useAsyncData("posts", () =>
  $fetch("/api/posts")
);

// With dependencies
const id = ref(1);
const { data: post } = await useAsyncData(
  `post-${id.value}`,
  () => $fetch(`/api/posts/${id.value}`),
  {
    watch: [id],
  }
);

// Server-only fetching
const { data } = await useAsyncData(
  "server-data",
  () => $fetch("/api/server-only"),
  {
    server: true,
    lazy: false,
  }
);
</script>
```

### 4.3 useLazyFetch

Non-blocking data fetching (doesn't block navigation).

```vue
<script setup>
// Doesn't block navigation
const { pending, data: posts } = useLazyFetch("/api/posts");
</script>

<template>
  <div>
    <div v-if="pending">Loading...</div>
    <div v-else>
      <div v-for="post in posts" :key="post.id">{{ post.title }}</div>
    </div>
  </div>
</template>
```

### 4.4 $fetch

Direct API calls (not SSR-friendly, use in client-side only).

```vue
<script setup>
async function submitForm() {
  try {
    const result = await $fetch("/api/posts", {
      method: "POST",
      body: {
        title: "New Post",
        content: "Content",
      },
    });
    console.log("Success:", result);
  } catch (error) {
    console.error("Error:", error);
  }
}
</script>
```

---

## 5. Rendering Modes

### 5.1 Universal Rendering (SSR)

Default mode. Pages rendered on server, then hydrated on client.

```typescript
// nuxt.config.ts
export default defineNuxtConfig({
  ssr: true, // Default
});
```

### 5.2 Client-Side Rendering

Render everything on client (like traditional SPA).

```typescript
// nuxt.config.ts
export default defineNuxtConfig({
  ssr: false,
});
```

```vue
<!-- Per-component CSR -->
<template>
  <ClientOnly>
    <div>This only renders on client</div>
    <template #fallback>
      <div>Loading...</div>
    </template>
  </ClientOnly>
</template>
```

### 5.3 Static Site Generation

Pre-render pages at build time.

```bash
# Generate static site
npm run generate
```

```typescript
// nuxt.config.ts
export default defineNuxtConfig({
  nitro: {
    prerender: {
      routes: ["/", "/about", "/posts/1"],
    },
  },
});
```

### 5.4 Hybrid Rendering

Mix SSR, SSG, and CSR per route.

```vue
<script setup>
defineRouteRules({
  // SSR (default)
  "/": { ssr: true },

  // SSG
  "/about": { prerender: true },

  // CSR
  "/dashboard": { ssr: false },

  // ISR (Incremental Static Regeneration)
  "/blog/**": { swr: 3600 }, // Revalidate every hour
});
</script>
```

---

## 6. State Management (Nuxt)

### 6.1 useState

Shared state across components (SSR-friendly).

```typescript
// composables/useCounter.ts
export const useCounter = () => {
  return useState("counter", () => 0);
};
```

```vue
<script setup>
const counter = useCounter();

function increment() {
  counter.value++;
}
</script>

<template>
  <div>
    <p>Count: {{ counter }}</p>
    <button @click="increment">Increment</button>
  </div>
</template>
```

### 6.2 Pinia Integration

```bash
npm install @pinia/nuxt
```

```typescript
// nuxt.config.ts
export default defineNuxtConfig({
  modules: ["@pinia/nuxt"],
});
```

```typescript
// stores/counter.ts
import { defineStore } from "pinia";

export const useCounterStore = defineStore("counter", {
  state: () => ({
    count: 0,
  }),
  actions: {
    increment() {
      this.count++;
    },
  },
});
```

```vue
<script setup>
const counter = useCounterStore();
</script>

<template>
  <div>
    <p>Count: {{ counter.count }}</p>
    <button @click="counter.increment">Increment</button>
  </div>
</template>
```

---

## 7. Server Routes

### 7.1 API Routes

```typescript
// server/api/posts.get.ts
export default defineEventHandler(async (event) => {
  return [
    { id: 1, title: "Post 1" },
    { id: 2, title: "Post 2" },
  ];
});
```

```typescript
// server/api/posts/[id].get.ts
export default defineEventHandler(async (event) => {
  const id = getRouterParam(event, "id");
  return { id, title: `Post ${id}` };
});
```

```typescript
// server/api/posts.post.ts
export default defineEventHandler(async (event) => {
  const body = await readBody(event);
  // Save to database
  return { success: true, post: body };
});
```

### 7.2 Server Middleware

```typescript
// server/middleware/auth.ts
export default defineEventHandler((event) => {
  const token = getHeader(event, "authorization");

  if (!token) {
    throw createError({
      statusCode: 401,
      message: "Unauthorized",
    });
  }
});
```

### 7.3 Server Utils

```typescript
// server/utils/db.ts
export const getUser = async (id: number) => {
  // Database query
  return { id, name: "John" };
};
```

```typescript
// server/api/users/[id].get.ts
export default defineEventHandler(async (event) => {
  const id = getRouterParam(event, "id");
  const user = await getUser(Number(id));
  return user;
});
```

---

## 8. Modules and Plugins

### 8.1 Nuxt Modules

```bash
# Popular modules
npm install @nuxtjs/tailwindcss
npm install @pinia/nuxt
npm install @nuxt/image
npm install @nuxtjs/i18n
```

```typescript
// nuxt.config.ts
export default defineNuxtConfig({
  modules: [
    "@nuxtjs/tailwindcss",
    "@pinia/nuxt",
    "@nuxt/image",
    "@nuxtjs/i18n",
  ],
});
```

### 8.2 Plugins

```typescript
// plugins/api.ts
export default defineNuxtPlugin(() => {
  const api = $fetch.create({
    baseURL: "https://api.example.com",
    headers: {
      Authorization: `Bearer ${token}`,
    },
  });

  return {
    provide: {
      api,
    },
  };
});
```

```vue
<script setup>
const { $api } = useNuxtApp();

const data = await $api("/posts");
</script>
```

### 8.3 Auto Imports

Nuxt automatically imports:

- Components from `components/`
- Composables from `composables/`
- Utils from `utils/`
- Vue APIs (ref, computed, etc.)
- Nuxt APIs (useFetch, navigateTo, etc.)

```vue
<!-- No imports needed! -->
<script setup>
const count = ref(0); // Auto-imported from Vue
const route = useRoute(); // Auto-imported from Nuxt
</script>

<template>
  <MyComponent />
  <!-- Auto-imported from components/ -->
</template>
```

---

## 9. SEO and Meta

### 9.1 useHead

```vue
<script setup>
useHead({
  title: "My Page Title",
  meta: [
    { name: "description", content: "Page description" },
    { property: "og:title", content: "My Page Title" },
    { property: "og:image", content: "/image.jpg" },
  ],
  link: [{ rel: "canonical", href: "https://example.com/page" }],
  script: [{ src: "https://example.com/script.js", async: true }],
});
</script>
```

### 9.2 useSeoMeta

```vue
<script setup>
useSeoMeta({
  title: "My Page",
  description: "Page description",
  ogTitle: "My Page",
  ogDescription: "Page description",
  ogImage: "/image.jpg",
  twitterCard: "summary_large_image",
});
</script>
```

### 9.3 Dynamic Meta Tags

```vue
<script setup>
const { data: post } = await useFetch(`/api/posts/${route.params.id}`);

useHead({
  title: () => post.value?.title,
  meta: [{ name: "description", content: () => post.value?.excerpt }],
});
</script>
```

---

## 10. Deployment

### 10.1 Build for Production

```bash
# Build for production
npm run build

# Preview production build
npm run preview

# Generate static site
npm run generate
```

### 10.2 Deployment Platforms

#### Vercel

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

#### Netlify

```bash
# Build command
npm run generate

# Publish directory
.output/public
```

#### Node.js Server

```bash
# Build
npm run build

# Start production server
node .output/server/index.mjs
```

---

## 11. Nuxt Interview Questions

### 11.1 Fundamental Questions

**Q: What is Nuxt.js?**
A: Nuxt.js is a meta-framework built on Vue.js that provides SSR, SSG, file-based routing, and other features for building production-ready applications.

**Q: What are the rendering modes in Nuxt?**
A: Universal (SSR), Client-Side Rendering (CSR), Static Site Generation (SSG), and Hybrid rendering.

**Q: What is the difference between useFetch and useAsyncData?**
A: `useFetch` is a wrapper around `useAsyncData` and `$fetch` for simpler API calls. `useAsyncData` is more flexible and allows custom fetcher functions.

**Q: What is file-based routing?**
A: Automatic route generation based on file structure in the `pages/` directory. Each file becomes a route.

**Q: What is the purpose of layouts?**
A: Layouts provide reusable page structures. They wrap page components and can be switched dynamically.

**Q: What are Nuxt modules?**
A: Reusable extensions that add functionality to Nuxt applications. Examples: Tailwind, Pinia, i18n.

**Q: What is useState in Nuxt?**
A: A composable for creating SSR-friendly shared state across components.

**Q: What are server routes?**
A: API endpoints defined in the `server/api/` directory that run on the server.

**Q: What is the difference between SSR and SSG?**
A: SSR renders pages on each request, SSG pre-renders pages at build time.

**Q: What is middleware in Nuxt?**
A: Functions that run before rendering a page or group of pages, used for authentication, authorization, etc.

### 11.2 Advanced Questions

**Q: How does Nuxt handle SEO?**
A: Through `useHead`, `useSeoMeta`, and SSR/SSG rendering modes that provide fully rendered HTML to search engines.

**Q: What is hybrid rendering?**
A: Mixing different rendering strategies (SSR, SSG, CSR) for different routes in the same application.

**Q: How do you handle authentication in Nuxt?**
A: Using middleware, composables, and server routes. Store tokens in cookies (httpOnly), protect routes with middleware, and use server-side validation.

**Q: What is the purpose of the server directory?**
A: Contains server-side code including API routes, middleware, and utilities that run on the server.

**Q: How do you optimize Nuxt performance?**
A: Lazy loading, code splitting, image optimization, caching, ISR, proper data fetching, and production builds.

**Q: What is the difference between plugins and modules?**
A: Plugins extend the Vue app instance and run on both client and server. Modules extend Nuxt itself at build time.

**Q: How do you handle environment variables?**
A: Using `runtimeConfig` in `nuxt.config.ts`. Private keys are server-only, public keys are exposed to client.

**Q: What is Nitro?**
A: Nuxt's server engine that provides API routes, server middleware, and deployment presets for various platforms.

**Q: How do you implement i18n in Nuxt?**
A: Using `@nuxtjs/i18n` module for internationalization with automatic route generation and locale switching.

**Q: What are route rules?**
A: Configuration for individual routes to set rendering mode, caching, redirects, and other behaviors.

### 11.3 Practical Questions

**Q: How do you fetch data in Nuxt?**
A: Using `useFetch`, `useAsyncData`, `useLazyFetch`, or `$fetch` depending on the use case.

**Q: How do you create dynamic routes?**
A: Using square brackets in file names: `[id].vue` for `/posts/:id`.

**Q: How do you protect routes?**
A: Using middleware with `definePageMeta` and checking authentication state.

**Q: How do you handle forms in Nuxt?**
A: Using `v-model`, handling submit events, validating data, and sending to API routes.

**Q: How do you implement pagination?**
A: Using query parameters, watching them with `useFetch`, and updating the URL with `navigateTo`.

**Q: How do you handle errors in Nuxt?**
A: Using error pages (`error.vue`), `createError`, and error boundaries.

**Q: How do you add meta tags dynamically?**
A: Using `useHead` or `useSeoMeta` with reactive data from API calls.

**Q: How do you implement caching?**
A: Using route rules with `swr` (stale-while-revalidate) or `cache` options.

**Q: How do you create API routes?**
A: Creating files in `server/api/` directory with `defineEventHandler`.

**Q: How do you deploy a Nuxt app?**
A: Build with `npm run build` and deploy to platforms like Vercel, Netlify, or Node.js servers. For static sites, use `npm run generate`.

---

## Additional Resources

### Official Documentation

- [Vue.js Docs](https://vuejs.org)
- [Nuxt.js Docs](https://nuxt.com)
- [Vue Router Docs](https://router.vuejs.org)
- [Pinia Docs](https://pinia.vuejs.org)

### Tools

- **Volar** - VS Code extension for Vue 3
- **Vue DevTools** - Browser extension
- **Nuxt DevTools** - Built-in development tools

### Learning Resources

- Vue Mastery
- Vue School
- Nuxt.com Learn Section
- Official Vue/Nuxt YouTube Channels

### Popular Modules

- **@nuxtjs/tailwindcss** - Tailwind CSS integration
- **@nuxt/image** - Image optimization
- **@nuxtjs/i18n** - Internationalization
- **@vueuse/nuxt** - Collection of Vue composables
- **nuxt-icon** - Icon components

---

**Happy Coding with Vue & Nuxt! 🚀**

_These notes cover Vue.js 3.5 and Nuxt.js 4.2 concepts, features, and interview questions. Practice building projects to master Vue and Nuxt development._
