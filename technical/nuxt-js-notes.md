# Nuxt.js Master Notes By Deepak Modi

> Latest Version: Nuxt 4.2.1 (2024) | Recommended: Nuxt.js Official Docs

## Table of Contents

1. [Introduction to Nuxt.js](#1-introduction-to-nuxtjs)
   - [1.1 What is Nuxt.js?](#11-what-is-nuxtjs)
   - [1.2 Why Nuxt.js?](#12-why-nuxtjs)
   - [1.3 Nuxt 4 Features](#13-nuxt-4-features)
   - [1.4 Nuxt vs Next.js vs SvelteKit](#14-nuxt-vs-nextjs-vs-sveltekit)

2. [Core Concepts](#2-core-concepts)
   - [2.1 File-Based Routing](#21-file-based-routing)
   - [2.2 Auto Imports](#22-auto-imports)
   - [2.3 Server Engine (Nitro)](#23-server-engine-nitro)
   - [2.4 Rendering Modes](#24-rendering-modes)

3. [Routing](#3-routing)
   - [3.1 Pages Directory](#31-pages-directory)
   - [3.2 Dynamic Routes](#32-dynamic-routes)
   - [3.3 Nested Routes](#33-nested-routes)
   - [3.4 Route Middleware](#34-route-middleware)
   - [3.5 Navigation](#35-navigation)

4. [Data Fetching](#4-data-fetching)
   - [4.1 useFetch](#41-usefetch)
   - [4.2 useAsyncData](#42-useasyncdata)
   - [4.3 useLazyFetch](#43-uselazyfetch)
   - [4.4 $fetch](#44-fetch)
   - [4.5 Data Fetching Best Practices](#45-data-fetching-best-practices)

5. [Rendering Strategies](#5-rendering-strategies)
   - [5.1 Universal Rendering (SSR)](#51-universal-rendering-ssr)
   - [5.2 Client-Side Rendering (CSR)](#52-client-side-rendering-csr)
   - [5.3 Static Site Generation (SSG)](#53-static-site-generation-ssg)
   - [5.4 Hybrid Rendering](#54-hybrid-rendering)
   - [5.5 ISR (Incremental Static Regeneration)](#55-isr-incremental-static-regeneration)

6. [State Management](#6-state-management)
   - [6.1 useState](#61-usestate)
   - [6.2 Pinia Integration](#62-pinia-integration)
   - [6.3 State Persistence](#63-state-persistence)

7. [Server Routes & API](#7-server-routes--api)
   - [7.1 API Routes](#71-api-routes)
   - [7.2 Server Middleware](#72-server-middleware)
   - [7.3 Server Utils](#73-server-utils)
   - [7.4 Database Integration](#74-database-integration)

8. [Layouts & Pages](#8-layouts--pages)
   - [8.1 Layouts](#81-layouts)
   - [8.2 Pages](#82-pages)
   - [8.3 Error Pages](#83-error-pages)
   - [8.4 App.vue](#84-appvue)

9. [SEO & Meta Tags](#9-seo--meta-tags)
   - [9.1 useHead](#91-usehead)
   - [9.2 useSeoMeta](#92-useseometa)
   - [9.3 Dynamic Meta](#93-dynamic-meta)
   - [9.4 Sitemap & Robots](#94-sitemap--robots)

10. [Modules & Plugins](#10-modules--plugins)
    - [10.1 Nuxt Modules](#101-nuxt-modules)
    - [10.2 Plugins](#102-plugins)
    - [10.3 Popular Modules](#103-popular-modules)

11. [Configuration](#11-configuration)
    - [11.1 nuxt.config.ts](#111-nuxtconfigts)
    - [11.2 Runtime Config](#112-runtime-config)
    - [11.3 Environment Variables](#113-environment-variables)

12. [Deployment](#12-deployment)
    - [12.1 Build Process](#121-build-process)
    - [12.2 Deployment Platforms](#122-deployment-platforms)
    - [12.3 Performance Optimization](#123-performance-optimization)

13. [Interview Questions](#13-interview-questions)
    - [13.1 Fundamental Questions](#131-fundamental-questions)
    - [13.2 Advanced Questions](#132-advanced-questions)
    - [13.3 Practical Questions](#133-practical-questions)

---

## 1. Introduction to Nuxt.js

### 1.1 What is Nuxt.js?

Nuxt.js is a **meta-framework built on top of Vue.js** that provides a higher-level structure for building production-ready applications. It adds powerful features like server-side rendering, static site generation, file-based routing, and automatic code splitting.

#### Key Characteristics

- **Meta-Framework:** Built on Vue.js, adds structure and conventions
- **Full-Stack:** Frontend and backend in one framework
- **Hybrid Rendering:** Mix SSR, SSG, and CSR
- **Developer Experience:** Auto-imports, hot reload, DevTools
- **Production-Ready:** Optimized builds, SEO-friendly

#### Core Philosophy

Nuxt's design emphasizes:
- **Convention over Configuration:** Sensible defaults, less boilerplate
- **Developer Experience:** Fast development, great tooling
- **Performance:** Optimized builds, efficient rendering
- **Flexibility:** Multiple rendering modes, extensible
- **SEO-First:** Built for search engine optimization

### 1.2 Why Nuxt.js?

#### Advantages

**1. SEO-Friendly**
- Server-side rendering for better indexing
- Meta tag management
- Automatic sitemap generation
- Pre-rendered HTML for crawlers

**2. Performance**
- Automatic code splitting
- Optimized builds
- Lazy loading
- Image optimization
- Fast hydration

**3. Developer Experience**
- File-based routing (no manual route config)
- Auto-imports (components, composables, utils)
- Hot module replacement
- Built-in DevTools
- TypeScript support

**4. Full-Stack Capabilities**
- API routes in same project
- Server middleware
- Database integration
- Authentication handling
- File uploads

**5. Flexible Rendering**
- SSR for dynamic content
- SSG for static pages
- CSR for client-only pages
- Hybrid rendering (mix all three)
- ISR (Incremental Static Regeneration)

**6. Rich Ecosystem**
- Official modules for common needs
- Large community
- Active development
- Good documentation

#### When to Use Nuxt.js

- **E-commerce sites:** SEO-critical, dynamic content
- **Content sites:** Blogs, news, documentation
- **Landing pages:** Fast loading, SEO-optimized
- **Dashboards:** Full-stack applications
- **Marketing sites:** Performance and SEO critical
- **Multi-page applications:** Complex routing needs

#### When NOT to Use Nuxt.js

- **Simple static sites:** Plain HTML/CSS might be enough
- **Highly interactive apps:** Pure CSR might be simpler
- **Real-time apps:** Consider specialized frameworks
- **Mobile apps:** Use native or React Native/Flutter

### 1.3 Nuxt 4 Features

#### Major Updates in Nuxt 4 (2024)

**1. Vue 3.5 Integration**
- Latest Vue.js features
- Better reactivity system
- Improved performance
- Enhanced TypeScript support

**2. Enhanced Performance**
- Faster build times with Vite improvements
- Optimized hydration
- Better code splitting
- Reduced bundle sizes
- Faster HMR (Hot Module Replacement)

**3. Improved Developer Experience**
- Better error messages with stack traces
- Enhanced DevTools with more features
- Faster development server
- Better debugging capabilities

**4. New Composables**
- More utility composables
- Better data fetching composables
- Enhanced state management
- Improved SEO composables

**5. Better TypeScript Support**
- Improved type inference
- Auto-generated types
- Better IDE integration
- Type-safe routing

**6. Module System Improvements**
- Easier module creation
- Better module compatibility
- Enhanced module hooks
- Richer module ecosystem

**7. Server Improvements**
- Better API route handling
- Enhanced server middleware
- Improved caching
- Better error handling

**8. Build Optimizations**
- Tree-shaking improvements
- Better chunk splitting
- Optimized dependencies
- Smaller output sizes

### 1.4 Nuxt vs Next.js vs SvelteKit

| Feature | Nuxt.js | Next.js | SvelteKit |
|---------|---------|---------|-----------|
| **Framework** | Vue.js | React | Svelte |
| **Learning Curve** | Easy | Moderate | Easy |
| **SSR** | Built-in | Built-in | Built-in |
| **SSG** | Built-in | Built-in | Built-in |
| **File Routing** | Yes | Yes | Yes |
| **API Routes** | Yes | Yes | Yes |
| **Auto Imports** | Yes | No | No |
| **State Management** | Built-in | External | Built-in |
| **TypeScript** | First-class | First-class | First-class |
| **Module System** | Rich | Plugin-based | Adapter-based |
| **Bundle Size** | Small | Small | Smallest |
| **Performance** | Fast | Fast | Fastest |
| **Community** | Large | Huge | Growing |
| **Corporate Backing** | Community | Vercel | Community |

---

## 2. Installation and Setup

### 2.1 Installation

#### Create New Nuxt Project

```bash
# Create new Nuxt project (latest version)
npx nuxi@latest init my-nuxt-app

# Navigate to project
cd my-nuxt-app

# Install dependencies
npm install

# Start development server
npm run dev
```

The development server will start at `http://localhost:3000`

#### Installation Options

**With specific Nuxt version:**
```bash
npx nuxi@4.2.1 init my-app
```

**With template:**
```bash
npx nuxi init my-app -t <template-name>
```

### 2.2 Project Structure

```
my-nuxt-app/
├── .nuxt/              # Build output (auto-generated, gitignored)
├── .output/            # Production build output
├── assets/             # Uncompiled assets (CSS, images, fonts)
├── components/         # Vue components (auto-imported)
│   ├── global/         # Globally available components
│   └── feature/        # Feature-specific components
├── composables/        # Composables (auto-imported)
│   └── useAuth.ts
├── content/            # Content files (if using @nuxt/content)
├── layouts/            # App layouts
│   ├── default.vue
│   └── admin.vue
├── middleware/         # Route middleware
│   ├── auth.ts
│   └── analytics.global.ts
├── pages/              # File-based routing
│   ├── index.vue       # Home page
│   ├── about.vue
│   └── posts/
│       └── [id].vue
├── plugins/            # Plugins
│   ├── api.ts
│   └── analytics.client.ts
├── public/             # Static files (served as-is)
│   ├── favicon.ico
│   └── robots.txt
├── server/             # Server-side code
│   ├── api/            # API routes
│   │   ├── posts.get.ts
│   │   └── auth/
│   │       └── login.post.ts
│   ├── middleware/     # Server middleware
│   │   └── log.ts
│   └── utils/          # Server utilities
│       └── db.ts
├── utils/              # Utilities (auto-imported)
│   └── helpers.ts
├── .env                # Environment variables (gitignored)
├── .gitignore
├── app.vue             # Main app component (optional)
├── error.vue           # Error page (optional)
├── nuxt.config.ts      # Nuxt configuration
├── package.json
├── tsconfig.json       # TypeScript configuration
└── README.md
```

**Key Directories:**

- **pages/**: File-based routing, each file becomes a route
- **components/**: Auto-imported Vue components
- **composables/**: Reusable composition functions
- **server/**: Backend code (API routes, middleware, utils)
- **layouts/**: Reusable page layouts
- **middleware/**: Route protection and logic
- **public/**: Static assets served at root
- **assets/**: Assets processed by build tool

### 2.3 Development Tools

#### VS Code Extensions

**Essential:**
1. **Volar** (Vue Language Features)
   - Syntax highlighting
   - IntelliSense
   - Type checking
   - Error detection

2. **Nuxt** (Official Nuxt extension)
   - Nuxt-specific features
   - Better auto-completion
   - File navigation

**Recommended:**
3. **ESLint**
   - Code linting
   - Style enforcement

4. **Prettier**
   - Code formatting

5. **Tailwind CSS IntelliSense** (if using Tailwind)
   - Class name completion
   - CSS preview

#### Nuxt DevTools

Nuxt 3 includes built-in DevTools accessible at `http://localhost:3000/__nuxt_devtools__`

**Features:**
- Component inspector
- Route explorer
- API route tester
- State inspector
- Performance metrics
- Module manager
- Asset inspector

### 2.4 Configuration

#### Basic nuxt.config.ts

```typescript
// nuxt.config.ts
export default defineNuxtConfig({
  // App configuration
  app: {
    head: {
      title: 'My Nuxt App',
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        { name: 'description', content: 'My amazing Nuxt application' }
      ],
      link: [
        { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
      ]
    }
  },

  // Modules
  modules: [
    '@nuxtjs/tailwindcss',
    '@pinia/nuxt',
    '@nuxt/image'
  ],

  // Runtime configuration
  runtimeConfig: {
    // Private keys (server-only)
    apiSecret: process.env.API_SECRET,
    
    // Public keys (client + server)
    public: {
      apiBase: process.env.API_BASE_URL || 'https://api.example.com'
    }
  },

  // Development server
  devServer: {
    port: 3000
  },

  // TypeScript
  typescript: {
    strict: true,
    typeCheck: true
  },

  // Vite configuration
  vite: {
    css: {
      preprocessorOptions: {
        scss: {
          additionalData: '@use "@/assets/styles/variables.scss" as *;'
        }
      }
    }
  }
})
```

### 2.5 Environment Variables

#### .env File

```bash
# .env (not committed to git)
API_SECRET=your-secret-key
API_BASE_URL=https://api.example.com
DATABASE_URL=postgresql://user:password@localhost:5432/db
```

#### Accessing Environment Variables

```typescript
// Server-side (API routes, server middleware)
const config = useRuntimeConfig()
console.log(config.apiSecret) // Private key

// Client-side
const config = useRuntimeConfig()
console.log(config.public.apiBase) // Public key only
```

### 2.6 Package.json Scripts

```json
{
  "scripts": {
    "dev": "nuxt dev",
    "build": "nuxt build",
    "generate": "nuxt generate",
    "preview": "nuxt preview",
    "postinstall": "nuxt prepare",
    "lint": "eslint .",
    "typecheck": "nuxt typecheck"
  }
}
```

**Script Descriptions:**
- `dev`: Start development server
- `build`: Build for production (SSR)
- `generate`: Generate static site (SSG)
- `preview`: Preview production build locally
- `postinstall`: Prepare Nuxt (generate types)
- `lint`: Run ESLint
- `typecheck`: Check TypeScript types

### 2.7 First Nuxt Application

#### app.vue (Optional Root Component)

```vue
<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>
```

#### pages/index.vue (Home Page)

```vue
<template>
  <div class="container">
    <h1>Welcome to Nuxt!</h1>
    <p>{{ message }}</p>
    <NuxtLink to="/about">About</NuxtLink>
  </div>
</template>

<script setup>
const message = ref('Hello from Nuxt 4!')

useHead({
  title: 'Home - My Nuxt App'
})
</script>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}
</style>
```

#### layouts/default.vue (Default Layout)

```vue
<template>
  <div>
    <header>
      <nav>
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/about">About</NuxtLink>
      </nav>
    </header>
    
    <main>
      <slot />
    </main>
    
    <footer>
      <p>&copy; 2024 My Nuxt App</p>
    </footer>
  </div>
</template>

<style scoped>
header {
  background: #00dc82;
  padding: 1rem;
}

nav {
  display: flex;
  gap: 1rem;
}

main {
  min-height: calc(100vh - 200px);
  padding: 2rem;
}

footer {
  background: #f3f4f6;
  padding: 1rem;
  text-align: center;
}
</style>
```

---

## 3. Core Concepts

### 2.1 File-Based Routing

Nuxt automatically generates routes based on file structure in the `pages/` directory. No manual route configuration needed.

#### How It Works

- Each `.vue` file in `pages/` becomes a route
- File name determines the route path
- Folder structure creates nested routes
- Dynamic segments use square brackets
- Catch-all routes use rest parameters

#### Benefits

- No manual route configuration
- Clear project structure
- Easy to understand routing
- Automatic code splitting per route
- Type-safe routing

#### Route Generation Examples

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

### 2.2 Auto Imports

Nuxt automatically imports components, composables, and utilities. No need for manual import statements.

#### What Gets Auto-Imported

**Components:**
- All components in `components/` directory
- Nested components with path-based naming
- Third-party components from modules

**Composables:**
- All files in `composables/` directory
- Vue composables (ref, computed, watch, etc.)
- Nuxt composables (useFetch, useState, etc.)

**Utilities:**
- All files in `utils/` directory
- Helper functions
- Constants

#### Benefits

- Less boilerplate code
- Cleaner component files
- Better developer experience
- Automatic tree-shaking
- Type-safe imports

#### Considerations

- Can make dependencies less explicit
- May cause naming conflicts
- Requires understanding of auto-import rules
- Can be disabled if needed

### 2.3 Server Engine (Nitro)

Nitro is Nuxt's server engine that powers server-side features.

#### Key Features

**1. Universal Deployment**
- Deploy to any platform
- Automatic platform detection
- Optimized for each platform
- Serverless support

**2. API Routes**
- File-based API routes
- Automatic route generation
- Type-safe endpoints
- Built-in validation

**3. Server Middleware**
- Request/response handling
- Authentication
- Logging
- Error handling

**4. Caching**
- Built-in caching layer
- Route-level caching
- API response caching
- Configurable cache strategies

**5. Storage Layer**
- File system storage
- Key-value storage
- Database integration
- Cloud storage support

### 2.4 Rendering Modes

Nuxt supports multiple rendering strategies that can be mixed in the same application.

#### Available Modes

**1. Universal (SSR)**
- Server-side rendering
- Best for SEO
- Dynamic content
- Initial HTML from server

**2. Client-Side (CSR)**
- Rendered in browser
- Like traditional SPA
- No SEO benefits
- Faster subsequent navigation

**3. Static (SSG)**
- Pre-rendered at build time
- Fastest performance
- Best for static content
- Deploy to CDN

**4. Hybrid**
- Mix SSR, CSR, and SSG
- Per-route configuration
- Best of all worlds
- Maximum flexibility

**5. ISR**
- Incremental Static Regeneration
- Static with periodic updates
- Best for semi-dynamic content
- Balance between SSG and SSR

---

## 3. Routing

### 3.1 Pages Directory

The `pages/` directory is the heart of Nuxt routing. Each file automatically becomes a route.

#### Page Components

Pages are Vue components with special features:
- Automatic route generation
- Route metadata with `definePageMeta`
- Access to route parameters
- Navigation guards
- Layout selection

#### Index Routes

`index.vue` files create default routes for their directory level.

### 3.2 Dynamic Routes

Routes with dynamic segments that match URL patterns.

#### Dynamic Parameters

Use square brackets `[param]` in file names to create dynamic segments.

**Types:**
- **Required:** `[id].vue` matches `/posts/123`
- **Optional:** `[id].vue` with optional handling
- **Catch-all:** `[...slug].vue` matches any path depth
- **Regex:** Validate parameters with regex patterns

#### Accessing Parameters

Parameters are available through `useRoute()` composable or `$route` in templates.

#### Parameter Validation

Use `definePageMeta` to validate parameters before rendering.

### 3.3 Nested Routes

Create hierarchical route structures with nested components.

#### How It Works

- Parent component needs `<NuxtPage />` to render children
- Child routes defined in subdirectories
- Shared layouts through parent component
- Independent data fetching per level

#### Use Cases

- Dashboards with sidebar navigation
- Multi-step forms
- Tabbed interfaces
- Master-detail views

### 3.4 Route Middleware

Functions that run before rendering pages. Used for authentication, authorization, redirects, etc.

#### Types of Middleware

**1. Anonymous Middleware**
- Defined inline with `definePageMeta`
- Page-specific logic
- Not reusable

**2. Named Middleware**
- Defined in `middleware/` directory
- Reusable across pages
- Can be applied to multiple routes

**3. Global Middleware**
- Runs on every route change
- Suffix with `.global.ts`
- Used for analytics, auth checks

#### Middleware Execution Order

1. Global middleware (in order)
2. Page-defined middleware (in order)
3. Layout middleware (if any)

#### Common Use Cases

- Authentication checks
- Authorization/permissions
- Redirects based on conditions
- Analytics tracking
- Loading states
- Data prefetching

### 3.5 Navigation

Nuxt provides multiple ways to navigate between pages.

#### Declarative Navigation

Use `<NuxtLink>` component for links. It's optimized for Nuxt with:
- Automatic prefetching
- Active class management
- Smart external link handling
- Accessibility features

#### Programmatic Navigation

Use `navigateTo()` composable for navigation in code:
- Route changes
- Redirects
- External URLs
- With options (replace, redirect)

#### Navigation Guards

Control navigation flow with:
- Middleware
- `onBeforeRouteLeave` hook
- `onBeforeRouteUpdate` hook
- Return values control navigation

---

## 4. Data Fetching

### 4.1 useFetch

Primary composable for fetching data. Wrapper around `useAsyncData` and `$fetch`.

#### Key Features

- **SSR-friendly:** Works on server and client
- **Automatic caching:** Prevents duplicate requests
- **Reactive:** Refetch when dependencies change
- **Type-safe:** Full TypeScript support
- **Error handling:** Built-in error states

#### Return Values

- **data:** Fetched data (reactive)
- **pending:** Loading state
- **error:** Error object if request fails
- **refresh:** Function to refetch data
- **status:** Request status (idle, pending, success, error)

#### Options

- **method:** HTTP method (GET, POST, etc.)
- **query:** Query parameters
- **headers:** Request headers
- **body:** Request body
- **transform:** Transform response data
- **pick:** Select specific fields
- **watch:** Reactive dependencies to watch
- **immediate:** Fetch immediately or wait
- **server:** Run only on server
- **lazy:** Non-blocking fetch

### 4.2 useAsyncData

More flexible data fetching with custom fetcher function.

#### When to Use

- Custom data fetching logic
- Non-HTTP data sources
- Complex data transformations
- Multiple data sources
- Computed data fetching

#### Key Differences from useFetch

- Requires custom fetcher function
- More control over fetching logic
- Can fetch from any source
- More flexible but more verbose

#### Caching

Automatically caches data by key to prevent duplicate requests. Key can be auto-generated or manually specified.

### 4.3 useLazyFetch

Non-blocking version of `useFetch`. Doesn't block navigation.

#### When to Use

- Non-critical data
- Below-the-fold content
- Secondary information
- Progressive enhancement
- Better perceived performance

#### Behavior

- Returns immediately with null data
- Fetches in background
- Updates when data arrives
- Doesn't block page rendering

### 4.4 $fetch

Direct HTTP client for manual API calls. Not SSR-friendly by default.

#### When to Use

- Client-side only requests
- Event handlers
- Form submissions
- Manual API calls
- Non-reactive fetching

#### Characteristics

- Not automatically cached
- Not reactive
- Doesn't track loading state
- Good for one-off requests
- Based on ofetch library

### 4.5 Data Fetching Best Practices

#### SSR Considerations

- Use `useFetch` or `useAsyncData` for SSR
- Avoid `$fetch` in setup (causes double requests)
- Handle errors gracefully
- Consider loading states

#### Performance

- Use `lazy` option for non-critical data
- Implement proper caching
- Minimize data transferred
- Use `pick` to select only needed fields
- Transform data on server when possible

#### Error Handling

- Always handle errors
- Provide fallback UI
- Show user-friendly messages
- Log errors for debugging
- Implement retry logic when appropriate

#### Caching Strategy

- Use appropriate cache keys
- Invalidate cache when needed
- Consider cache duration
- Use `refresh()` to update data
- Implement optimistic updates

---

## 5. Rendering Strategies

### 5.1 Universal Rendering (SSR)

Server-Side Rendering is Nuxt's default mode. Pages are rendered on the server for each request.

#### How It Works

1. User requests page
2. Server renders Vue component to HTML
3. HTML sent to browser
4. Browser displays HTML immediately
5. JavaScript loads and hydrates
6. Page becomes interactive

#### Benefits

- **SEO-friendly:** Full HTML for crawlers
- **Fast initial load:** Content visible immediately
- **Social sharing:** Proper meta tags for previews
- **Accessibility:** Works without JavaScript

#### Drawbacks

- **Server load:** More server resources needed
- **Complexity:** More complex than CSR
- **TTFB:** Time to first byte can be slower
- **Caching:** Requires careful cache strategy

#### When to Use

- SEO-critical pages
- Content-heavy sites
- Dynamic content
- Social media sharing important

### 5.2 Client-Side Rendering (CSR)

Pages rendered entirely in the browser, like traditional SPAs.

#### How It Works

1. Server sends minimal HTML
2. JavaScript bundle loads
3. Vue renders content in browser
4. Page becomes interactive

#### Benefits

- **Simple deployment:** Static files only
- **No server costs:** Can use CDN
- **Rich interactions:** Full client-side control
- **Fast navigation:** No server roundtrips

#### Drawbacks

- **Poor SEO:** Limited HTML for crawlers
- **Slow initial load:** Wait for JavaScript
- **No social previews:** Missing meta tags
- **JavaScript required:** Won't work without JS

#### When to Use

- Authenticated dashboards
- Admin panels
- Internal tools
- Apps not needing SEO

### 5.3 Static Site Generation (SSG)

Pages pre-rendered at build time and served as static files.

#### How It Works

1. Build process renders all pages
2. Generates static HTML files
3. Deploy to CDN
4. Browser receives pre-rendered HTML
5. Hydration makes interactive

#### Benefits

- **Fastest performance:** Instant page loads
- **SEO-friendly:** Full HTML for crawlers
- **Cheap hosting:** Static file hosting
- **High scalability:** CDN distribution
- **Security:** No server to attack

#### Drawbacks

- **Build time:** Longer builds for many pages
- **Stale content:** Requires rebuild for updates
- **Dynamic content:** Not suitable for frequently changing data
- **Personalization:** Limited user-specific content

#### When to Use

- Blogs and documentation
- Marketing sites
- Landing pages
- Content that doesn't change often

### 5.4 Hybrid Rendering

Mix different rendering strategies in the same application.

#### Route Rules

Configure rendering per route using `routeRules` in `nuxt.config.ts`.

**Options:**
- **ssr:** Enable/disable SSR per route
- **prerender:** Pre-render specific routes
- **swr:** Stale-while-revalidate caching
- **cache:** Cache duration
- **redirect:** Redirect rules

#### Benefits

- **Flexibility:** Best strategy per page
- **Optimization:** Optimize each route differently
- **Gradual adoption:** Mix strategies as needed
- **Performance:** Fine-tune per route

#### Use Cases

- Homepage: SSG for speed
- Product pages: ISR for freshness
- Dashboard: CSR for interactivity
- Blog posts: SSG for performance

### 5.5 ISR (Incremental Static Regeneration)

Static pages that regenerate periodically in the background.

#### How It Works

1. Page pre-rendered at build
2. Served from cache
3. Cache expires after duration
4. Next request triggers regeneration
5. Old page served while regenerating
6. New page cached for future requests

#### Benefits

- **Static performance:** Fast like SSG
- **Fresh content:** Updates periodically
- **Scalability:** CDN distribution
- **No build required:** Updates without rebuild

#### Configuration

Use `swr` in route rules to enable ISR with cache duration.

#### When to Use

- Product catalogs
- News sites
- Blog posts
- Content that updates periodically

---

## 6. State Management

### 6.1 useState

Nuxt's built-in composable for SSR-friendly shared state.

#### How It Works

- Creates reactive state shared across components
- SSR-safe (state synced between server and client)
- Scoped to current request on server
- Persists during client-side navigation

#### Key Features

- **Shared state:** Accessible from any component
- **SSR-safe:** No state leakage between requests
- **Reactive:** Automatic updates
- **Type-safe:** Full TypeScript support
- **Simple API:** Easy to use

#### When to Use

- Simple shared state
- User preferences
- UI state (modals, sidebars)
- Temporary data
- Small applications

#### Limitations

- Not persistent (resets on page reload)
- No time-travel debugging
- Limited organization for complex state
- No built-in devtools

### 6.2 Pinia Integration

Pinia is the recommended state management for complex applications.

#### Why Pinia with Nuxt

- **Official module:** First-class integration
- **SSR support:** Works with server rendering
- **DevTools:** Built-in debugging
- **TypeScript:** Excellent type support
- **Modular:** Organize by feature

#### Setup

Install `@pinia/nuxt` module and add to `nuxt.config.ts`.

#### Benefits Over useState

- Better organization
- DevTools support
- Actions and getters
- Plugin system
- Time-travel debugging

#### When to Use

- Complex state logic
- Multiple stores
- Large applications
- Need for debugging
- Team projects

### 6.3 State Persistence

Keep state across page reloads using various strategies.

#### Options

**1. localStorage/sessionStorage**
- Client-side only
- Simple implementation
- Limited storage
- Synchronous

**2. Cookies**
- Works on server and client
- Sent with every request
- Size limitations
- Good for auth tokens

**3. IndexedDB**
- Large storage capacity
- Asynchronous
- Client-side only
- Complex API

**4. Server-side sessions**
- Secure
- No size limits
- Requires server
- More complex

---

## 7. Server Routes & API

### 7.1 API Routes

Create backend API endpoints in the same project as frontend.

#### File-Based API Routes

Files in `server/api/` automatically become API endpoints.

**Naming convention:**
- `file.get.ts` → GET /api/file
- `file.post.ts` → POST /api/file
- `file.put.ts` → PUT /api/file
- `file.delete.ts` → DELETE /api/file
- `file.ts` → Handles all methods

#### Event Handler

Use `defineEventHandler` to create API route handlers.

#### Request Handling

- **getQuery:** Get query parameters
- **readBody:** Read request body
- **getRouterParam:** Get route parameters
- **getHeader:** Get request headers
- **getCookie:** Get cookies

#### Response Handling

- Return data directly (auto-serialized to JSON)
- Set status code with `setResponseStatus`
- Set headers with `setHeader`
- Send errors with `createError`

### 7.2 Server Middleware

Middleware that runs on every request before route handlers.

#### Use Cases

- Authentication
- Logging
- Request modification
- Rate limiting
- CORS handling

#### Execution Order

Server middleware runs before API routes and page rendering.

### 7.3 Server Utils

Reusable server-side utilities in `server/utils/`.

#### Use Cases

- Database queries
- Authentication helpers
- Validation functions
- External API calls
- Business logic

#### Auto-Import

Server utils are automatically imported in server context (API routes, middleware).

### 7.4 Database Integration

Connect to databases from server routes.

#### Options

**1. SQL Databases**
- PostgreSQL
- MySQL
- SQLite
- Use Prisma, Drizzle, or Kysely

**2. NoSQL Databases**
- MongoDB
- Redis
- Firebase

**3. ORMs/Query Builders**
- Prisma (recommended)
- Drizzle ORM
- Kysely
- TypeORM

#### Best Practices

- Use connection pooling
- Handle errors gracefully
- Validate input data
- Use transactions when needed
- Implement proper indexing

---

## 8. Layouts & Pages

### 8.1 Layouts

Reusable page structures that wrap page components.

#### Default Layout

`layouts/default.vue` is used by default for all pages unless specified otherwise.

#### Custom Layouts

Create multiple layouts for different page types:
- `layouts/admin.vue` for admin pages
- `layouts/auth.vue` for auth pages
- `layouts/blog.vue` for blog pages

#### Selecting Layouts

Use `definePageMeta` in pages to select layout.

#### Layout Components

- Must have `<slot />` to render page content
- Can have shared navigation, headers, footers
- Can fetch shared data
- Can define shared state

### 8.2 Pages

Vue components in `pages/` directory that become routes.

#### Page Meta

Use `definePageMeta` to configure:
- Layout selection
- Middleware
- Route metadata
- Transition effects
- Keep-alive settings

#### Page Components

Pages can:
- Fetch data with composables
- Define SEO meta tags
- Access route parameters
- Use layouts
- Define middleware

### 8.3 Error Pages

Custom error pages for different error scenarios.

#### Error Page

Create `error.vue` in project root to handle errors.

#### Error Object

Receives error object with:
- **statusCode:** HTTP status code
- **message:** Error message
- **stack:** Stack trace (dev only)

#### Custom Error Pages

Create different error pages for specific status codes.

### 8.4 App.vue

Optional root component that wraps entire application.

#### Use Cases

- Global layouts
- App-wide providers
- Global error handling
- Loading states
- Transition effects

#### When to Use

- Need app-wide wrapper
- Global state providers
- Custom root structure
- App-level error boundary

---

## 9. SEO & Meta Tags

### 9.1 useHead

Composable for managing document head (title, meta tags, links, scripts).

#### Features

- Reactive meta tags
- Per-page customization
- Template syntax
- Script management
- Link management

#### Use Cases

- Page titles
- Meta descriptions
- Open Graph tags
- Twitter cards
- Canonical URLs
- Structured data

### 9.2 useSeoMeta

Simplified composable specifically for SEO meta tags.

#### Benefits

- Type-safe SEO tags
- Cleaner syntax
- Common SEO patterns
- Auto-completion in IDE
- Less verbose than useHead

#### Supported Tags

- Title and description
- Open Graph tags
- Twitter cards
- Canonical URLs
- Robots directives

### 9.3 Dynamic Meta

Generate meta tags based on page data.

#### Patterns

- Fetch data first
- Use computed properties
- Update meta reactively
- Handle loading states
- Provide fallbacks

### 9.4 Sitemap & Robots

#### Sitemap

Use `@nuxtjs/sitemap` module to generate sitemap.xml automatically.

**Features:**
- Auto-generate from routes
- Dynamic routes
- Custom URLs
- Multiple sitemaps
- Sitemap index

#### Robots.txt

Configure robots.txt to control crawler access.

**Best practices:**
- Allow important pages
- Disallow admin/private pages
- Link to sitemap
- Specify crawl delay if needed

---

## 10. Modules & Plugins

### 10.1 Nuxt Modules

Modules extend Nuxt's core functionality.

#### Types of Modules

**1. Official Modules**
- Maintained by Nuxt team
- Well-documented
- Regularly updated
- Production-ready

**2. Community Modules**
- Created by community
- Various quality levels
- Specific use cases
- May have less support

#### Module Capabilities

- Add components
- Add composables
- Add plugins
- Modify configuration
- Add server routes
- Extend build process

### 10.2 Plugins

Plugins run before Vue app is created. Used for:
- Vue plugins
- Third-party libraries
- Global utilities
- Client/server-specific code

#### Plugin Types

**1. Client-only plugins**
- Suffix with `.client.ts`
- Run only in browser
- For browser APIs

**2. Server-only plugins**
- Suffix with `.server.ts`
- Run only on server
- For server APIs

**3. Universal plugins**
- No suffix
- Run on both server and client
- Most common type

### 10.3 Popular Modules

#### UI & Styling
- `@nuxtjs/tailwindcss` - Tailwind CSS
- `@nuxt/ui` - UI component library
- `@nuxtjs/color-mode` - Dark mode

#### SEO & Meta
- `@nuxtjs/seo` - SEO utilities
- `@nuxtjs/sitemap` - Sitemap generation
- `nuxt-schema-org` - Structured data

#### Data & API
- `@nuxt/content` - File-based CMS
- `@pinia/nuxt` - State management
- `@nuxtjs/apollo` - GraphQL

#### Images & Media
- `@nuxt/image` - Image optimization
- `@nuxtjs/cloudinary` - Cloudinary integration

#### Authentication
- `@sidebase/nuxt-auth` - Authentication
- `@nuxtjs/supabase` - Supabase integration

#### Internationalization
- `@nuxtjs/i18n` - Multi-language support

#### Analytics & Monitoring
- `@nuxtjs/google-analytics` - Google Analytics
- `@nuxtjs/plausible` - Plausible Analytics

---

## 11. Configuration

### 11.1 nuxt.config.ts

Central configuration file for Nuxt application.

#### Key Configuration Options

**App Config:**
- head: Default meta tags
- pageTransition: Page transitions
- layoutTransition: Layout transitions

**Build Config:**
- transpile: Dependencies to transpile
- analyze: Bundle analysis
- optimization: Build optimizations

**Modules:**
- List of Nuxt modules to use

**Vite Config:**
- Vite-specific configuration
- CSS preprocessors
- Build plugins

**Router Config:**
- options: Router options
- middleware: Global middleware

**Nitro Config:**
- prerender: Pre-render routes
- routeRules: Per-route configuration

### 11.2 Runtime Config

Configuration that can be different between environments.

#### Public vs Private

**Private (server-only):**
- API keys
- Database credentials
- Secret tokens
- Sensitive data

**Public (client + server):**
- API base URLs
- Public keys
- Feature flags
- Non-sensitive config

#### Accessing Runtime Config

Use `useRuntimeConfig()` composable to access configuration.

### 11.3 Environment Variables

Manage configuration across environments.

#### .env File

Store environment variables in `.env` file (not committed to git).

#### Best Practices

- Never commit secrets
- Use different values per environment
- Validate required variables
- Document all variables
- Use type-safe access

---

## 12. Deployment

### 12.1 Build Process

#### Build Commands

**Development:**
- `npm run dev` - Development server
- Hot reload enabled
- Source maps
- DevTools

**Production:**
- `npm run build` - Build for production
- Minification
- Optimization
- Tree-shaking

**Preview:**
- `npm run preview` - Preview production build locally

**Generate (SSG):**
- `npm run generate` - Generate static site

### 12.2 Deployment Platforms

#### Vercel
- Zero-config deployment
- Automatic HTTPS
- Global CDN
- Serverless functions
- Preview deployments

#### Netlify
- Git-based deployment
- Automatic builds
- CDN distribution
- Edge functions
- Form handling

#### Node.js Server
- Full control
- Any hosting provider
- PM2 for process management
- Nginx as reverse proxy
- Manual scaling

#### Docker
- Containerized deployment
- Consistent environments
- Easy scaling
- Cloud-agnostic
- Orchestration support

#### Static Hosting (SSG)
- GitHub Pages
- Cloudflare Pages
- AWS S3 + CloudFront
- Any static host

### 12.3 Performance Optimization

#### Build Optimization

- Enable compression
- Minimize bundle size
- Code splitting
- Tree-shaking
- Remove unused code

#### Runtime Optimization

- Use lazy loading
- Implement caching
- Optimize images
- Reduce API calls
- Use CDN

#### SEO Optimization

- Server-side rendering
- Meta tags
- Sitemap
- Structured data
- Fast loading times

#### Monitoring

- Performance metrics
- Error tracking
- User analytics
- Core Web Vitals
- Server monitoring

---

## 13. Interview Questions

### 13.1 Fundamental Questions

**Q: What is Nuxt.js?**
A: Nuxt.js is a meta-framework built on Vue.js that provides server-side rendering, static site generation, file-based routing, and other features for building production-ready applications.

**Q: What are the main benefits of using Nuxt.js?**
A: SEO-friendly (SSR/SSG), better performance, automatic routing, auto-imports, full-stack capabilities with API routes, multiple rendering modes, and excellent developer experience.

**Q: What is file-based routing?**
A: Automatic route generation based on file structure in the `pages/` directory. Each `.vue` file becomes a route without manual configuration.

**Q: What are the different rendering modes in Nuxt?**
A: Universal (SSR), Client-Side (CSR), Static (SSG), Hybrid (mix of all), and ISR (Incremental Static Regeneration).

**Q: What is the difference between SSR and SSG?**
A: SSR renders pages on each request (dynamic), while SSG pre-renders pages at build time (static). SSR is better for dynamic content, SSG for static content.

**Q: What is Nitro?**
A: Nuxt's server engine that provides API routes, server middleware, universal deployment, and optimized server-side rendering.

**Q: What are auto-imports in Nuxt?**
A: Automatic importing of components, composables, and utilities without explicit import statements. Improves developer experience and reduces boilerplate.

**Q: What is the purpose of layouts in Nuxt?**
A: Reusable page structures that wrap page components. Used for shared navigation, headers, footers, and common UI elements.

**Q: What is middleware in Nuxt?**
A: Functions that run before rendering pages. Used for authentication, authorization, redirects, and other pre-rendering logic.

**Q: What is the difference between useFetch and $fetch?**
A: `useFetch` is SSR-friendly, reactive, and caches data automatically. `$fetch` is for manual API calls, client-side only by default, and doesn't provide loading states.

### 13.2 Advanced Questions

**Q: How does Nuxt handle SEO?**
A: Through SSR/SSG for full HTML, `useHead` and `useSeoMeta` composables for meta tags, automatic sitemap generation, and proper HTML structure for crawlers.

**Q: What is hybrid rendering and when would you use it?**
A: Mixing different rendering strategies (SSR, SSG, CSR) in the same application using route rules. Use it to optimize each route differently - SSG for static pages, SSR for dynamic pages, CSR for authenticated sections.

**Q: How does useState differ from Pinia?**
A: `useState` is simpler, built-in, and good for basic shared state. Pinia is more powerful with actions, getters, DevTools, and better organization for complex state management.

**Q: What is ISR (Incremental Static Regeneration)?**
A: A rendering strategy that combines SSG benefits (speed) with periodic updates. Pages are pre-rendered but regenerate in the background after a specified duration.

**Q: How do you handle authentication in Nuxt?**
A: Using middleware to protect routes, storing tokens in httpOnly cookies, creating auth composables, using server routes for auth logic, and modules like `@sidebase/nuxt-auth`.

**Q: What are route rules and how are they used?**
A: Configuration in `nuxt.config.ts` to set rendering mode, caching, redirects, and other behaviors per route. Enables hybrid rendering and fine-grained optimization.

**Q: How does Nuxt handle data fetching on the server vs client?**
A: Uses composables like `useFetch` and `useAsyncData` that work on both server and client. Data fetched on server is serialized and hydrated on client to avoid duplicate requests.

**Q: What is the purpose of the server directory?**
A: Contains server-side code including API routes (`server/api/`), middleware (`server/middleware/`), and utilities (`server/utils/`) that run only on the server.

**Q: How do you optimize Nuxt application performance?**
A: Use appropriate rendering mode per route, implement lazy loading, optimize images with `@nuxt/image`, use caching strategies, code splitting, and production builds.

**Q: What is the difference between plugins and modules?**
A: Plugins extend the Vue app instance and run at runtime. Modules extend Nuxt itself at build time, can add routes, components, and modify configuration.

**Q: How does Nuxt handle environment variables?**
A: Through `runtimeConfig` in `nuxt.config.ts`. Private keys are server-only, public keys are exposed to client. Access with `useRuntimeConfig()`.

**Q: What is the purpose of app.vue?**
A: Optional root component that wraps the entire application. Used for app-wide layouts, providers, global error handling, and loading states.

**Q: How do you implement error handling in Nuxt?**
A: Create `error.vue` for custom error pages, use `createError` in server routes, implement error boundaries, and handle errors in data fetching composables.

**Q: What is the difference between layouts and pages?**
A: Layouts are reusable wrappers with shared UI (navigation, footer). Pages are specific route components. Layouts wrap pages and can be switched per page.

**Q: How does Nuxt handle code splitting?**
A: Automatically splits code per route, supports lazy loading with dynamic imports, creates vendor chunks, and optimizes bundle sizes for better performance.

### 13.3 Practical Questions

**Q: How do you create dynamic routes in Nuxt?**
A: Use square brackets in file names: `[id].vue` for `/posts/:id`. Access parameters with `useRoute().params.id`.

**Q: How do you fetch data in Nuxt?**
A: Use `useFetch` for simple API calls, `useAsyncData` for custom fetching logic, `useLazyFetch` for non-blocking fetches, and `$fetch` for manual client-side calls.

**Q: How do you protect routes with authentication?**
A: Create middleware to check auth state, redirect to login if not authenticated, apply middleware to protected pages with `definePageMeta`.

**Q: How do you implement pagination in Nuxt?**
A: Use query parameters for page number, watch query changes with `useFetch`, update URL with `navigateTo`, and handle loading states.

**Q: How do you create API routes in Nuxt?**
A: Create files in `server/api/` directory. Use `defineEventHandler` to handle requests. File name determines endpoint and HTTP method.

**Q: How do you handle forms in Nuxt?**
A: Use `v-model` for inputs, handle submit with API routes, show loading states, validate data, handle errors, and provide feedback.

**Q: How do you implement internationalization (i18n)?**
A: Use `@nuxtjs/i18n` module. Define translations, configure locales, use `$t()` for translations, handle route localization, and detect user language.

**Q: How do you optimize images in Nuxt?**
A: Use `@nuxt/image` module for automatic optimization, lazy loading, responsive images, and format conversion (WebP, AVIF).

**Q: How do you implement caching in Nuxt?**
A: Use route rules with `swr` or `cache` options, implement HTTP caching headers, use CDN caching, and cache API responses.

**Q: How do you deploy a Nuxt application?**
A: Build with `npm run build`, choose deployment platform (Vercel, Netlify, Node.js), configure environment variables, and deploy. For SSG, use `npm run generate`.

**Q: How do you handle loading states in Nuxt?**
A: Use `pending` from data fetching composables, create loading components, use Suspense for async components, and show skeletons or spinners.

**Q: How do you implement dark mode in Nuxt?**
A: Use `@nuxtjs/color-mode` module, toggle with `useColorMode()`, apply CSS classes based on mode, persist preference, and respect system preference.

**Q: How do you handle redirects in Nuxt?**
A: Use `navigateTo()` in middleware, configure redirects in route rules, handle in API routes with `sendRedirect`, or use server middleware.

**Q: How do you implement real-time features in Nuxt?**
A: Use WebSockets, Server-Sent Events (SSE), or third-party services like Pusher/Supabase Realtime. Handle connection in plugins or composables.

**Q: How do you test Nuxt applications?**
A: Use Vitest for unit tests, Playwright or Cypress for E2E tests, test composables and components separately, mock API calls, and test server routes.

---

## Additional Resources

### Official Documentation
- [Nuxt.js Official Docs](https://nuxt.com)
- [Nuxt Modules](https://nuxt.com/modules)
- [Nitro Documentation](https://nitro.unjs.io)

### Tools
- **Nuxt DevTools** - Built-in development tools
- **Vue DevTools** - Browser extension
- **Vite** - Build tool

### Learning Resources
- Nuxt.com Learn Section
- Vue Mastery Nuxt Course
- Official Nuxt YouTube Channel
- Nuxt Examples Repository

### Popular Modules
- **@nuxt/image** - Image optimization
- **@nuxt/content** - File-based CMS
- **@nuxtjs/tailwindcss** - Tailwind CSS
- **@pinia/nuxt** - State management
- **@nuxtjs/i18n** - Internationalization
- **@sidebase/nuxt-auth** - Authentication

---

**Happy Coding with Nuxt.js! 🚀**

_These notes cover Nuxt.js 4.2 concepts, features, and interview questions. Practice building projects to master Nuxt development._

