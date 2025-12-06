# Tailwind CSS v4 Master Notes By Deepak Modi

> Latest Version: Tailwind CSS v4.1.17 (2024) | Recommended: Tailwind CSS Official Docs

## Table of Contents

1. [Introduction to Tailwind CSS](#1-introduction-to-tailwind-css)

   - [1.1 What is Tailwind CSS?](#11-what-is-tailwind-css)
   - [1.2 Why Tailwind CSS?](#12-why-tailwind-css)
   - [1.3 Tailwind v4 New Features](#13-tailwind-v4-new-features)
   - [1.4 Tailwind vs Other CSS Frameworks](#14-tailwind-vs-other-css-frameworks)

2. [Installation and Setup](#2-installation-and-setup)

   - [2.1 Installation Methods](#21-installation-methods)
   - [2.2 Configuration](#22-configuration)
   - [2.3 Editor Setup](#23-editor-setup)
   - [2.4 Build Process](#24-build-process)

3. [Core Concepts](#3-core-concepts)

   - [3.1 Utility-First Approach](#31-utility-first-approach)
   - [3.2 Responsive Design](#32-responsive-design)
   - [3.3 State Variants](#33-state-variants)
   - [3.4 Dark Mode](#34-dark-mode)
   - [3.5 CSS Variables](#35-css-variables)

4. [Layout](#4-layout)

   - [4.1 Container](#41-container)
   - [4.2 Display](#42-display)
   - [4.3 Flexbox](#43-flexbox)
   - [4.4 Grid](#44-grid)
   - [4.5 Positioning](#45-positioning)
   - [4.6 Z-Index](#46-z-index)

5. [Spacing](#5-spacing)

   - [5.1 Padding](#51-padding)
   - [5.2 Margin](#52-margin)
   - [5.3 Space Between](#53-space-between)
   - [5.4 Custom Spacing](#54-custom-spacing)

6. [Typography](#6-typography)

   - [6.1 Font Family](#61-font-family)
   - [6.2 Font Size](#62-font-size)
   - [6.3 Font Weight](#63-font-weight)
   - [6.4 Text Color](#64-text-color)
   - [6.5 Text Alignment](#65-text-alignment)
   - [6.6 Line Height](#66-line-height)

7. [Colors and Backgrounds](#7-colors-and-backgrounds)

   - [7.1 Color Palette](#71-color-palette)
   - [7.2 Background Colors](#72-background-colors)
   - [7.3 Gradients](#73-gradients)
   - [7.4 Opacity](#74-opacity)
   - [7.5 Custom Colors](#75-custom-colors)

8. [Borders and Effects](#8-borders-and-effects)

   - [8.1 Border Width](#81-border-width)
   - [8.2 Border Color](#82-border-color)
   - [8.3 Border Radius](#83-border-radius)
   - [8.4 Shadows](#84-shadows)
   - [8.5 Blur Effects](#85-blur-effects)

9. [Animations and Transitions](#9-animations-and-transitions)

   - [9.1 Transitions](#91-transitions)
   - [9.2 Transforms](#92-transforms)
   - [9.3 Animations](#93-animations)
   - [9.4 Custom Animations](#94-custom-animations)

10. [Customization](#10-customization)

    - [10.1 Theme Configuration](#101-theme-configuration)
    - [10.2 Custom Utilities](#102-custom-utilities)
    - [10.3 Plugins](#103-plugins)
    - [10.4 Extending Tailwind](#104-extending-tailwind)

11. [Best Practices](#11-best-practices)

    - [11.1 Component Organization](#111-component-organization)
    - [11.2 Performance Optimization](#112-performance-optimization)
    - [11.3 Maintainability](#113-maintainability)
    - [11.4 Common Patterns](#114-common-patterns)

12. [Advanced Features](#12-advanced-features)

    - [12.1 Container Queries](#121-container-queries)
    - [12.2 Arbitrary Values](#122-arbitrary-values)
    - [12.3 Dynamic Classes](#123-dynamic-classes)
    - [12.4 CSS-in-JS Integration](#124-css-in-js-integration)

13. [Interview Questions](#13-interview-questions)
    - [13.1 Fundamental Questions](#131-fundamental-questions)
    - [13.2 Advanced Questions](#132-advanced-questions)
    - [13.3 Practical Questions](#133-practical-questions)

---

## 1. Introduction to Tailwind CSS

### 1.1 What is Tailwind CSS?

Tailwind CSS is a **utility-first CSS framework** that provides low-level utility classes to build custom designs without writing custom CSS. Instead of opinionated pre-designed components, Tailwind gives you the building blocks to create your own unique designs.

> **Key Point:** Tailwind CSS is not a UI kit or component library. It's a CSS framework that provides utility classes for building custom designs.

#### Core Philosophy

- **Utility-First:** Compose designs using utility classes
- **Responsive:** Mobile-first responsive design
- **Customizable:** Fully customizable with configuration
- **Modern:** Built for modern web development
- **Performance:** Optimized for production with PurgeCSS

#### Real-World Usage

Companies using Tailwind CSS: GitHub, Netflix, NASA, Shopify, OpenAI, Laravel, Vercel, Stripe

### 1.2 Why Tailwind CSS?

#### Advantages

1. **Rapid Development:** Build UIs faster with utility classes
2. **No Naming Conflicts:** No need to name classes or components
3. **Consistent Design:** Design system built-in with spacing, colors, etc.
4. **Responsive by Default:** Easy responsive design with breakpoint prefixes
5. **Small Bundle Size:** PurgeCSS removes unused styles
6. **Highly Customizable:** Configure everything via config file
7. **No Context Switching:** Write styles in your HTML/JSX
8. **Great Developer Experience:** IntelliSense, documentation

#### Disadvantages

1. **HTML Clutter:** Many classes can make HTML verbose
2. **Learning Curve:** Need to learn utility class names
3. **Repetition:** Similar patterns repeated across components
4. **Design Limitations:** Constrained to utility classes
5. **Build Step Required:** Needs compilation for production

#### When to Use Tailwind CSS

- Rapid prototyping
- Custom designs (not template-based)
- Projects requiring design consistency
- Teams wanting to avoid CSS maintenance
- Modern web applications

#### When NOT to Use Tailwind CSS

- Simple static websites (vanilla CSS might be enough)
- Projects with existing CSS architecture
- Teams unfamiliar with utility-first approach
- Projects requiring minimal build tooling

### 1.3 Tailwind v4 New Features

#### Major Updates in Tailwind CSS v4 (2024)

**1. New Engine (Oxide)**

- Complete rewrite in Rust
- Up to 10x faster build times
- Better performance and reliability
- Improved watch mode

**2. CSS-First Configuration**

- Configuration now in CSS using `@theme`
- No more JavaScript config file required
- Better IDE support and autocomplete
- More intuitive syntax

```css
@theme {
  --color-primary: #3b82f6;
  --font-family-sans: "Inter", system-ui, sans-serif;
  --spacing-xs: 0.5rem;
}
```

**3. Native Cascade Layers**

- Built-in support for CSS cascade layers
- Better specificity control
- Easier to override styles
- More predictable styling

**4. Container Queries**

- Native container query support
- No plugin required
- Better responsive components
- More flexible layouts

**5. Improved Dark Mode**

- Better dark mode implementation
- More flexible color schemes
- Automatic color adjustments
- Enhanced contrast support

**6. Simplified Imports**

- Single CSS import
- No PostCSS config needed (optional)
- Faster setup
- Better DX

**7. Enhanced Performance**

- Faster compilation
- Smaller output CSS
- Better tree-shaking
- Optimized for modern browsers

**8. Better TypeScript Support**

- Full TypeScript support
- Type-safe configuration
- Better IDE integration
- Enhanced autocomplete

**9. Automatic Content Detection**

- No need to configure content paths
- Automatic file scanning
- Better detection algorithms
- Fewer configuration errors

**10. Improved Gradients**

- More gradient utilities
- Better color stops
- Easier gradient creation
- Enhanced visual effects

### 1.4 Tailwind vs Other CSS Frameworks

| Feature             | Tailwind CSS    | Bootstrap       | Material-UI     | Bulma           |
| ------------------- | --------------- | --------------- | --------------- | --------------- |
| Approach            | Utility-first   | Component-based | Component-based | Component-based |
| Customization       | Highly flexible | Limited         | Moderate        | Moderate        |
| Bundle Size         | Very small\*    | Large           | Large           | Medium          |
| Learning Curve      | Moderate        | Easy            | Moderate        | Easy            |
| Design Freedom      | Complete        | Limited         | Limited         | Limited         |
| JavaScript Required | No              | Yes (optional)  | Yes             | No              |
| Build Step          | Required        | Optional        | Required        | Optional        |
| Responsive          | Mobile-first    | Mobile-first    | Desktop-first   | Mobile-first    |
| Dark Mode           | Built-in        | Manual          | Built-in        | Manual          |
| Community           | Large           | Huge            | Large           | Medium          |

_\*After PurgeCSS removes unused styles_

---

## 2. Installation and Setup

### 2.1 Installation Methods

#### Method 1: Using npm/yarn (Recommended)

```bash
# Install Tailwind CSS
npm install -D tailwindcss

# Initialize Tailwind
npx tailwindcss init
```

#### Method 2: Using CDN (Development Only)

```html
<!-- Not recommended for production -->
<script src="https://cdn.tailwindcss.com"></script>
```

#### Method 3: With Frameworks

**Next.js:**

```bash
npx create-next-app@latest my-app
# Select Tailwind CSS during setup
```

**Vite:**

```bash
npm create vite@latest my-app
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

**Create React App:**

```bash
npx create-react-app my-app
npm install -D tailwindcss
npx tailwindcss init
```

### 2.2 Configuration

#### Tailwind v4 CSS Configuration

```css
/* app.css */
@import "tailwindcss";

@theme {
  /* Colors */
  --color-primary: #3b82f6;
  --color-secondary: #8b5cf6;
  --color-accent: #f59e0b;

  /* Fonts */
  --font-family-sans: "Inter", system-ui, sans-serif;
  --font-family-mono: "Fira Code", monospace;

  /* Spacing */
  --spacing-xs: 0.5rem;
  --spacing-sm: 1rem;
  --spacing-md: 1.5rem;
  --spacing-lg: 2rem;
  --spacing-xl: 3rem;

  /* Breakpoints */
  --breakpoint-sm: 640px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 1024px;
  --breakpoint-xl: 1280px;
  --breakpoint-2xl: 1536px;
}

/* Custom utilities */
@utility btn {
  padding: 0.5rem 1rem;
  border-radius: 0.375rem;
  font-weight: 500;
  transition: all 0.2s;
}
```

#### Legacy JavaScript Configuration (v3 style)

```javascript
// tailwind.config.js (still supported)
module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx}", "./public/index.html"],
  theme: {
    extend: {
      colors: {
        primary: "#3b82f6",
        secondary: "#8b5cf6",
      },
      fontFamily: {
        sans: ["Inter", "system-ui", "sans-serif"],
      },
    },
  },
  plugins: [],
};
```

### 2.3 Editor Setup

#### VS Code Extensions

1. **Tailwind CSS IntelliSense** (Essential)

   - Autocomplete
   - Syntax highlighting
   - Linting

2. **PostCSS Language Support**

   - CSS syntax support
   - Better highlighting

3. **Headwind** (Optional)
   - Automatic class sorting
   - Better organization

#### VS Code Settings

```json
{
  "tailwindCSS.experimental.classRegex": [
    ["cva\\(([^)]*)\\)", "[\"'`]([^\"'`]*).*?[\"'`]"],
    ["cx\\(([^)]*)\\)", "(?:'|\"|`)([^']*)(?:'|\"|`)"]
  ],
  "editor.quickSuggestions": {
    "strings": true
  }
}
```

### 2.4 Build Process

#### Development Build

```bash
# Watch mode
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch

# With minification
npx tailwindcss -i ./src/input.css -o ./dist/output.css --minify
```

#### Production Build

```bash
# Optimized build
npx tailwindcss -i ./src/input.css -o ./dist/output.css --minify

# With content paths
npx tailwindcss -i ./src/input.css -o ./dist/output.css --content './src/**/*.{html,js}'
```

#### Package.json Scripts

```json
{
  "scripts": {
    "dev": "tailwindcss -i ./src/input.css -o ./dist/output.css --watch",
    "build": "tailwindcss -i ./src/input.css -o ./dist/output.css --minify"
  }
}
```

---

## 3. Core Concepts

### 3.1 Utility-First Approach

Instead of writing custom CSS, you compose designs using utility classes.

#### Traditional CSS Approach

```css
.button {
  padding: 0.5rem 1rem;
  background-color: #3b82f6;
  color: white;
  border-radius: 0.375rem;
  font-weight: 500;
}

.button:hover {
  background-color: #2563eb;
}
```

```html
<button class="button">Click me</button>
```

#### Tailwind Utility-First Approach

```html
<button
  class="px-4 py-2 bg-blue-500 text-white rounded-md font-medium hover:bg-blue-600"
>
  Click me
</button>
```

#### Benefits

- No naming classes
- No context switching
- Easier to maintain
- Faster development
- Consistent design

### 3.2 Responsive Design

Tailwind uses a mobile-first breakpoint system.

#### Breakpoints

| Prefix | Min Width | CSS                          |
| ------ | --------- | ---------------------------- |
| `sm:`  | 640px     | `@media (min-width: 640px)`  |
| `md:`  | 768px     | `@media (min-width: 768px)`  |
| `lg:`  | 1024px    | `@media (min-width: 1024px)` |
| `xl:`  | 1280px    | `@media (min-width: 1280px)` |
| `2xl:` | 1536px    | `@media (min-width: 1536px)` |

#### Responsive Example

```html
<!-- Stack on mobile, grid on larger screens -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Different text sizes -->
<h1 class="text-2xl md:text-4xl lg:text-6xl">Responsive Heading</h1>

<!-- Hide on mobile, show on desktop -->
<div class="hidden md:block">Desktop only content</div>

<!-- Show on mobile, hide on desktop -->
<div class="block md:hidden">Mobile only content</div>
```

### 3.3 State Variants

Tailwind provides variants for different states.

#### Hover, Focus, Active

```html
<!-- Hover -->
<button class="bg-blue-500 hover:bg-blue-600">Hover me</button>

<!-- Focus -->
<input
  class="border-gray-300 focus:border-blue-500 focus:ring-2 focus:ring-blue-200"
/>

<!-- Active -->
<button class="bg-blue-500 active:bg-blue-700">Click me</button>

<!-- Disabled -->
<button
  class="bg-blue-500 disabled:bg-gray-300 disabled:cursor-not-allowed"
  disabled
>
  Disabled
</button>
```

#### Group Hover

```html
<div class="group">
  <img class="group-hover:scale-110 transition" src="image.jpg" />
  <p class="group-hover:text-blue-500">Hover the parent</p>
</div>
```

#### Peer State

```html
<input type="checkbox" class="peer" />
<label class="peer-checked:text-blue-500">Checkbox label</label>
```

### 3.4 Dark Mode

Tailwind v4 has improved dark mode support.

#### Enable Dark Mode

```css
@theme {
  --color-scheme: light dark;
}
```

#### Dark Mode Classes

```html
<!-- Light mode: white background, dark mode: gray background -->
<div class="bg-white dark:bg-gray-900">
  <h1 class="text-gray-900 dark:text-white">Hello World</h1>
  <p class="text-gray-600 dark:text-gray-300">Description text</p>
</div>

<!-- Dark mode button -->
<button class="bg-blue-500 dark:bg-blue-600 text-white">Click me</button>
```

#### Manual Dark Mode Toggle

```html
<html class="dark">
  <!-- Dark mode enabled -->
</html>
```

```javascript
// Toggle dark mode
document.documentElement.classList.toggle("dark");
```

### 3.5 CSS Variables

Tailwind v4 uses CSS variables extensively.

#### Using CSS Variables

```css
@theme {
  --color-brand: #3b82f6;
  --spacing-section: 4rem;
}
```

```html
<div class="bg-[--color-brand] p-[--spacing-section]">Custom values</div>
```

#### Dynamic Variables

```html
<div style="--dynamic-color: #ff0000" class="bg-[--dynamic-color]">
  Dynamic color
</div>
```

---

## 4. Layout

### 4.1 Container

Centers content with max-width.

```html
<!-- Responsive container -->
<div class="container mx-auto px-4">Content</div>

<!-- Full width container -->
<div class="container-fluid">Full width content</div>
```

### 4.2 Display

```html
<!-- Block -->
<div class="block">Block element</div>

<!-- Inline -->
<span class="inline">Inline element</span>

<!-- Inline-block -->
<div class="inline-block">Inline-block</div>

<!-- Flex -->
<div class="flex">Flex container</div>

<!-- Grid -->
<div class="grid">Grid container</div>

<!-- Hidden -->
<div class="hidden">Hidden element</div>
```

### 4.3 Flexbox

```html
<!-- Basic flex -->
<div class="flex">
  <div>Item 1</div>
  <div>Item 2</div>
</div>

<!-- Flex direction -->
<div class="flex flex-col">Column</div>
<div class="flex flex-row">Row</div>
<div class="flex flex-row-reverse">Row reverse</div>

<!-- Justify content -->
<div class="flex justify-start">Start</div>
<div class="flex justify-center">Center</div>
<div class="flex justify-between">Space between</div>
<div class="flex justify-around">Space around</div>
<div class="flex justify-evenly">Space evenly</div>

<!-- Align items -->
<div class="flex items-start">Start</div>
<div class="flex items-center">Center</div>
<div class="flex items-end">End</div>
<div class="flex items-stretch">Stretch</div>

<!-- Flex wrap -->
<div class="flex flex-wrap">Wrap</div>
<div class="flex flex-nowrap">No wrap</div>

<!-- Flex grow/shrink -->
<div class="flex">
  <div class="flex-1">Grow</div>
  <div class="flex-none">No grow</div>
</div>

<!-- Gap -->
<div class="flex gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

### 4.4 Grid

```html
<!-- Basic grid -->
<div class="grid grid-cols-3 gap-4">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>

<!-- Responsive grid -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
  <div>Item</div>
</div>

<!-- Grid template columns -->
<div class="grid grid-cols-[200px_1fr_200px]">
  <div>Sidebar</div>
  <div>Content</div>
  <div>Sidebar</div>
</div>

<!-- Grid span -->
<div class="grid grid-cols-3">
  <div class="col-span-2">Spans 2 columns</div>
  <div>1 column</div>
</div>

<!-- Grid auto-fit -->
<div class="grid grid-cols-[repeat(auto-fit,minmax(200px,1fr))] gap-4">
  <div>Auto-fit items</div>
</div>
```

### 4.5 Positioning

```html
<!-- Static (default) -->
<div class="static">Static</div>

<!-- Relative -->
<div class="relative">
  <div class="absolute top-0 right-0">Absolute child</div>
</div>

<!-- Fixed -->
<div class="fixed top-0 left-0 right-0">Fixed header</div>

<!-- Sticky -->
<div class="sticky top-0">Sticky header</div>

<!-- Absolute positioning -->
<div class="absolute top-4 right-4">Top right</div>
<div class="absolute bottom-4 left-4">Bottom left</div>

<!-- Center with absolute -->
<div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2">
  Centered
</div>

<!-- Inset -->
<div class="absolute inset-0">Full coverage</div>
<div class="absolute inset-x-0">Horizontal coverage</div>
<div class="absolute inset-y-0">Vertical coverage</div>
```

### 4.6 Z-Index

```html
<!-- Z-index values -->
<div class="z-0">z-0</div>
<div class="z-10">z-10</div>
<div class="z-20">z-20</div>
<div class="z-30">z-30</div>
<div class="z-40">z-40</div>
<div class="z-50">z-50</div>
<div class="z-auto">z-auto</div>

<!-- Negative z-index -->
<div class="-z-10">Behind</div>
```

---

## 5. Spacing

### 5.1 Padding

```html
<!-- All sides -->
<div class="p-4">Padding all sides</div>

<!-- Specific sides -->
<div class="pt-4">Padding top</div>
<div class="pr-4">Padding right</div>
<div class="pb-4">Padding bottom</div>
<div class="pl-4">Padding left</div>

<!-- Horizontal/Vertical -->
<div class="px-4">Padding horizontal</div>
<div class="py-4">Padding vertical</div>

<!-- Responsive padding -->
<div class="p-2 md:p-4 lg:p-8">Responsive padding</div>

<!-- Spacing scale -->
<!-- 0, 0.5, 1, 1.5, 2, 2.5, 3, 3.5, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 16, 20, 24, 28, 32, 36, 40, 44, 48, 52, 56, 60, 64, 72, 80, 96 -->
```

### 5.2 Margin

```html
<!-- All sides -->
<div class="m-4">Margin all sides</div>

<!-- Specific sides -->
<div class="mt-4">Margin top</div>
<div class="mr-4">Margin right</div>
<div class="mb-4">Margin bottom</div>
<div class="ml-4">Margin left</div>

<!-- Horizontal/Vertical -->
<div class="mx-4">Margin horizontal</div>
<div class="my-4">Margin vertical</div>

<!-- Auto margin (centering) -->
<div class="mx-auto">Centered</div>

<!-- Negative margin -->
<div class="-mt-4">Negative margin top</div>
<div class="-mx-4">Negative margin horizontal</div>
```

### 5.3 Space Between

```html
<!-- Horizontal space -->
<div class="flex space-x-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Vertical space -->
<div class="flex flex-col space-y-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Reverse space -->
<div class="flex flex-row-reverse space-x-reverse space-x-4">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

### 5.4 Custom Spacing

```css
@theme {
  --spacing-xs: 0.5rem;
  --spacing-sm: 1rem;
  --spacing-md: 1.5rem;
  --spacing-lg: 2rem;
  --spacing-xl: 3rem;
}
```

```html
<div class="p-[--spacing-lg]">Custom spacing</div>

<!-- Arbitrary values -->
<div class="p-[17px]">Exact 17px padding</div>
<div class="m-[2.5rem]">Exact 2.5rem margin</div>
```

---

## 6. Typography

### 6.1 Font Family

```html
<!-- Sans-serif (default) -->
<p class="font-sans">Sans-serif text</p>

<!-- Serif -->
<p class="font-serif">Serif text</p>

<!-- Monospace -->
<code class="font-mono">Monospace code</code>

<!-- Custom font -->
<p class="font-[Inter]">Custom font</p>
```

### 6.2 Font Size

```html
<!-- Text sizes -->
<p class="text-xs">Extra small</p>
<p class="text-sm">Small</p>
<p class="text-base">Base (default)</p>
<p class="text-lg">Large</p>
<p class="text-xl">Extra large</p>
<p class="text-2xl">2XL</p>
<p class="text-3xl">3XL</p>
<p class="text-4xl">4XL</p>
<p class="text-5xl">5XL</p>
<p class="text-6xl">6XL</p>
<p class="text-7xl">7XL</p>
<p class="text-8xl">8XL</p>
<p class="text-9xl">9XL</p>

<!-- Responsive text -->
<h1 class="text-2xl md:text-4xl lg:text-6xl">Responsive heading</h1>

<!-- Arbitrary value -->
<p class="text-[17px]">Exact 17px</p>
```

### 6.3 Font Weight

```html
<p class="font-thin">Thin (100)</p>
<p class="font-extralight">Extra light (200)</p>
<p class="font-light">Light (300)</p>
<p class="font-normal">Normal (400)</p>
<p class="font-medium">Medium (500)</p>
<p class="font-semibold">Semibold (600)</p>
<p class="font-bold">Bold (700)</p>
<p class="font-extrabold">Extra bold (800)</p>
<p class="font-black">Black (900)</p>
```

### 6.4 Text Color

```html
<!-- Color scale (50-950) -->
<p class="text-gray-500">Gray text</p>
<p class="text-red-500">Red text</p>
<p class="text-blue-500">Blue text</p>
<p class="text-green-500">Green text</p>

<!-- Opacity -->
<p class="text-blue-500/50">50% opacity</p>
<p class="text-blue-500/75">75% opacity</p>

<!-- Dark mode -->
<p class="text-gray-900 dark:text-white">Dark mode text</p>

<!-- Arbitrary color -->
<p class="text-[#ff0000]">Custom color</p>
```

### 6.5 Text Alignment

```html
<p class="text-left">Left aligned</p>
<p class="text-center">Center aligned</p>
<p class="text-right">Right aligned</p>
<p class="text-justify">Justified</p>

<!-- Vertical alignment -->
<span class="align-baseline">Baseline</span>
<span class="align-top">Top</span>
<span class="align-middle">Middle</span>
<span class="align-bottom">Bottom</span>
```

### 6.6 Line Height

```html
<p class="leading-none">No line height</p>
<p class="leading-tight">Tight</p>
<p class="leading-snug">Snug</p>
<p class="leading-normal">Normal</p>
<p class="leading-relaxed">Relaxed</p>
<p class="leading-loose">Loose</p>

<!-- Numeric values -->
<p class="leading-3">0.75rem</p>
<p class="leading-10">2.5rem</p>

<!-- Arbitrary value -->
<p class="leading-[3rem]">Custom line height</p>
```

---

## 7. Colors and Backgrounds

### 7.1 Color Palette

Tailwind v4 includes a comprehensive color palette:

**Color Scales:** 50, 100, 200, 300, 400, 500, 600, 700, 800, 900, 950

**Colors:**

- Gray, Slate, Zinc, Neutral, Stone
- Red, Orange, Amber, Yellow, Lime, Green, Emerald, Teal, Cyan
- Sky, Blue, Indigo, Violet, Purple, Fuchsia, Pink, Rose

### 7.2 Background Colors

```html
<!-- Solid backgrounds -->
<div class="bg-blue-500">Blue background</div>
<div class="bg-red-500">Red background</div>

<!-- Opacity -->
<div class="bg-blue-500/50">50% opacity</div>

<!-- Dark mode -->
<div class="bg-white dark:bg-gray-900">Dark mode background</div>

<!-- Hover state -->
<div class="bg-blue-500 hover:bg-blue-600">Hover background</div>

<!-- Arbitrary color -->
<div class="bg-[#ff0000]">Custom background</div>
```

### 7.3 Gradients

```html
<!-- Linear gradients -->
<div class="bg-gradient-to-r from-blue-500 to-purple-500">
  Left to right gradient
</div>

<div class="bg-gradient-to-b from-blue-500 to-purple-500">
  Top to bottom gradient
</div>

<!-- Gradient directions -->
<div class="bg-gradient-to-t">To top</div>
<div class="bg-gradient-to-tr">To top right</div>
<div class="bg-gradient-to-r">To right</div>
<div class="bg-gradient-to-br">To bottom right</div>
<div class="bg-gradient-to-b">To bottom</div>
<div class="bg-gradient-to-bl">To bottom left</div>
<div class="bg-gradient-to-l">To left</div>
<div class="bg-gradient-to-tl">To top left</div>

<!-- Multiple color stops -->
<div class="bg-gradient-to-r from-red-500 via-yellow-500 to-green-500">
  Three color gradient
</div>

<!-- Gradient with opacity -->
<div class="bg-gradient-to-r from-blue-500/50 to-purple-500/50">
  Transparent gradient
</div>
```

### 7.4 Opacity

```html
<!-- Background opacity -->
<div class="bg-blue-500 bg-opacity-50">50% opacity</div>

<!-- Text opacity -->
<p class="text-blue-500 text-opacity-75">75% opacity</p>

<!-- Element opacity -->
<div class="opacity-0">Invisible</div>
<div class="opacity-50">Half visible</div>
<div class="opacity-100">Fully visible</div>

<!-- Hover opacity -->
<div class="opacity-50 hover:opacity-100">Fade in on hover</div>
```

### 7.5 Custom Colors

```css
@theme {
  --color-brand-primary: #3b82f6;
  --color-brand-secondary: #8b5cf6;
  --color-brand-accent: #f59e0b;
}
```

```html
<div class="bg-[--color-brand-primary]">Custom brand color</div>
```

---

## 8. Borders and Effects

### 8.1 Border Width

```html
<!-- Border all sides -->
<div class="border">1px border</div>
<div class="border-2">2px border</div>
<div class="border-4">4px border</div>
<div class="border-8">8px border</div>

<!-- Specific sides -->
<div class="border-t">Top border</div>
<div class="border-r">Right border</div>
<div class="border-b">Bottom border</div>
<div class="border-l">Left border</div>

<!-- Horizontal/Vertical -->
<div class="border-x">Horizontal borders</div>
<div class="border-y">Vertical borders</div>

<!-- No border -->
<div class="border-0">No border</div>
```

### 8.2 Border Color

```html
<!-- Solid border color -->
<div class="border border-blue-500">Blue border</div>

<!-- Opacity -->
<div class="border border-blue-500/50">50% opacity</div>

<!-- Dark mode -->
<div class="border border-gray-300 dark:border-gray-700">Dark mode border</div>

<!-- Hover state -->
<div class="border border-gray-300 hover:border-blue-500">Hover border</div>
```

### 8.3 Border Radius

```html
<!-- All corners -->
<div class="rounded-none">No radius</div>
<div class="rounded-sm">Small radius</div>
<div class="rounded">Default radius</div>
<div class="rounded-md">Medium radius</div>
<div class="rounded-lg">Large radius</div>
<div class="rounded-xl">Extra large radius</div>
<div class="rounded-2xl">2XL radius</div>
<div class="rounded-3xl">3XL radius</div>
<div class="rounded-full">Full radius (circle/pill)</div>

<!-- Specific corners -->
<div class="rounded-t-lg">Top corners</div>
<div class="rounded-r-lg">Right corners</div>
<div class="rounded-b-lg">Bottom corners</div>
<div class="rounded-l-lg">Left corners</div>

<!-- Individual corners -->
<div class="rounded-tl-lg">Top left</div>
<div class="rounded-tr-lg">Top right</div>
<div class="rounded-br-lg">Bottom right</div>
<div class="rounded-bl-lg">Bottom left</div>
```

### 8.4 Shadows

```html
<!-- Box shadows -->
<div class="shadow-sm">Small shadow</div>
<div class="shadow">Default shadow</div>
<div class="shadow-md">Medium shadow</div>
<div class="shadow-lg">Large shadow</div>
<div class="shadow-xl">Extra large shadow</div>
<div class="shadow-2xl">2XL shadow</div>

<!-- Inner shadow -->
<div class="shadow-inner">Inner shadow</div>

<!-- No shadow -->
<div class="shadow-none">No shadow</div>

<!-- Colored shadows -->
<div class="shadow-lg shadow-blue-500/50">Colored shadow</div>

<!-- Hover shadow -->
<div class="shadow hover:shadow-lg transition">Hover shadow</div>
```

### 8.5 Blur Effects

```html
<!-- Blur -->
<div class="blur-none">No blur</div>
<div class="blur-sm">Small blur</div>
<div class="blur">Default blur</div>
<div class="blur-md">Medium blur</div>
<div class="blur-lg">Large blur</div>
<div class="blur-xl">Extra large blur</div>
<div class="blur-2xl">2XL blur</div>
<div class="blur-3xl">3XL blur</div>

<!-- Backdrop blur -->
<div class="backdrop-blur-sm">Backdrop blur</div>
<div class="backdrop-blur-md">Medium backdrop blur</div>

<!-- Backdrop filters -->
<div class="backdrop-brightness-50">Darken backdrop</div>
<div class="backdrop-contrast-125">Increase contrast</div>
<div class="backdrop-saturate-150">Saturate backdrop</div>
```

---

## 9. Animations and Transitions

### 9.1 Transitions

```html
<!-- Transition property -->
<div class="transition">All properties</div>
<div class="transition-colors">Colors only</div>
<div class="transition-opacity">Opacity only</div>
<div class="transition-shadow">Shadow only</div>
<div class="transition-transform">Transform only</div>

<!-- Duration -->
<div class="transition duration-75">75ms</div>
<div class="transition duration-100">100ms</div>
<div class="transition duration-150">150ms</div>
<div class="transition duration-200">200ms</div>
<div class="transition duration-300">300ms</div>
<div class="transition duration-500">500ms</div>
<div class="transition duration-700">700ms</div>
<div class="transition duration-1000">1000ms</div>

<!-- Timing function -->
<div class="transition ease-linear">Linear</div>
<div class="transition ease-in">Ease in</div>
<div class="transition ease-out">Ease out</div>
<div class="transition ease-in-out">Ease in-out</div>

<!-- Delay -->
<div class="transition delay-75">75ms delay</div>
<div class="transition delay-150">150ms delay</div>

<!-- Example: Hover transition -->
<button class="bg-blue-500 hover:bg-blue-600 transition duration-300">
  Hover me
</button>
```

### 9.2 Transforms

```html
<!-- Scale -->
<div class="scale-50">50% scale</div>
<div class="scale-100">100% scale</div>
<div class="scale-150">150% scale</div>
<div class="hover:scale-110 transition">Scale on hover</div>

<!-- Rotate -->
<div class="rotate-45">45deg rotation</div>
<div class="rotate-90">90deg rotation</div>
<div class="rotate-180">180deg rotation</div>
<div class="-rotate-45">-45deg rotation</div>

<!-- Translate -->
<div class="translate-x-4">Translate X</div>
<div class="translate-y-4">Translate Y</div>
<div class="-translate-x-1/2">-50% X (centering)</div>

<!-- Skew -->
<div class="skew-x-12">Skew X</div>
<div class="skew-y-6">Skew Y</div>

<!-- Transform origin -->
<div class="origin-center">Center origin</div>
<div class="origin-top-left">Top left origin</div>

<!-- Combined transforms -->
<div class="hover:scale-110 hover:rotate-3 transition">Multiple transforms</div>
```

### 9.3 Animations

```html
<!-- Built-in animations -->
<div class="animate-spin">Spinning</div>
<div class="animate-ping">Pinging</div>
<div class="animate-pulse">Pulsing</div>
<div class="animate-bounce">Bouncing</div>

<!-- Loading spinner -->
<div
  class="animate-spin h-8 w-8 border-4 border-blue-500 border-t-transparent rounded-full"
></div>

<!-- Pulse notification -->
<div class="relative">
  <span
    class="absolute top-0 right-0 h-3 w-3 bg-red-500 rounded-full animate-ping"
  ></span>
  <span class="absolute top-0 right-0 h-3 w-3 bg-red-500 rounded-full"></span>
</div>
```

### 9.4 Custom Animations

```css
@theme {
  --animate-fade-in: fade-in 0.5s ease-in;
}

@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
```

```html
<div class="animate-[fade-in_0.5s_ease-in]">Fade in animation</div>
```

---

## 10. Customization

### 10.1 Theme Configuration

```css
@theme {
  /* Colors */
  --color-primary: #3b82f6;
  --color-secondary: #8b5cf6;
  --color-success: #10b981;
  --color-warning: #f59e0b;
  --color-danger: #ef4444;

  /* Typography */
  --font-family-sans: "Inter", system-ui, sans-serif;
  --font-family-serif: "Georgia", serif;
  --font-family-mono: "Fira Code", monospace;

  /* Spacing */
  --spacing-xs: 0.5rem;
  --spacing-sm: 1rem;
  --spacing-md: 1.5rem;
  --spacing-lg: 2rem;
  --spacing-xl: 3rem;
  --spacing-2xl: 4rem;

  /* Breakpoints */
  --breakpoint-sm: 640px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 1024px;
  --breakpoint-xl: 1280px;
  --breakpoint-2xl: 1536px;

  /* Border radius */
  --radius-sm: 0.25rem;
  --radius-md: 0.375rem;
  --radius-lg: 0.5rem;
  --radius-xl: 0.75rem;

  /* Shadows */
  --shadow-sm: 0 1px 2px 0 rgb(0 0 0 / 0.05);
  --shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.1);
  --shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.1);
}
```

### 10.2 Custom Utilities

```css
@utility btn {
  padding: 0.5rem 1rem;
  border-radius: 0.375rem;
  font-weight: 500;
  transition: all 0.2s;
}

@utility btn-primary {
  background-color: var(--color-primary);
  color: white;
}

@utility btn-primary:hover {
  background-color: var(--color-primary-dark);
}

@utility card {
  padding: 1.5rem;
  border-radius: 0.5rem;
  background-color: white;
  box-shadow: var(--shadow-md);
}
```

```html
<button class="btn btn-primary">Custom button</button>
<div class="card">Custom card</div>
```

### 10.3 Plugins

#### Official Plugins

```bash
# Forms plugin
npm install @tailwindcss/forms

# Typography plugin
npm install @tailwindcss/typography

# Aspect ratio plugin
npm install @tailwindcss/aspect-ratio

# Container queries plugin
npm install @tailwindcss/container-queries
```

#### Using Plugins

```javascript
// tailwind.config.js
module.exports = {
  plugins: [
    require("@tailwindcss/forms"),
    require("@tailwindcss/typography"),
    require("@tailwindcss/aspect-ratio"),
    require("@tailwindcss/container-queries"),
  ],
};
```

### 10.4 Extending Tailwind

```css
@theme {
  /* Add custom colors */
  --color-brand: #ff6b6b;
  --color-accent: #4ecdc4;

  /* Add custom spacing */
  --spacing-128: 32rem;
  --spacing-144: 36rem;

  /* Add custom fonts */
  --font-family-display: "Poppins", sans-serif;
}
```

---

## 11. Best Practices

### 11.1 Component Organization

#### Extract Reusable Components

```jsx
// Button.jsx
export function Button({ children, variant = "primary", ...props }) {
  const baseClasses = "px-4 py-2 rounded-md font-medium transition";
  const variants = {
    primary: "bg-blue-500 text-white hover:bg-blue-600",
    secondary: "bg-gray-200 text-gray-900 hover:bg-gray-300",
    danger: "bg-red-500 text-white hover:bg-red-600",
  };

  return (
    <button className={`${baseClasses} ${variants[variant]}`} {...props}>
      {children}
    </button>
  );
}
```

#### Use Component Libraries

```jsx
// Card.jsx
export function Card({ children, className = "" }) {
  return (
    <div className={`bg-white rounded-lg shadow-md p-6 ${className}`}>
      {children}
    </div>
  );
}

// Usage
<Card className="hover:shadow-lg transition">
  <h2 className="text-xl font-bold mb-2">Title</h2>
  <p className="text-gray-600">Content</p>
</Card>;
```

### 11.2 Performance Optimization

#### Use PurgeCSS (Built-in)

Tailwind v4 automatically removes unused styles in production.

#### Optimize Build

```bash
# Production build with minification
npx tailwindcss -i ./src/input.css -o ./dist/output.css --minify
```

#### Use JIT Mode (Default in v4)

Just-In-Time mode generates styles on-demand, resulting in faster builds and smaller CSS files.

### 11.3 Maintainability

#### Use Consistent Naming

```jsx
// Good: Consistent utility order
<div className="flex items-center justify-between p-4 bg-white rounded-lg shadow-md">

// Bad: Random order
<div className="shadow-md flex bg-white p-4 rounded-lg items-center justify-between">
```

#### Group Related Classes

```jsx
// Layout
<div className="flex flex-col items-center justify-center">
  {/* Spacing */}
  <div className="p-4 m-2">
    {/* Typography */}
    <h1 className="text-2xl font-bold text-gray-900">
      {/* Colors & Effects */}
      <span className="bg-blue-500 text-white rounded-md shadow-lg">Title</span>
    </h1>
  </div>
</div>
```

#### Use Class Sorting

Install Prettier plugin for automatic class sorting:

```bash
npm install -D prettier prettier-plugin-tailwindcss
```

### 11.4 Common Patterns

#### Card Pattern

```html
<div class="bg-white rounded-lg shadow-md overflow-hidden">
  <img src="image.jpg" class="w-full h-48 object-cover" />
  <div class="p-6">
    <h3 class="text-xl font-bold mb-2">Card Title</h3>
    <p class="text-gray-600 mb-4">Card description</p>
    <button
      class="bg-blue-500 text-white px-4 py-2 rounded-md hover:bg-blue-600"
    >
      Action
    </button>
  </div>
</div>
```

#### Modal Pattern

```html
<div class="fixed inset-0 bg-black/50 flex items-center justify-center">
  <div class="bg-white rounded-lg p-6 max-w-md w-full mx-4">
    <h2 class="text-2xl font-bold mb-4">Modal Title</h2>
    <p class="text-gray-600 mb-6">Modal content</p>
    <div class="flex justify-end gap-2">
      <button class="px-4 py-2 text-gray-600 hover:bg-gray-100 rounded-md">
        Cancel
      </button>
      <button
        class="px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600"
      >
        Confirm
      </button>
    </div>
  </div>
</div>
```

#### Navigation Pattern

```html
<nav class="bg-white shadow-md">
  <div class="container mx-auto px-4">
    <div class="flex items-center justify-between h-16">
      <div class="flex items-center">
        <img src="logo.svg" class="h-8" />
        <span class="ml-2 text-xl font-bold">Brand</span>
      </div>
      <div class="hidden md:flex space-x-4">
        <a href="#" class="text-gray-700 hover:text-blue-500">Home</a>
        <a href="#" class="text-gray-700 hover:text-blue-500">About</a>
        <a href="#" class="text-gray-700 hover:text-blue-500">Contact</a>
      </div>
    </div>
  </div>
</nav>
```

---

## 12. Advanced Features

### 12.1 Container Queries

```html
<!-- Container query context -->
<div class="@container">
  <div class="@sm:text-lg @md:text-xl @lg:text-2xl">
    Responsive to container size
  </div>
</div>

<!-- Named containers -->
<div class="@container/sidebar">
  <div class="@lg/sidebar:hidden">Hidden in large sidebar</div>
</div>
```

### 12.2 Arbitrary Values

```html
<!-- Arbitrary spacing -->
<div class="p-[17px]">Exact 17px padding</div>
<div class="m-[2.5rem]">Exact 2.5rem margin</div>

<!-- Arbitrary colors -->
<div class="bg-[#ff0000]">Hex color</div>
<div class="text-[rgb(255,0,0)]">RGB color</div>

<!-- Arbitrary sizes -->
<div class="w-[347px]">Exact width</div>
<div class="h-[calc(100vh-4rem)]">Calculated height</div>

<!-- Arbitrary properties -->
<div class="[mask-type:luminance]">Custom CSS property</div>
```

### 12.3 Dynamic Classes

#### Using Template Literals (Avoid)

```jsx
// ❌ Bad: Won't be detected by Tailwind
<div className={`text-${color}-500`}>Text</div>

// ✅ Good: Use complete class names
<div className={color === 'blue' ? 'text-blue-500' : 'text-red-500'}>Text</div>
```

#### Using clsx or classnames

```jsx
import clsx from "clsx";

<div
  className={clsx(
    "px-4 py-2 rounded-md",
    isPrimary && "bg-blue-500 text-white",
    isSecondary && "bg-gray-200 text-gray-900",
    isDisabled && "opacity-50 cursor-not-allowed"
  )}
>
  Button
</div>;
```

### 12.4 CSS-in-JS Integration

#### With Styled Components

```jsx
import styled from "styled-components";
import tw from "twin.macro";

const Button = styled.button`
  ${tw`px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600`}
`;
```

#### With Emotion

```jsx
import { css } from "@emotion/react";
import tw from "twin.macro";

const buttonStyles = css`
  ${tw`px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600`}
`;
```

---

## 13. Interview Questions

### 13.1 Fundamental Questions

**Q: What is Tailwind CSS?**
A: Tailwind CSS is a utility-first CSS framework that provides low-level utility classes to build custom designs without writing custom CSS.

**Q: What is utility-first CSS?**
A: An approach where you compose designs using small, single-purpose utility classes instead of writing custom CSS. For example, `flex items-center justify-between` instead of creating a custom `.header` class.

**Q: What are the advantages of Tailwind CSS?**
A: Rapid development, no naming conflicts, consistent design system, small bundle size with PurgeCSS, highly customizable, responsive by default, and great developer experience.

**Q: What are the disadvantages of Tailwind CSS?**
A: HTML can become cluttered with many classes, learning curve for utility names, repetition of patterns, and requires a build step.

**Q: How does Tailwind CSS achieve small bundle sizes?**
A: Through PurgeCSS (built-in), which scans your code and removes unused CSS classes in production, resulting in very small CSS files.

**Q: What is the difference between Tailwind CSS and Bootstrap?**
A: Tailwind is utility-first and provides building blocks, while Bootstrap is component-based with pre-designed components. Tailwind offers more design freedom but requires more work, while Bootstrap is faster for standard designs.

**Q: How do you install Tailwind CSS?**
A: Install via npm (`npm install -D tailwindcss`), initialize config (`npx tailwindcss init`), configure content paths, add Tailwind directives to CSS, and build.

**Q: What is JIT mode in Tailwind?**
A: Just-In-Time mode generates styles on-demand as you use them, resulting in faster build times and smaller development CSS files. It's the default in Tailwind v3+.

**Q: How do you customize Tailwind CSS?**
A: Through the `tailwind.config.js` file (v3) or CSS `@theme` directive (v4), where you can extend colors, spacing, fonts, breakpoints, and more.

**Q: What is PurgeCSS?**
A: A tool (built into Tailwind) that removes unused CSS by scanning your files and eliminating classes that aren't used, dramatically reducing file size.

### 13.2 Advanced Questions

**Q: How does responsive design work in Tailwind?**
A: Tailwind uses mobile-first breakpoint prefixes (`sm:`, `md:`, `lg:`, `xl:`, `2xl:`) that apply styles at specific screen sizes and above.

**Q: What are Tailwind variants?**
A: Modifiers that change when styles apply, such as `hover:`, `focus:`, `active:`, `disabled:`, `dark:`, `group-hover:`, etc.

**Q: How do you implement dark mode in Tailwind?**
A: Add `dark:` prefix to classes (e.g., `dark:bg-gray-900`), configure dark mode strategy in config (`class` or `media`), and toggle the `dark` class on the root element.

**Q: What are arbitrary values in Tailwind?**
A: Square bracket notation that lets you use custom values not in the default scale, like `w-[347px]` or `bg-[#ff0000]`.

**Q: How do you create custom utilities in Tailwind v4?**
A: Use the `@utility` directive in CSS to define custom utility classes with their styles.

**Q: What is the `@apply` directive?**
A: A directive that lets you extract repeated utility patterns into custom CSS classes, though it's discouraged in favor of components.

**Q: How do you handle dynamic class names in Tailwind?**
A: Use complete class names with conditionals instead of string interpolation. Use libraries like `clsx` or `classnames` for conditional classes.

**Q: What are container queries in Tailwind v4?**
A: A feature that allows responsive design based on container size instead of viewport size, using `@container` and `@sm:`, `@md:` prefixes.

**Q: How do you optimize Tailwind for production?**
A: Enable minification, ensure PurgeCSS is configured correctly, use production build command, and consider code splitting for large applications.

**Q: What's new in Tailwind CSS v4?**
A: New Oxide engine (Rust-based), CSS-first configuration with `@theme`, native cascade layers, container queries, improved dark mode, simplified imports, and better performance.

### 13.3 Practical Questions

**Q: How do you center a div with Tailwind?**
A: Using flexbox: `flex items-center justify-center` or using grid: `grid place-items-center` or absolute positioning: `absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2`

**Q: How do you create a responsive grid in Tailwind?**
A: `grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4` - 1 column on mobile, 2 on tablet, 3 on desktop.

**Q: How do you create a gradient background?**
A: `bg-gradient-to-r from-blue-500 to-purple-500` for a left-to-right gradient.

**Q: How do you make text truncate with ellipsis?**
A: `truncate` utility, which applies `overflow: hidden`, `text-overflow: ellipsis`, and `white-space: nowrap`.

**Q: How do you create a sticky header?**
A: `sticky top-0 z-50 bg-white shadow-md`

**Q: How do you handle hover effects on parent-child elements?**
A: Use `group` class on parent and `group-hover:` prefix on child: `<div class="group"><p class="group-hover:text-blue-500">Text</p></div>`

**Q: How do you create a card with shadow that increases on hover?**
A: `bg-white rounded-lg shadow-md hover:shadow-xl transition`

**Q: How do you make an image cover its container?**
A: `w-full h-full object-cover` or for aspect ratio: `aspect-video object-cover`

**Q: How do you create a modal overlay?**
A: `fixed inset-0 bg-black/50 flex items-center justify-center z-50`

**Q: How do you handle form styling in Tailwind?**
A: Use the `@tailwindcss/forms` plugin for better default form styles, or manually style with utilities like `border`, `rounded`, `focus:ring`, etc.

---

## Additional Resources

### Official Documentation

- [Tailwind CSS Docs](https://tailwindcss.com)
- [Tailwind CSS v4 Beta Docs](https://tailwindcss.com/docs/v4-beta)
- [Tailwind UI](https://tailwindui.com) - Premium components

### Tools and Plugins

- **Tailwind CSS IntelliSense** - VS Code extension
- **Headwind** - Class sorting
- **@tailwindcss/forms** - Form styling
- **@tailwindcss/typography** - Prose styling
- **@tailwindcss/aspect-ratio** - Aspect ratio utilities
- **@tailwindcss/container-queries** - Container queries

### Learning Resources

- Tailwind CSS Official Screencasts
- Tailwind Labs YouTube Channel
- Play Tailwind (Interactive Playground)

### Component Libraries

- **Headless UI** - Unstyled, accessible components
- **DaisyUI** - Component library for Tailwind
- **Flowbite** - Component library
- **Tailwind Elements** - Bootstrap-like components

### Community

- Tailwind CSS Discord
- GitHub Discussions
- Twitter @tailwindcss

---

**Happy Styling! 🎨**

_These notes cover Tailwind CSS v4 concepts, features, and interview questions. Practice building projects to master utility-first CSS._
