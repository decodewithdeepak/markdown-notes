# Next.js Master Notes By Deepak Modi

> Latest Stable: Next.js 16 (October 2025) | Previous: Next.js 15 (October 2024) | Recommended: Next.js Official Docs, Vercel Documentation

## Table of Contents

1. [Introduction to Next.js](#1-introduction-to-nextjs)

   - [1.1 What is Next.js?](#11-what-is-nextjs)
   - [1.2 Why Next.js?](#12-why-nextjs)
   - [1.3 Next.js vs Other Frameworks](#13-nextjs-vs-other-frameworks)
   - [1.4 Next.js 16 New Features](#14-nextjs-16-new-features)
   - [1.5 Setting Up Next.js 16](#15-setting-up-nextjs-16)

2. [App Router (Recommended)](#2-app-router-recommended)

   - [2.1 App Router vs Pages Router](#21-app-router-vs-pages-router)
   - [2.2 File-based Routing](#22-file-based-routing)
   - [2.3 Layouts and Templates](#23-layouts-and-templates)
   - [2.4 Route Groups](#24-route-groups)
   - [2.5 Dynamic Routes](#25-dynamic-routes)
   - [2.6 Parallel Routes](#26-parallel-routes)
   - [2.7 Intercepting Routes](#27-intercepting-routes)
   - [2.8 Route Handlers (API Routes)](#28-route-handlers-api-routes)

3. [Server Components & Client Components](#3-server-components--client-components)

   - [3.1 React Server Components (RSC)](#31-react-server-components-rsc)
   - [3.2 Client Components](#32-client-components)
   - [3.3 When to Use Server vs Client](#33-when-to-use-server-vs-client)
   - [3.4 Composition Patterns](#34-composition-patterns)
   - [3.5 Server Actions](#35-server-actions)

4. [Rendering Strategies](#4-rendering-strategies)

   - [4.1 Static Rendering (SSG)](#41-static-rendering-ssg)
   - [4.2 Dynamic Rendering (SSR)](#42-dynamic-rendering-ssr)
   - [4.3 Streaming](#43-streaming)
   - [4.4 Incremental Static Regeneration (ISR)](#44-incremental-static-regeneration-isr)
   - [4.5 Partial Prerendering (PPR)](#45-partial-prerendering-ppr)

5. [Data Fetching](#5-data-fetching)

   - [5.1 Server-Side Data Fetching](#51-server-side-data-fetching)
   - [5.2 Client-Side Data Fetching](#52-client-side-data-fetching)
   - [5.3 Caching Strategies](#53-caching-strategies)
   - [5.4 Revalidation](#54-revalidation)
   - [5.5 Parallel and Sequential Data Fetching](#55-parallel-and-sequential-data-fetching)

6. [Caching](#6-caching)

   - [6.1 Request Memoization](#61-request-memoization)
   - [6.2 Data Cache](#62-data-cache)
   - [6.3 Full Route Cache](#63-full-route-cache)
   - [6.4 Router Cache](#64-router-cache)
   - [6.5 Cache Configuration](#65-cache-configuration)

7. [Metadata and SEO](#7-metadata-and-seo)

   - [7.1 Static Metadata](#71-static-metadata)
   - [7.2 Dynamic Metadata](#72-dynamic-metadata)
   - [7.3 Open Graph and Twitter Cards](#73-open-graph-and-twitter-cards)
   - [7.4 JSON-LD](#74-json-ld)
   - [7.5 Sitemap and Robots](#75-sitemap-and-robots)

8. [Styling](#8-styling)

   - [8.1 CSS Modules](#81-css-modules)
   - [8.2 Tailwind CSS](#82-tailwind-css)
   - [8.3 CSS-in-JS](#83-css-in-js)
   - [8.4 Sass](#84-sass)
   - [8.5 Global Styles](#85-global-styles)

9. [Images and Fonts](#9-images-and-fonts)

   - [9.1 Next.js Image Component](#91-nextjs-image-component)
   - [9.2 Image Optimization](#92-image-optimization)
   - [9.3 Font Optimization](#93-font-optimization)
   - [9.4 Local Fonts](#94-local-fonts)

10. [Navigation and Linking](#10-navigation-and-linking)

    - [10.1 Link Component](#101-link-component)
    - [10.2 useRouter Hook](#102-userouter-hook)
    - [10.3 usePathname and useSearchParams](#103-usepathname-and-usesearchparams)
    - [10.4 Redirects](#104-redirects)
    - [10.5 Middleware](#105-middleware)

11. [Authentication](#11-authentication)

    - [11.1 Authentication Strategies](#111-authentication-strategies)
    - [11.2 NextAuth.js (Auth.js)](#112-nextauthjs-authjs)
    - [11.3 Session Management](#113-session-management)
    - [11.4 Protected Routes](#114-protected-routes)
    - [11.5 JWT and Cookies](#115-jwt-and-cookies)

12. [API Routes and Server Actions](#12-api-routes-and-server-actions)

    - [12.1 Route Handlers](#121-route-handlers)
    - [12.2 Server Actions](#122-server-actions)
    - [12.3 Form Handling](#123-form-handling)
    - [12.4 Error Handling](#124-error-handling)
    - [12.5 CORS and Security](#125-cors-and-security)

13. [Database Integration](#13-database-integration)

    - [13.1 Prisma](#131-prisma)
    - [13.2 MongoDB](#132-mongodb)
    - [13.3 PostgreSQL](#133-postgresql)
    - [13.4 Supabase](#134-supabase)
    - [13.5 Database Best Practices](#135-database-best-practices)

14. [Performance Optimization](#14-performance-optimization)

    - [14.1 Code Splitting](#141-code-splitting)
    - [14.2 Lazy Loading](#142-lazy-loading)
    - [14.3 Bundle Analysis](#143-bundle-analysis)
    - [14.4 Performance Monitoring](#144-performance-monitoring)
    - [14.5 Web Vitals](#145-web-vitals)

15. [Testing](#15-testing)

    - [15.1 Unit Testing](#151-unit-testing)
    - [15.2 Integration Testing](#152-integration-testing)
    - [15.3 E2E Testing](#153-e2e-testing)
    - [15.4 Testing Server Components](#154-testing-server-components)

16. [Deployment](#16-deployment)

    - [16.1 Vercel Deployment](#161-vercel-deployment)
    - [16.2 Self-Hosting](#162-self-hosting)
    - [16.3 Docker](#163-docker)
    - [16.4 Environment Variables](#164-environment-variables)
    - [16.5 CI/CD](#165-cicd)

17. [Advanced Concepts](#17-advanced-concepts)

    - [17.1 Internationalization (i18n)](#171-internationalization-i18n)
    - [17.2 Edge Runtime](#172-edge-runtime)
    - [17.3 Turbopack](#173-turbopack)
    - [17.4 Custom Server](#174-custom-server)
    - [17.5 Monorepo Setup](#175-monorepo-setup)

18. [Interview Questions](#18-interview-questions)
    - [18.1 Fundamental Questions](#181-fundamental-questions)
    - [18.2 Rendering Questions](#182-rendering-questions)
    - [18.3 Performance Questions](#183-performance-questions)
    - [18.4 Advanced Questions](#184-advanced-questions)
    - [18.5 Scenario-Based Questions](#185-scenario-based-questions)

---

## 1. Introduction to Next.js

### 1.1 What is Next.js?

Next.js is a **React framework** for building full-stack web applications. Created by Vercel, it provides a powerful set of features for production-ready applications including server-side rendering, static site generation, and API routes.

> **Key Point:** Next.js is a framework built on top of React, providing additional structure, features, and optimizations out of the box.

#### Core Features

- **Server-Side Rendering (SSR):** Render pages on the server
- **Static Site Generation (SSG):** Pre-render pages at build time
- **Incremental Static Regeneration (ISR):** Update static pages after deployment
- **API Routes:** Build backend APIs within Next.js
- **File-based Routing:** Automatic routing based on file structure
- **Image Optimization:** Automatic image optimization
- **Font Optimization:** Automatic font loading optimization
- **Code Splitting:** Automatic code splitting for faster page loads

#### Real-World Usage

Companies using Next.js: Netflix, TikTok, Twitch, Hulu, Nike, Uber, GitHub, Notion, Target, Walmart

### 1.2 Why Next.js?

#### Advantages

1. **SEO-Friendly:** Built-in SSR and SSG for better SEO
2. **Performance:** Automatic optimizations (images, fonts, code splitting)
3. **Developer Experience:** Fast refresh, TypeScript support, great tooling
4. **Full-Stack:** Build frontend and backend in one project
5. **Production Ready:** Built-in optimizations for production
6. **Scalable:** Handles small to large applications
7. **Zero Config:** Works out of the box with sensible defaults
8. **Vercel Integration:** Seamless deployment to Vercel

#### When to Use Next.js

- Content-heavy websites (blogs, documentation)
- E-commerce applications
- Marketing websites
- Dashboards and admin panels
- SaaS applications
- Any application requiring SEO

#### When NOT to Use Next.js

- Simple single-page applications (use Create React App or Vite)
- Applications with no SEO requirements
- Real-time applications with constant updates (consider WebSocket-focused solutions)

### 1.3 Next.js vs Other Frameworks

| Feature              | Next.js        | Create React App | Gatsby        | Remix        |
| -------------------- | -------------- | ---------------- | ------------- | ------------ |
| Rendering            | SSR/SSG/ISR    | CSR              | SSG           | SSR          |
| Routing              | File-based     | Manual           | File-based    | File-based   |
| API Routes           | Yes            | No               | No            | Yes          |
| Image Optimization   | Built-in       | Manual           | Plugin        | Manual       |
| TypeScript           | Built-in       | Manual           | Manual        | Built-in     |
| Learning Curve       | Moderate       | Easy             | Moderate      | Moderate     |
| Build Speed          | Fast (Turbo)   | Moderate         | Slow          | Fast         |
| Data Fetching        | Flexible       | Client-only      | GraphQL-first | Loader-based |
| Server Components    | Yes (React 19) | No               | No            | No           |
| Edge Runtime Support | Yes            | No               | No            | Yes          |

### 1.4 Next.js Version History

#### Next.js 15 Features (Released October 2024)

**1. React 19 Support**

- Full support for React 19 features
- Enhanced Server Components
- Improved Server Actions
- Better streaming support

**2. Turbopack Stable (Dev Mode)**

- Turbopack is now stable for development (Rust-based bundler)
- Up to 76.7% faster local server startup
- Up to 96.3% faster code updates with Fast Refresh
- Better HMR (Hot Module Replacement)
- Production builds still use Webpack (Turbopack for production coming in Next.js 16)

**3. Enhanced Caching**

- More granular cache control
- Better cache invalidation
- `fetch` requests are no longer cached by default
- Enhanced revalidation strategies

**4. Partial Prerendering (PPR) - Experimental**

- Experimental PPR support
- Mix static and dynamic content in same route
- Improved performance for hybrid pages

**5. `next/after` API**

- New API to execute code after response is sent
- Useful for logging, analytics
- Doesn't block the response

**6. Enhanced `create-next-app`**

- New design and improved prompts
- Better project setup experience
- Turbopack enabled by default in dev

**7. Server Actions Enhancements**

- Better form handling with Server Actions
- Improved security
- Enhanced error handling

**8. Async Request APIs (Breaking Change)**

- `headers()`, `cookies()`, `params`, and `searchParams` are now async
- Better alignment with async nature of server requests

#### Next.js 16 Features (Released October 2025)

**Major Updates in Next.js 16:**

**1. Turbopack for Production (Stable)**

- Turbopack is now stable for production builds
- Up to 10x faster production builds compared to Webpack
- Better tree-shaking and optimization
- Significantly reduced build times

**2. Stable Partial Prerendering (PPR)**

- PPR is now stable (no longer experimental)
- Mix static and dynamic content seamlessly
- Better performance for hybrid pages
- Improved streaming capabilities

**3. Enhanced Middleware**

- Better performance and reliability
- More flexible routing options
- Improved edge runtime support
- Better error handling

**4. Improved TypeScript Support**

- Enhanced type inference
- Better autocomplete and IntelliSense
- More helpful error messages
- Stricter type checking

**5. React 19 Full Integration**

- Complete optimization for React 19 features
- Enhanced Server Components performance
- Better streaming and Suspense support
- Improved Server Actions

**6. Performance Improvements**

- Faster cold starts
- Reduced memory usage
- Better caching strategies
- Optimized bundle sizes

**7. Developer Experience**

- Improved error messages and debugging
- Better dev server performance
- Enhanced hot module replacement
- Streamlined configuration

### 1.5 Setting Up Next.js

#### Installation

```bash
# Create new Next.js app (latest stable - Next.js 16)
npx create-next-app@latest my-app

# With specific options
npx create-next-app@latest my-app --typescript --tailwind --app --use-npm

# Or with interactive prompts (recommended)
npx create-next-app@latest

# For specific version (Next.js 15)
npx create-next-app@15 my-app
```

#### Project Structure (App Router)

```
my-app/
├── app/
│   ├── layout.tsx          # Root layout
│   ├── page.tsx            # Home page
│   ├── loading.tsx         # Loading UI
│   ├── error.tsx           # Error UI
│   ├── not-found.tsx       # 404 page
│   ├── global.css          # Global styles
│   └── api/                # API routes
│       └── route.ts
├── public/                 # Static assets
├── components/             # React components
├── lib/                    # Utility functions
├── next.config.js          # Next.js config
├── package.json
└── tsconfig.json
```

#### Configuration (next.config.js)

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  // Image domains
  images: {
    remotePatterns: [
      {
        protocol: "https",
        hostname: "example.com",
      },
    ],
  },

  // Experimental features (Next.js 16)
  experimental: {
    ppr: true, // Partial Prerendering (stable in Next.js 16)
    after: true, // Enable next/after API
    reactCompiler: true, // React Compiler (experimental)
  },

  // Environment variables
  env: {
    CUSTOM_KEY: "value",
  },

  // Turbopack (stable for production in Next.js 16)
  // Enabled by default in both dev and production
};

module.exports = nextConfig;
```

#### Important Breaking Changes in Next.js 15

**1. Async Request APIs**

```typescript
// Next.js 14 (synchronous)
import { cookies, headers } from "next/headers";

export default function Page() {
  const cookieStore = cookies();
  const headersList = headers();
}

// Next.js 15 (asynchronous)
import { cookies, headers } from "next/headers";

export default async function Page() {
  const cookieStore = await cookies();
  const headersList = await headers();
}
```

**2. Fetch Caching Changes**

```typescript
// Next.js 14 - cached by default
fetch("https://api.example.com/data");

// Next.js 15 - NOT cached by default
fetch("https://api.example.com/data");

// To cache in Next.js 15
fetch("https://api.example.com/data", { cache: "force-cache" });
```

---

## 2. App Router (Recommended)

### 2.1 App Router vs Pages Router

Next.js 16 supports both App Router (new) and Pages Router (legacy).

#### App Router (Recommended)

**Advantages:**

- Server Components by default
- Improved layouts
- Better data fetching
- Streaming support
- Server Actions
- Parallel routes
- Intercepting routes

**Location:** `app/` directory

#### Pages Router (Legacy)

**Still Supported:**

- Familiar API
- Stable and battle-tested
- Simpler mental model for beginners

**Location:** `pages/` directory

#### Comparison

| Feature           | App Router    | Pages Router       |
| ----------------- | ------------- | ------------------ |
| Server Components | Yes (default) | No                 |
| Layouts           | Nested        | Single             |
| Loading States    | Built-in      | Manual             |
| Error Handling    | Built-in      | Manual             |
| Streaming         | Yes           | Limited            |
| Server Actions    | Yes           | No                 |
| Data Fetching     | async/await   | getServerSideProps |
| File Convention   | page.tsx      | index.tsx          |
| API Routes        | route.ts      | api/\*.ts          |

**Recommendation:** Use App Router for all new projects.

### 2.2 File-based Routing

Next.js uses the file system for routing. Files inside `app/` directory automatically become routes.

#### Special Files

| File            | Purpose                      |
| --------------- | ---------------------------- |
| `layout.tsx`    | Shared UI for a segment      |
| `page.tsx`      | Unique UI for a route        |
| `loading.tsx`   | Loading UI                   |
| `error.tsx`     | Error UI                     |
| `not-found.tsx` | 404 UI                       |
| `template.tsx`  | Re-rendered layout           |
| `route.ts`      | API endpoint                 |
| `default.tsx`   | Fallback for parallel routes |

#### Route Examples

```
app/
├── page.tsx                    → /
├── about/
│   └── page.tsx               → /about
├── blog/
│   ├── page.tsx               → /blog
│   └── [slug]/
│       └── page.tsx           → /blog/:slug
├── dashboard/
│   ├── layout.tsx             → Shared layout
│   ├── page.tsx               → /dashboard
│   ├── settings/
│   │   └── page.tsx           → /dashboard/settings
│   └── analytics/
│       └── page.tsx           → /dashboard/analytics
```

### 2.3 Layouts and Templates

#### Root Layout (Required)

Every app must have a root layout in `app/layout.tsx`:

```typescript
// app/layout.tsx
export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}
```

#### Nested Layouts

Layouts can be nested for shared UI:

```typescript
// app/dashboard/layout.tsx
export default function DashboardLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <div>
      <nav>Dashboard Navigation</nav>
      <main>{children}</main>
    </div>
  );
}
```

#### Templates

Templates re-render on navigation (unlike layouts):

```typescript
// app/template.tsx
export default function Template({ children }: { children: React.ReactNode }) {
  return <div>{children}</div>;
}
```

#### Layout vs Template

| Layout                 | Template                |
| ---------------------- | ----------------------- |
| Persists across routes | Re-renders on each page |
| State is preserved     | State is reset          |
| Better for shared UI   | Better for animations   |
| More performant        | Less performant         |

### 2.4 Route Groups

Route groups organize routes without affecting URL structure.

#### Creating Route Groups

Use parentheses to create route groups:

```
app/
├── (marketing)/
│   ├── about/
│   │   └── page.tsx           → /about
│   └── contact/
│       └── page.tsx           → /contact
├── (shop)/
│   ├── products/
│   │   └── page.tsx           → /products
│   └── cart/
│       └── page.tsx           → /cart
└── page.tsx                   → /
```

#### Use Cases

1. **Organize routes by section**
2. **Multiple root layouts**
3. **Opt specific routes into layouts**

### 2.5 Dynamic Routes

Dynamic routes use square brackets for parameters.

#### Single Dynamic Segment

```typescript
// app/blog/[slug]/page.tsx
export default function BlogPost({ params }: { params: { slug: string } }) {
  return <div>Post: {params.slug}</div>;
}

// Generates: /blog/hello-world, /blog/nextjs-guide
```

#### Multiple Dynamic Segments

```typescript
// app/shop/[category]/[product]/page.tsx
export default function Product({
  params,
}: {
  params: { category: string; product: string };
}) {
  return (
    <div>
      Category: {params.category}, Product: {params.product}
    </div>
  );
}

// Generates: /shop/electronics/laptop
```

#### Catch-all Segments

```typescript
// app/docs/[...slug]/page.tsx
export default function Docs({ params }: { params: { slug: string[] } }) {
  return <div>Docs: {params.slug.join("/")}</div>;
}

// Matches: /docs/a, /docs/a/b, /docs/a/b/c
```

#### Optional Catch-all Segments

```typescript
// app/shop/[[...slug]]/page.tsx
// Matches: /shop, /shop/a, /shop/a/b
```

#### Generating Static Params

```typescript
// app/blog/[slug]/page.tsx
export async function generateStaticParams() {
  const posts = await getPosts();

  return posts.map((post) => ({
    slug: post.slug,
  }));
}

export default function BlogPost({ params }: { params: { slug: string } }) {
  return <div>Post: {params.slug}</div>;
}
```

### 2.6 Parallel Routes

Parallel routes allow rendering multiple pages in the same layout simultaneously.

#### Creating Parallel Routes

Use `@folder` convention:

```
app/
├── layout.tsx
├── page.tsx
├── @analytics/
│   └── page.tsx
└── @team/
    └── page.tsx
```

#### Using Parallel Routes

```typescript
// app/layout.tsx
export default function Layout({
  children,
  analytics,
  team,
}: {
  children: React.ReactNode;
  analytics: React.ReactNode;
  team: React.ReactNode;
}) {
  return (
    <>
      {children}
      {analytics}
      {team}
    </>
  );
}
```

#### Use Cases

- Dashboards with multiple sections
- Modals
- Conditional rendering based on route

### 2.7 Intercepting Routes

Intercepting routes allow loading a route within the current layout while keeping context.

#### Convention

Use `(..)` to intercept routes:

- `(.)` - same level
- `(..)` - one level up
- `(..)(..)` - two levels up
- `(...)` - from root

#### Example: Modal

```
app/
├── page.tsx
├── @modal/
│   └── (.)photo/
│       └── [id]/
│           └── page.tsx
└── photo/
    └── [id]/
        └── page.tsx
```

```typescript
// app/@modal/(.)photo/[id]/page.tsx
export default function PhotoModal({ params }: { params: { id: string } }) {
  return <Modal>Photo {params.id}</Modal>;
}
```

### 2.8 Route Handlers (API Routes)

Route handlers create API endpoints using `route.ts` files.

#### Basic Route Handler

```typescript
// app/api/hello/route.ts
export async function GET(request: Request) {
  return Response.json({ message: "Hello World" });
}
```

#### HTTP Methods

```typescript
// app/api/posts/route.ts
export async function GET(request: Request) {
  const posts = await getPosts();
  return Response.json(posts);
}

export async function POST(request: Request) {
  const body = await request.json();
  const post = await createPost(body);
  return Response.json(post, { status: 201 });
}

export async function PUT(request: Request) {
  const body = await request.json();
  const post = await updatePost(body);
  return Response.json(post);
}

export async function DELETE(request: Request) {
  await deletePost();
  return new Response(null, { status: 204 });
}
```

#### Dynamic Route Handlers

```typescript
// app/api/posts/[id]/route.ts
export async function GET(
  request: Request,
  { params }: { params: { id: string } }
) {
  const post = await getPost(params.id);
  return Response.json(post);
}
```

#### Request Object

```typescript
export async function GET(request: Request) {
  // URL
  const url = new URL(request.url);
  const searchParams = url.searchParams;
  const query = searchParams.get("query");

  // Headers
  const authorization = request.headers.get("authorization");

  // Cookies
  const { cookies } = await import("next/headers");
  const token = cookies().get("token");

  return Response.json({ query, authorization });
}
```

#### Response Options

```typescript
export async function GET() {
  return Response.json(
    { message: "Success" },
    {
      status: 200,
      headers: {
        "Content-Type": "application/json",
        "Cache-Control": "public, s-maxage=60, stale-while-revalidate=30",
      },
    }
  );
}
```

---

## 3. Server Components & Client Components

### 3.1 React Server Components (RSC)

Server Components are the default in Next.js 16 App Router. They render on the server and send HTML to the client.

#### Characteristics

- **Zero JavaScript:** No JavaScript sent to client
- **Direct Backend Access:** Can access databases, file system
- **Secure:** API keys and secrets stay on server
- **Better Performance:** Smaller bundle size
- **SEO-Friendly:** Fully rendered HTML

#### Server Component Example

```typescript
// app/posts/page.tsx (Server Component by default)
async function getPosts() {
  const res = await fetch("https://api.example.com/posts");
  return res.json();
}

export default async function PostsPage() {
  const posts = await getPosts();

  return (
    <div>
      {posts.map((post) => (
        <div key={post.id}>{post.title}</div>
      ))}
    </div>
  );
}
```

#### What You CAN Do in Server Components

- Fetch data
- Access backend resources directly
- Keep sensitive information on server
- Use async/await
- Import server-only code

#### What You CANNOT Do in Server Components

- Use React hooks (useState, useEffect, etc.)
- Use browser APIs (window, document)
- Add event listeners (onClick, onChange)
- Use Context API
- Use browser-only libraries

### 3.2 Client Components

Client Components render on the client and have access to browser APIs and React hooks.

#### Creating Client Components

Use `"use client"` directive at the top of the file:

```typescript
"use client";

import { useState } from "react";

export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

#### When to Use Client Components

- Need interactivity (onClick, onChange)
- Need React hooks (useState, useEffect)
- Need browser APIs (localStorage, geolocation)
- Need real-time updates
- Need third-party libraries that use hooks

### 3.3 When to Use Server vs Client

| Use Server Component                | Use Client Component |
| ----------------------------------- | -------------------- |
| Fetch data                          | Add interactivity    |
| Access backend resources            | Use React hooks      |
| Keep sensitive info on server       | Use browser APIs     |
| Large dependencies (keep on server) | Use event listeners  |
| SEO-critical content                | Use Context API      |
| Static content                      | Real-time updates    |

#### Best Practice: Server by Default

Start with Server Components and only use `"use client"` when needed.

### 3.4 Composition Patterns

#### Pattern 1: Pass Server Components to Client Components

```typescript
// app/page.tsx (Server Component)
import ClientComponent from "./ClientComponent";
import ServerComponent from "./ServerComponent";

export default function Page() {
  return (
    <ClientComponent>
      <ServerComponent />
    </ClientComponent>
  );
}
```

```typescript
// ClientComponent.tsx
"use client";

export default function ClientComponent({
  children,
}: {
  children: React.ReactNode;
}) {
  return <div>{children}</div>;
}
```

#### Pattern 2: Pass Server Data to Client Components

```typescript
// app/page.tsx (Server Component)
import ClientComponent from "./ClientComponent";

async function getData() {
  const res = await fetch("https://api.example.com/data");
  return res.json();
}

export default async function Page() {
  const data = await getData();
  return <ClientComponent data={data} />;
}
```

#### Pattern 3: Interleaving Server and Client Components

```typescript
// Server Component
import ClientNav from "./ClientNav";

export default async function Layout({ children }) {
  const user = await getUser();

  return (
    <div>
      <ClientNav user={user} />
      {children}
    </div>
  );
}
```

### 3.5 Server Actions

Server Actions are asynchronous functions that run on the server and can be called from Client Components.

#### Creating Server Actions

```typescript
// app/actions.ts
"use server";

export async function createPost(formData: FormData) {
  const title = formData.get("title");
  const content = formData.get("content");

  // Database operation
  await db.post.create({
    data: { title, content },
  });

  revalidatePath("/posts");
}
```

#### Using Server Actions in Forms

```typescript
// app/posts/new/page.tsx
import { createPost } from "@/app/actions";

export default function NewPost() {
  return (
    <form action={createPost}>
      <input name="title" type="text" required />
      <textarea name="content" required />
      <button type="submit">Create Post</button>
    </form>
  );
}
```

#### Using Server Actions in Client Components

```typescript
"use client";

import { createPost } from "@/app/actions";
import { useFormStatus } from "react-dom";

export default function PostForm() {
  const { pending } = useFormStatus();

  return (
    <form action={createPost}>
      <input name="title" type="text" />
      <button disabled={pending}>{pending ? "Creating..." : "Create"}</button>
    </form>
  );
}
```

#### Server Actions with useTransition

```typescript
"use client";

import { useTransition } from "react";
import { deletePost } from "@/app/actions";

export default function DeleteButton({ id }: { id: string }) {
  const [isPending, startTransition] = useTransition();

  return (
    <button
      onClick={() => startTransition(() => deletePost(id))}
      disabled={isPending}
    >
      {isPending ? "Deleting..." : "Delete"}
    </button>
  );
}
```

#### Server Actions Best Practices

1. **Validation:** Always validate input on server
2. **Error Handling:** Use try-catch blocks
3. **Revalidation:** Revalidate cache after mutations
4. **Security:** Check authentication/authorization
5. **Type Safety:** Use TypeScript for type safety

---

## 4. Rendering Strategies

### 4.1 Static Rendering (SSG)

Static rendering generates HTML at build time. Pages are pre-rendered and cached.

#### Characteristics

- **Fastest:** Served from CDN
- **SEO-Friendly:** Fully rendered HTML
- **Scalable:** No server load per request
- **Best for:** Marketing pages, blogs, documentation

#### Static Rendering Example

```typescript
// app/posts/page.tsx
async function getPosts() {
  const res = await fetch("https://api.example.com/posts");
  return res.json();
}

export default async function PostsPage() {
  const posts = await getPosts();
  return <div>{/* Render posts */}</div>;
}
```

#### Force Static Rendering

```typescript
export const dynamic = "force-static";
```

### 4.2 Dynamic Rendering (SSR)

Dynamic rendering generates HTML on each request.

#### Characteristics

- **Fresh Data:** Always up-to-date
- **Personalized:** User-specific content
- **Slower:** Server renders on each request
- **Best for:** Dashboards, user profiles, real-time data

#### Dynamic Rendering Triggers

Next.js automatically switches to dynamic rendering when:

1. Using dynamic functions (`cookies()`, `headers()`, `searchParams`)
2. Using `fetch()` with `cache: 'no-store'`
3. Using `revalidate: 0`

#### Dynamic Rendering Example

```typescript
// app/dashboard/page.tsx
import { cookies } from "next/headers";

export default async function Dashboard() {
  const cookieStore = cookies();
  const user = cookieStore.get("user");

  return <div>Welcome {user?.value}</div>;
}
```

#### Force Dynamic Rendering

```typescript
export const dynamic = "force-dynamic";
export const revalidate = 0;
```

### 4.3 Streaming

Streaming allows progressively rendering UI from the server.

#### Benefits

- **Faster Initial Load:** Show content as it's ready
- **Better UX:** Progressive loading
- **Reduced TTFB:** Time to First Byte

#### Streaming with Suspense

```typescript
// app/posts/page.tsx
import { Suspense } from "react";

async function Posts() {
  const posts = await getPosts(); // Slow
  return <div>{/* Render posts */}</div>;
}

export default function PostsPage() {
  return (
    <div>
      <h1>Posts</h1>
      <Suspense fallback={<div>Loading posts...</div>}>
        <Posts />
      </Suspense>
    </div>
  );
}
```

#### Loading.tsx for Streaming

```typescript
// app/posts/loading.tsx
export default function Loading() {
  return <div>Loading posts...</div>;
}
```

#### Streaming Multiple Components

```typescript
export default function Dashboard() {
  return (
    <div>
      <Suspense fallback={<Skeleton />}>
        <Analytics />
      </Suspense>
      <Suspense fallback={<Skeleton />}>
        <RecentOrders />
      </Suspense>
      <Suspense fallback={<Skeleton />}>
        <UserStats />
      </Suspense>
    </div>
  );
}
```

### 4.4 Incremental Static Regeneration (ISR)

ISR allows updating static pages after build without rebuilding the entire site.

#### Time-based Revalidation

```typescript
// app/posts/page.tsx
async function getPosts() {
  const res = await fetch("https://api.example.com/posts", {
    next: { revalidate: 60 }, // Revalidate every 60 seconds
  });
  return res.json();
}

export default async function PostsPage() {
  const posts = await getPosts();
  return <div>{/* Render posts */}</div>;
}
```

#### On-Demand Revalidation

```typescript
// app/api/revalidate/route.ts
import { revalidatePath, revalidateTag } from "next/cache";

export async function POST(request: Request) {
  const path = request.nextUrl.searchParams.get("path");

  if (path) {
    revalidatePath(path);
    return Response.json({ revalidated: true, now: Date.now() });
  }

  return Response.json({ revalidated: false, now: Date.now() });
}
```

#### Tag-based Revalidation

```typescript
// Fetch with tag
fetch("https://api.example.com/posts", {
  next: { tags: ["posts"] },
});

// Revalidate by tag
revalidateTag("posts");
```

### 4.5 Partial Prerendering (PPR)

PPR (Stable in Next.js 16) combines static and dynamic rendering in the same route.

#### Enabling PPR

```javascript
// next.config.js
module.exports = {
  experimental: {
    ppr: true,
  },
};
```

#### Using PPR

```typescript
// app/page.tsx
export const experimental_ppr = true;

export default function Page() {
  return (
    <div>
      {/* Static content */}
      <Header />

      {/* Dynamic content wrapped in Suspense */}
      <Suspense fallback={<Skeleton />}>
        <DynamicContent />
      </Suspense>

      {/* Static content */}
      <Footer />
    </div>
  );
}
```

#### Benefits

- **Best of Both Worlds:** Fast static shell + dynamic content
- **Improved Performance:** Static parts served instantly
- **Better UX:** Progressive enhancement

---

## 5. Data Fetching

### 5.1 Server-Side Data Fetching

#### Basic Fetch

```typescript
// app/posts/page.tsx
async function getPosts() {
  const res = await fetch("https://api.example.com/posts");

  if (!res.ok) {
    throw new Error("Failed to fetch posts");
  }

  return res.json();
}

export default async function PostsPage() {
  const posts = await getPosts();
  return <div>{/* Render posts */}</div>;
}
```

#### Fetch with Options

```typescript
async function getPosts() {
  const res = await fetch("https://api.example.com/posts", {
    // Cache options
    cache: "force-cache", // Default: cache
    // cache: 'no-store',     // Dynamic rendering

    // Revalidation
    next: {
      revalidate: 60, // Revalidate every 60 seconds
      tags: ["posts"], // Tag for on-demand revalidation
    },

    // Standard fetch options
    headers: {
      "Content-Type": "application/json",
    },
  });

  return res.json();
}
```

#### Direct Database Access

```typescript
// app/posts/page.tsx
import { db } from "@/lib/db";

export default async function PostsPage() {
  const posts = await db.post.findMany();
  return <div>{/* Render posts */}</div>;
}
```

### 5.2 Client-Side Data Fetching

#### Using useEffect

```typescript
"use client";

import { useState, useEffect } from "react";

export default function Posts() {
  const [posts, setPosts] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch("/api/posts")
      .then((res) => res.json())
      .then((data) => {
        setPosts(data);
        setLoading(false);
      });
  }, []);

  if (loading) return <div>Loading...</div>;
  return <div>{/* Render posts */}</div>;
}
```

#### Using SWR

```typescript
"use client";

import useSWR from "swr";

const fetcher = (url: string) => fetch(url).then((res) => res.json());

export default function Posts() {
  const { data, error, isLoading } = useSWR("/api/posts", fetcher);

  if (error) return <div>Failed to load</div>;
  if (isLoading) return <div>Loading...</div>;

  return <div>{/* Render posts */}</div>;
}
```

#### Using React Query

```typescript
"use client";

import { useQuery } from "@tanstack/react-query";

export default function Posts() {
  const { data, isLoading, error } = useQuery({
    queryKey: ["posts"],
    queryFn: () => fetch("/api/posts").then((res) => res.json()),
  });

  if (isLoading) return <div>Loading...</div>;
  if (error) return <div>Error loading posts</div>;

  return <div>{/* Render posts */}</div>;
}
```

### 5.3 Caching Strategies

#### Cache Options

```typescript
// Force cache (default)
fetch(url, { cache: "force-cache" });

// No cache (dynamic)
fetch(url, { cache: "no-store" });

// Revalidate
fetch(url, { next: { revalidate: 60 } });

// Tag-based
fetch(url, { next: { tags: ["posts"] } });
```

#### Cache Levels

1. **Request Memoization:** Deduplicates requests in a single render
2. **Data Cache:** Persistent cache across requests
3. **Full Route Cache:** Caches entire route
4. **Router Cache:** Client-side cache

### 5.4 Revalidation

#### Time-based Revalidation

```typescript
// Revalidate every 60 seconds
export const revalidate = 60;

// Or per-fetch
fetch(url, { next: { revalidate: 60 } });
```

#### On-Demand Revalidation

```typescript
import { revalidatePath, revalidateTag } from "next/cache";

// Revalidate specific path
revalidatePath("/posts");
revalidatePath("/posts/[slug]", "page");

// Revalidate by tag
revalidateTag("posts");
```

### 5.5 Parallel and Sequential Data Fetching

#### Sequential (Waterfall)

```typescript
async function Page() {
  const user = await getUser();
  const posts = await getPosts(user.id); // Waits for user

  return <div>{/* Render */}</div>;
}
```

#### Parallel

```typescript
async function Page() {
  const [user, posts] = await Promise.all([getUser(), getPosts()]);

  return <div>{/* Render */}</div>;
}
```

#### Preloading

```typescript
// lib/data.ts
import { cache } from "react";

export const getUser = cache(async (id: string) => {
  // Fetch user
});

// Preload in parent
async function Page() {
  getUser("123"); // Starts fetching
  return <UserProfile userId="123" />;
}

// Use in child
async function UserProfile({ userId }) {
  const user = await getUser(userId); // Uses cached result
  return <div>{user.name}</div>;
}
```

---

## 6. Caching

### 6.1 Request Memoization

Automatic deduplication of fetch requests during a single render.

#### How It Works

```typescript
// These will only make ONE request
async function Page() {
  const data1 = await fetch("https://api.example.com/data");
  const data2 = await fetch("https://api.example.com/data"); // Memoized
  const data3 = await fetch("https://api.example.com/data"); // Memoized

  return <div>...</div>;
}
```

#### Manual Memoization with React cache

```typescript
import { cache } from "react";

export const getUser = cache(async (id: string) => {
  const user = await db.user.findUnique({ where: { id } });
  return user;
});
```

### 6.2 Data Cache

Persistent cache for fetch requests across requests and deployments.

#### Default Behavior

```typescript
// Cached by default
fetch("https://api.example.com/data");

// Equivalent to
fetch("https://api.example.com/data", { cache: "force-cache" });
```

#### Opt Out of Caching

```typescript
// No cache
fetch("https://api.example.com/data", { cache: "no-store" });
```

#### Revalidation

```typescript
// Time-based
fetch("https://api.example.com/data", { next: { revalidate: 3600 } });

// Tag-based
fetch("https://api.example.com/data", { next: { tags: ["posts"] } });
```

### 6.3 Full Route Cache

Next.js caches the rendered result of routes at build time.

#### Static Routes (Cached)

```typescript
// Automatically cached
export default async function Page() {
  const data = await fetch("https://api.example.com/data");
  return <div>{/* Render */}</div>;
}
```

#### Dynamic Routes (Not Cached)

```typescript
// Not cached (uses dynamic function)
import { cookies } from "next/headers";

export default async function Page() {
  const cookieStore = cookies();
  return <div>{/* Render */}</div>;
}
```

#### Opt Out

```typescript
export const dynamic = "force-dynamic";
export const revalidate = 0;
```

### 6.4 Router Cache

Client-side cache for visited routes.

#### Characteristics

- **Automatic:** Caches visited routes
- **Temporary:** Cleared on page refresh
- **Prefetching:** Prefetches linked routes

#### Invalidation

```typescript
// Manual invalidation
import { useRouter } from "next/navigation";

const router = useRouter();
router.refresh(); // Invalidates router cache
```

### 6.5 Cache Configuration

#### Route Segment Config

```typescript
// app/posts/page.tsx
export const dynamic = "auto"; // 'auto' | 'force-dynamic' | 'error' | 'force-static'
export const dynamicParams = true; // true | false
export const revalidate = false; // false | 0 | number
export const fetchCache = "auto"; // 'auto' | 'default-cache' | 'only-cache' | 'force-cache' | 'force-no-store' | 'default-no-store' | 'only-no-store'
export const runtime = "nodejs"; // 'nodejs' | 'edge'
export const preferredRegion = "auto"; // 'auto' | 'global' | 'home' | string | string[]
```

#### Cache Control Headers

```typescript
// app/api/data/route.ts
export async function GET() {
  return Response.json(
    { data: "..." },
    {
      headers: {
        "Cache-Control": "public, s-maxage=60, stale-while-revalidate=30",
      },
    }
  );
}
```

---

## 7. Metadata and SEO

### 7.1 Static Metadata

Define metadata for SEO using the `metadata` export.

#### Basic Metadata

```typescript
// app/page.tsx
import type { Metadata } from "next";

export const metadata: Metadata = {
  title: "My App",
  description: "Description of my app",
  keywords: ["next.js", "react", "typescript"],
};

export default function Page() {
  return <div>...</div>;
}
```

#### Complete Metadata

```typescript
export const metadata: Metadata = {
  title: "My App",
  description: "Description",
  keywords: ["keyword1", "keyword2"],
  authors: [{ name: "John Doe", url: "https://example.com" }],
  creator: "John Doe",
  publisher: "Publisher Name",
  robots: {
    index: true,
    follow: true,
    googleBot: {
      index: true,
      follow: true,
    },
  },
  icons: {
    icon: "/favicon.ico",
    apple: "/apple-icon.png",
  },
  manifest: "/manifest.json",
  openGraph: {
    title: "My App",
    description: "Description",
    url: "https://example.com",
    siteName: "My App",
    images: [
      {
        url: "https://example.com/og.png",
        width: 1200,
        height: 630,
      },
    ],
    locale: "en_US",
    type: "website",
  },
  twitter: {
    card: "summary_large_image",
    title: "My App",
    description: "Description",
    images: ["https://example.com/og.png"],
    creator: "@username",
  },
};
```

### 7.2 Dynamic Metadata

Generate metadata dynamically based on route parameters.

#### generateMetadata Function

```typescript
// app/posts/[slug]/page.tsx
import type { Metadata } from "next";

export async function generateMetadata({
  params,
}: {
  params: { slug: string };
}): Promise<Metadata> {
  const post = await getPost(params.slug);

  return {
    title: post.title,
    description: post.excerpt,
    openGraph: {
      title: post.title,
      description: post.excerpt,
      images: [post.image],
    },
  };
}

export default function Post({ params }: { params: { slug: string } }) {
  return <div>...</div>;
}
```

#### Template Titles

```typescript
// app/layout.tsx
export const metadata = {
  title: {
    template: "%s | My App",
    default: "My App",
  },
};

// app/posts/page.tsx
export const metadata = {
  title: "Posts", // Becomes "Posts | My App"
};
```

### 7.3 Open Graph and Twitter Cards

#### Open Graph

```typescript
export const metadata = {
  openGraph: {
    title: "My App",
    description: "Description",
    url: "https://example.com",
    siteName: "My App",
    images: [
      {
        url: "https://example.com/og.png",
        width: 1200,
        height: 630,
        alt: "My App Preview",
      },
    ],
    locale: "en_US",
    type: "website",
  },
};
```

#### Twitter Cards

```typescript
export const metadata = {
  twitter: {
    card: "summary_large_image",
    title: "My App",
    description: "Description",
    siteId: "123456789",
    creator: "@username",
    creatorId: "123456789",
    images: ["https://example.com/twitter.png"],
  },
};
```

### 7.4 JSON-LD

Structured data for search engines.

```typescript
// app/posts/[slug]/page.tsx
export default function Post({ params }: { params: { slug: string } }) {
  const jsonLd = {
    "@context": "https://schema.org",
    "@type": "Article",
    headline: "Article Title",
    image: "https://example.com/image.jpg",
    datePublished: "2024-01-01",
    author: {
      "@type": "Person",
      name: "John Doe",
    },
  };

  return (
    <>
      <script
        type="application/ld+json"
        dangerouslySetInnerHTML={{ __html: JSON.stringify(jsonLd) }}
      />
      <article>...</article>
    </>
  );
}
```

### 7.5 Sitemap and Robots

#### Sitemap

```typescript
// app/sitemap.ts
import { MetadataRoute } from "next";

export default function sitemap(): MetadataRoute.Sitemap {
  return [
    {
      url: "https://example.com",
      lastModified: new Date(),
      changeFrequency: "yearly",
      priority: 1,
    },
    {
      url: "https://example.com/about",
      lastModified: new Date(),
      changeFrequency: "monthly",
      priority: 0.8,
    },
  ];
}
```

#### Dynamic Sitemap

```typescript
// app/sitemap.ts
export default async function sitemap(): Promise<MetadataRoute.Sitemap> {
  const posts = await getPosts();

  const postUrls = posts.map((post) => ({
    url: `https://example.com/posts/${post.slug}`,
    lastModified: post.updatedAt,
  }));

  return [
    {
      url: "https://example.com",
      lastModified: new Date(),
    },
    ...postUrls,
  ];
}
```

#### Robots.txt

```typescript
// app/robots.ts
import { MetadataRoute } from "next";

export default function robots(): MetadataRoute.Robots {
  return {
    rules: {
      userAgent: "*",
      allow: "/",
      disallow: "/private/",
    },
    sitemap: "https://example.com/sitemap.xml",
  };
}
```

---

## 8. Styling

### 8.1 CSS Modules

Locally scoped CSS by default.

```typescript
// app/page.module.css
.container {
  padding: 20px;
  background: white;
}

.title {
  color: blue;
}
```

```typescript
// app/page.tsx
import styles from "./page.module.css";

export default function Page() {
  return (
    <div className={styles.container}>
      <h1 className={styles.title}>Hello</h1>
    </div>
  );
}
```

### 8.2 Tailwind CSS

Utility-first CSS framework.

#### Installation

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

#### Configuration

```javascript
// tailwind.config.js
module.exports = {
  content: [
    "./app/**/*.{js,ts,jsx,tsx,mdx}",
    "./components/**/*.{js,ts,jsx,tsx,mdx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

```css
/* app/globals.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

#### Usage

```typescript
export default function Page() {
  return (
    <div className="container mx-auto px-4">
      <h1 className="text-3xl font-bold text-blue-600">Hello</h1>
    </div>
  );
}
```

### 8.3 CSS-in-JS

#### Styled-JSX (Built-in)

```typescript
export default function Page() {
  return (
    <div>
      <h1>Hello</h1>
      <style jsx>{`
        h1 {
          color: blue;
          font-size: 24px;
        }
      `}</style>
    </div>
  );
}
```

#### Styled-Components

```typescript
"use client";

import styled from "styled-components";

const Title = styled.h1`
  color: blue;
  font-size: 24px;
`;

export default function Page() {
  return <Title>Hello</Title>;
}
```

### 8.4 Sass

```bash
npm install sass
```

```scss
// app/page.module.scss
.container {
  padding: 20px;

  .title {
    color: blue;
  }
}
```

### 8.5 Global Styles

```css
/* app/globals.css */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
}
```

```typescript
// app/layout.tsx
import "./globals.css";

export default function RootLayout({ children }) {
  return (
    <html>
      <body>{children}</body>
    </html>
  );
}
```

---

## 9. Images and Fonts

### 9.1 Next.js Image Component

Automatic image optimization with the `<Image>` component.

#### Basic Usage

```typescript
import Image from "next/image";

export default function Page() {
  return (
    <Image
      src="/profile.jpg"
      alt="Profile"
      width={500}
      height={500}
      priority // Load immediately
    />
  );
}
```

#### Remote Images

```typescript
// next.config.js
module.exports = {
  images: {
    remotePatterns: [
      {
        protocol: "https",
        hostname: "example.com",
      },
    ],
  },
};
```

```typescript
<Image
  src="https://example.com/image.jpg"
  alt="Remote"
  width={500}
  height={500}
/>
```

#### Fill Container

```typescript
<div style={{ position: "relative", width: "100%", height: "400px" }}>
  <Image src="/image.jpg" alt="Image" fill style={{ objectFit: "cover" }} />
</div>
```

### 9.2 Image Optimization

#### Responsive Images

```typescript
<Image
  src="/image.jpg"
  alt="Responsive"
  width={800}
  height={600}
  sizes="(max-width: 768px) 100vw, (max-width: 1200px) 50vw, 33vw"
/>
```

#### Quality

```typescript
<Image src="/image.jpg" alt="Image" width={500} height={500} quality={75} />
```

#### Placeholder

```typescript
<Image
  src="/image.jpg"
  alt="Image"
  width={500}
  height={500}
  placeholder="blur"
  blurDataURL="data:image/jpeg;base64,..."
/>
```

### 9.3 Font Optimization

Next.js automatically optimizes fonts with `next/font`.

#### Google Fonts

```typescript
// app/layout.tsx
import { Inter, Roboto_Mono } from "next/font/google";

const inter = Inter({
  subsets: ["latin"],
  display: "swap",
});

const robotoMono = Roboto_Mono({
  subsets: ["latin"],
  display: "swap",
});

export default function RootLayout({ children }) {
  return (
    <html lang="en" className={inter.className}>
      <body>{children}</body>
    </html>
  );
}
```

#### Variable Fonts

```typescript
import { Inter } from "next/font/google";

const inter = Inter({
  subsets: ["latin"],
  variable: "--font-inter",
});

export default function RootLayout({ children }) {
  return (
    <html lang="en" className={inter.variable}>
      <body>{children}</body>
    </html>
  );
}
```

```css
/* globals.css */
body {
  font-family: var(--font-inter);
}
```

### 9.4 Local Fonts

```typescript
import localFont from "next/font/local";

const myFont = localFont({
  src: "./my-font.woff2",
  display: "swap",
});

export default function RootLayout({ children }) {
  return (
    <html lang="en" className={myFont.className}>
      <body>{children}</body>
    </html>
  );
}
```

---

## 10. Navigation and Linking

### 10.1 Link Component

Client-side navigation without page reload.

#### Basic Link

```typescript
import Link from "next/link";

export default function Page() {
  return <Link href="/about">About</Link>;
}
```

#### Dynamic Links

```typescript
<Link href={`/posts/${post.slug}`}>{post.title}</Link>
```

#### Prefetching

```typescript
// Prefetch on hover (default)
<Link href="/about" prefetch={true}>About</Link>

// No prefetch
<Link href="/about" prefetch={false}>About</Link>
```

#### Replace History

```typescript
<Link href="/login" replace>
  Login
</Link>
```

### 10.2 useRouter Hook

Programmatic navigation in Client Components.

```typescript
"use client";

import { useRouter } from "next/navigation";

export default function Page() {
  const router = useRouter();

  return (
    <button onClick={() => router.push("/dashboard")}>Go to Dashboard</button>
  );
}
```

#### Router Methods

```typescript
const router = useRouter();

// Navigate
router.push("/dashboard");
router.replace("/login");
router.back();
router.forward();

// Refresh
router.refresh(); // Re-fetch server data

// Prefetch
router.prefetch("/dashboard");
```

### 10.3 usePathname and useSearchParams

#### usePathname

```typescript
"use client";

import { usePathname } from "next/navigation";

export default function Nav() {
  const pathname = usePathname();

  return (
    <nav>
      <Link href="/" className={pathname === "/" ? "active" : ""}>
        Home
      </Link>
      <Link href="/about" className={pathname === "/about" ? "active" : ""}>
        About
      </Link>
    </nav>
  );
}
```

#### useSearchParams

```typescript
"use client";

import { useSearchParams } from "next/navigation";

export default function Search() {
  const searchParams = useSearchParams();
  const query = searchParams.get("q");

  return <div>Search: {query}</div>;
}
```

### 10.4 Redirects

#### Server Component Redirect

```typescript
import { redirect } from "next/navigation";

export default async function Page() {
  const user = await getUser();

  if (!user) {
    redirect("/login");
  }

  return <div>Dashboard</div>;
}
```

#### Permanent Redirect

```typescript
import { permanentRedirect } from "next/navigation";

export default function Page() {
  permanentRedirect("https://newdomain.com");
}
```

#### next.config.js Redirects

```javascript
module.exports = {
  async redirects() {
    return [
      {
        source: "/old-path",
        destination: "/new-path",
        permanent: true,
      },
      {
        source: "/blog/:slug",
        destination: "/posts/:slug",
        permanent: false,
      },
    ];
  },
};
```

### 10.5 Proxy (Replaces Middleware)

Run code before a request is completed.

> **Breaking Change in Next.js 16:** `middleware.ts` has been replaced by `proxy.ts` in the root directory. The API remains similar but with improved performance and capabilities.

#### Basic Proxy

```typescript
// proxy.ts (root directory)
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function proxy(request: NextRequest) {
  // Check authentication
  const token = request.cookies.get("token");

  if (!token && request.nextUrl.pathname.startsWith("/dashboard")) {
    return NextResponse.redirect(new URL("/login", request.url));
  }

  return NextResponse.next();
}

export const config = {
  matcher: ["/dashboard/:path*", "/admin/:path*"],
};
```

#### Migration from middleware.ts to proxy.ts

```typescript
// Old: middleware.ts (Next.js 15)
export function middleware(request: NextRequest) {
  // ...
}

// New: proxy.ts (Next.js 16)
export function proxy(request: NextRequest) {
  // Same logic, just rename the file and function
}
```

#### Advanced Proxy Examples

**1. Authentication & Authorization**

```typescript
// proxy.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";
import { verifyToken } from "@/lib/auth";

export async function proxy(request: NextRequest) {
  const token = request.cookies.get("token")?.value;
  const { pathname } = request.nextUrl;

  // Public routes
  if (pathname.startsWith("/login") || pathname.startsWith("/register")) {
    return NextResponse.next();
  }

  // Protected routes
  if (pathname.startsWith("/dashboard")) {
    if (!token) {
      return NextResponse.redirect(new URL("/login", request.url));
    }

    try {
      const user = await verifyToken(token);

      // Add user info to headers
      const response = NextResponse.next();
      response.headers.set("x-user-id", user.id);
      return response;
    } catch (error) {
      return NextResponse.redirect(new URL("/login", request.url));
    }
  }

  return NextResponse.next();
}

export const config = {
  matcher: ["/dashboard/:path*", "/admin/:path*", "/login", "/register"],
};
```

**2. Internationalization (i18n)**

```typescript
// proxy.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

const locales = ["en", "es", "fr"];
const defaultLocale = "en";

export function proxy(request: NextRequest) {
  const pathname = request.nextUrl.pathname;

  // Check if pathname has locale
  const pathnameHasLocale = locales.some(
    (locale) => pathname.startsWith(`/${locale}/`) || pathname === `/${locale}`
  );

  if (pathnameHasLocale) return NextResponse.next();

  // Redirect to locale
  const locale = request.cookies.get("locale")?.value || defaultLocale;
  request.nextUrl.pathname = `/${locale}${pathname}`;
  return NextResponse.redirect(request.nextUrl);
}

export const config = {
  matcher: ["/((?!api|_next/static|_next/image|favicon.ico).*)"],
};
```

**3. A/B Testing**

```typescript
// proxy.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function proxy(request: NextRequest) {
  const pathname = request.nextUrl.pathname;

  if (pathname === "/") {
    // Check for existing variant
    let variant = request.cookies.get("variant")?.value;

    if (!variant) {
      // Randomly assign variant
      variant = Math.random() < 0.5 ? "A" : "B";
    }

    const response = NextResponse.rewrite(
      new URL(`/variants/${variant}`, request.url)
    );
    response.cookies.set("variant", variant);
    return response;
  }

  return NextResponse.next();
}
```

**4. Rate Limiting**

```typescript
// proxy.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";
import { Ratelimit } from "@upstash/ratelimit";
import { Redis } from "@upstash/redis";

const ratelimit = new Ratelimit({
  redis: Redis.fromEnv(),
  limiter: Ratelimit.slidingWindow(10, "10 s"),
});

export async function proxy(request: NextRequest) {
  const ip = request.ip ?? "127.0.0.1";
  const { success } = await ratelimit.limit(ip);

  if (!success) {
    return NextResponse.json({ error: "Too many requests" }, { status: 429 });
  }

  return NextResponse.next();
}

export const config = {
  matcher: "/api/:path*",
};
```

**5. Custom Headers**

```typescript
// proxy.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function proxy(request: NextRequest) {
  const response = NextResponse.next();

  // Security headers
  response.headers.set("X-Frame-Options", "DENY");
  response.headers.set("X-Content-Type-Options", "nosniff");
  response.headers.set("Referrer-Policy", "origin-when-cross-origin");
  response.headers.set(
    "Permissions-Policy",
    "camera=(), microphone=(), geolocation=()"
  );

  return response;
}
```

#### Proxy Configuration

**Matcher Options:**

```typescript
export const config = {
  // Match specific paths
  matcher: ["/dashboard/:path*", "/admin/:path*"],

  // Match all except specific paths
  matcher: ["/((?!api|_next/static|_next/image|favicon.ico).*)"],

  // Multiple matchers
  matcher: [
    "/dashboard/:path*",
    "/admin/:path*",
    "/((?!api|_next/static|_next/image).*)",
  ],
};
```

#### Proxy Execution Order

1. `headers` from `next.config.js`
2. `redirects` from `next.config.js`
3. Proxy (`rewrites`, `redirects`, etc.)
4. `beforeFiles` (`rewrites`) from `next.config.js`
5. Filesystem routes (`public/`, `_next/static/`, Pages, etc.)
6. `afterFiles` (`rewrites`) from `next.config.js`
7. Dynamic Routes (`/blog/[slug]`)
8. `fallback` (`rewrites`) from `next.config.js`

#### Proxy Use Cases

- **Authentication:** Protect routes, verify tokens
- **Redirects:** Conditional redirects based on user state
- **Rewriting URLs:** A/B testing, feature flags
- **Setting Headers:** Security headers, CORS
- **Bot Detection:** Block or redirect bots
- **Localization:** Detect and redirect to user's locale
- **Rate Limiting:** Prevent abuse
- **Logging:** Track requests and analytics
- **Feature Flags:** Enable/disable features per user
- **Request Transformation:** Modify requests before they reach your app

#### Proxy Best Practices

1. **Keep it Fast:** Proxy runs on every matched request
2. **Use Edge Runtime:** Faster cold starts and better performance
3. **Avoid Heavy Computations:** Defer complex logic to API routes
4. **Cache When Possible:** Use caching for expensive operations
5. **Handle Errors:** Always have fallback behavior
6. **Test Thoroughly:** Proxy affects all matched routes
7. **Optimize Matchers:** Use specific matchers to avoid unnecessary executions

#### Key Differences: proxy.ts vs middleware.ts

| Feature        | middleware.ts (Next.js 15) | proxy.ts (Next.js 16) |
| -------------- | -------------------------- | --------------------- |
| File Name      | `middleware.ts`            | `proxy.ts`            |
| Function Name  | `middleware()`             | `proxy()`             |
| Performance    | Good                       | Better (optimized)    |
| Edge Runtime   | Supported                  | Enhanced              |
| Error Handling | Manual                     | Improved built-in     |
| Type Safety    | Good                       | Enhanced              |

---

## 11. Authentication

### 11.1 Authentication Strategies

#### Session-based Authentication

- Store session on server
- Send session ID to client (cookie)
- Validate on each request

#### Token-based Authentication (JWT)

- Generate JWT on login
- Store in cookie or localStorage
- Validate on each request

#### OAuth

- Third-party authentication (Google, GitHub)
- More secure
- Better UX

### 11.2 NextAuth.js (Auth.js)

Popular authentication library for Next.js.

#### Installation

```bash
npm install next-auth@beta
```

#### Configuration

```typescript
// app/api/auth/[...nextauth]/route.ts
import NextAuth from "next-auth";
import GithubProvider from "next-auth/providers/github";
import CredentialsProvider from "next-auth/providers/credentials";

const handler = NextAuth({
  providers: [
    GithubProvider({
      clientId: process.env.GITHUB_ID!,
      clientSecret: process.env.GITHUB_SECRET!,
    }),
    CredentialsProvider({
      name: "Credentials",
      credentials: {
        email: { label: "Email", type: "email" },
        password: { label: "Password", type: "password" },
      },
      async authorize(credentials) {
        // Validate credentials
        const user = await validateUser(credentials);
        return user;
      },
    }),
  ],
  callbacks: {
    async jwt({ token, user }) {
      if (user) {
        token.id = user.id;
      }
      return token;
    },
    async session({ session, token }) {
      session.user.id = token.id;
      return session;
    },
  },
  pages: {
    signIn: "/login",
  },
});

export { handler as GET, handler as POST };
```

#### Using in Components

```typescript
"use client";

import { useSession, signIn, signOut } from "next-auth/react";

export default function Component() {
  const { data: session, status } = useSession();

  if (status === "loading") return <div>Loading...</div>;

  if (session) {
    return (
      <>
        <p>Signed in as {session.user?.email}</p>
        <button onClick={() => signOut()}>Sign out</button>
      </>
    );
  }

  return <button onClick={() => signIn()}>Sign in</button>;
}
```

#### Server Component

```typescript
import { getServerSession } from "next-auth";

export default async function Page() {
  const session = await getServerSession();

  if (!session) {
    redirect("/login");
  }

  return <div>Welcome {session.user?.name}</div>;
}
```

### 11.3 Session Management

#### Cookies

```typescript
import { cookies } from "next/headers";

// Set cookie
cookies().set("token", "value", {
  httpOnly: true,
  secure: process.env.NODE_ENV === "production",
  sameSite: "lax",
  maxAge: 60 * 60 * 24 * 7, // 1 week
});

// Get cookie
const token = cookies().get("token");

// Delete cookie
cookies().delete("token");
```

#### JWT

```typescript
import jwt from "jsonwebtoken";

// Generate token
const token = jwt.sign({ userId: user.id }, process.env.JWT_SECRET!, {
  expiresIn: "7d",
});

// Verify token
const decoded = jwt.verify(token, process.env.JWT_SECRET!);
```

### 11.4 Protected Routes

#### Middleware Protection

```typescript
// middleware.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function middleware(request: NextRequest) {
  const token = request.cookies.get("token");

  if (!token) {
    return NextResponse.redirect(new URL("/login", request.url));
  }

  return NextResponse.next();
}

export const config = {
  matcher: ["/dashboard/:path*"],
};
```

#### Component-level Protection

```typescript
// app/dashboard/page.tsx
import { redirect } from "next/navigation";
import { getSession } from "@/lib/auth";

export default async function Dashboard() {
  const session = await getSession();

  if (!session) {
    redirect("/login");
  }

  return <div>Dashboard</div>;
}
```

### 11.5 JWT and Cookies

#### Best Practices

1. **Use HttpOnly cookies** for tokens
2. **Set Secure flag** in production
3. **Use SameSite** to prevent CSRF
4. **Short expiration** for access tokens
5. **Refresh tokens** for long sessions
6. **Validate on server** always

---

## 12. API Routes and Server Actions

### 12.1 Route Handlers

#### Basic Route Handler

```typescript
// app/api/posts/route.ts
export async function GET(request: Request) {
  const posts = await db.post.findMany();
  return Response.json(posts);
}

export async function POST(request: Request) {
  const body = await request.json();
  const post = await db.post.create({ data: body });
  return Response.json(post, { status: 201 });
}
```

#### Dynamic Route Handler

```typescript
// app/api/posts/[id]/route.ts
export async function GET(
  request: Request,
  { params }: { params: { id: string } }
) {
  const post = await db.post.findUnique({
    where: { id: params.id },
  });

  if (!post) {
    return Response.json({ error: "Not found" }, { status: 404 });
  }

  return Response.json(post);
}

export async function PATCH(
  request: Request,
  { params }: { params: { id: string } }
) {
  const body = await request.json();
  const post = await db.post.update({
    where: { id: params.id },
    data: body,
  });

  return Response.json(post);
}

export async function DELETE(
  request: Request,
  { params }: { params: { id: string } }
) {
  await db.post.delete({ where: { id: params.id } });
  return new Response(null, { status: 204 });
}
```

### 12.2 Server Actions

#### Creating Server Actions

```typescript
// app/actions.ts
"use server";

import { revalidatePath } from "next/cache";
import { redirect } from "next/navigation";

export async function createPost(formData: FormData) {
  const title = formData.get("title") as string;
  const content = formData.get("content") as string;

  // Validation
  if (!title || !content) {
    return { error: "Title and content are required" };
  }

  // Database operation
  const post = await db.post.create({
    data: { title, content },
  });

  // Revalidate cache
  revalidatePath("/posts");

  // Redirect
  redirect(`/posts/${post.id}`);
}
```

#### Using in Forms

```typescript
// app/posts/new/page.tsx
import { createPost } from "@/app/actions";

export default function NewPost() {
  return (
    <form action={createPost}>
      <input name="title" type="text" required />
      <textarea name="content" required />
      <button type="submit">Create Post</button>
    </form>
  );
}
```

#### Using in Client Components

```typescript
"use client";

import { createPost } from "@/app/actions";
import { useFormState, useFormStatus } from "react-dom";

function SubmitButton() {
  const { pending } = useFormStatus();
  return (
    <button disabled={pending}>{pending ? "Creating..." : "Create"}</button>
  );
}

export default function PostForm() {
  const [state, formAction] = useFormState(createPost, { error: null });

  return (
    <form action={formAction}>
      <input name="title" type="text" />
      {state?.error && <p>{state.error}</p>}
      <SubmitButton />
    </form>
  );
}
```

### 12.3 Form Handling

#### Progressive Enhancement

```typescript
"use server";

export async function submitForm(formData: FormData) {
  // Works without JavaScript
  const data = {
    name: formData.get("name"),
    email: formData.get("email"),
  };

  await saveToDatabase(data);
  revalidatePath("/");
}
```

#### With Validation

```typescript
"use server";

import { z } from "zod";

const schema = z.object({
  title: z.string().min(1).max(100),
  content: z.string().min(10),
});

export async function createPost(formData: FormData) {
  const validatedFields = schema.safeParse({
    title: formData.get("title"),
    content: formData.get("content"),
  });

  if (!validatedFields.success) {
    return {
      errors: validatedFields.error.flatten().fieldErrors,
    };
  }

  const post = await db.post.create({
    data: validatedFields.data,
  });

  revalidatePath("/posts");
  redirect(`/posts/${post.id}`);
}
```

### 12.4 Error Handling

#### Try-Catch

```typescript
export async function GET() {
  try {
    const data = await fetchData();
    return Response.json(data);
  } catch (error) {
    console.error(error);
    return Response.json({ error: "Internal Server Error" }, { status: 500 });
  }
}
```

#### Custom Error Responses

```typescript
export async function GET(request: Request) {
  const { searchParams } = new URL(request.url);
  const id = searchParams.get("id");

  if (!id) {
    return Response.json({ error: "ID is required" }, { status: 400 });
  }

  const data = await getData(id);

  if (!data) {
    return Response.json({ error: "Not found" }, { status: 404 });
  }

  return Response.json(data);
}
```

### 12.5 CORS and Security

#### CORS Headers

```typescript
export async function GET(request: Request) {
  const data = await getData();

  return Response.json(data, {
    headers: {
      "Access-Control-Allow-Origin": "*",
      "Access-Control-Allow-Methods": "GET, POST, PUT, DELETE, OPTIONS",
      "Access-Control-Allow-Headers": "Content-Type, Authorization",
    },
  });
}

export async function OPTIONS(request: Request) {
  return new Response(null, {
    status: 200,
    headers: {
      "Access-Control-Allow-Origin": "*",
      "Access-Control-Allow-Methods": "GET, POST, PUT, DELETE, OPTIONS",
      "Access-Control-Allow-Headers": "Content-Type, Authorization",
    },
  });
}
```

#### Rate Limiting

```typescript
import { Ratelimit } from "@upstash/ratelimit";
import { Redis } from "@upstash/redis";

const ratelimit = new Ratelimit({
  redis: Redis.fromEnv(),
  limiter: Ratelimit.slidingWindow(10, "10 s"),
});

export async function GET(request: Request) {
  const ip = request.headers.get("x-forwarded-for") ?? "127.0.0.1";
  const { success } = await ratelimit.limit(ip);

  if (!success) {
    return Response.json({ error: "Too many requests" }, { status: 429 });
  }

  return Response.json({ data: "..." });
}
```

---

## 13. Database Integration

### 13.1 Prisma

#### Installation

```bash
npm install prisma @prisma/client
npx prisma init
```

#### Schema

```prisma
// prisma/schema.prisma
datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

generator client {
  provider = "prisma-client-js"
}

model Post {
  id        String   @id @default(cuid())
  title     String
  content   String
  published Boolean  @default(false)
  author    User     @relation(fields: [authorId], references: [id])
  authorId  String
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
}

model User {
  id    String @id @default(cuid())
  email String @unique
  name  String?
  posts Post[]
}
```

#### Client Setup

```typescript
// lib/prisma.ts
import { PrismaClient } from "@prisma/client";

const globalForPrisma = globalThis as unknown as {
  prisma: PrismaClient | undefined;
};

export const prisma =
  globalForPrisma.prisma ??
  new PrismaClient({
    log: ["query"],
  });

if (process.env.NODE_ENV !== "production") globalForPrisma.prisma = prisma;
```

#### Usage

```typescript
// app/posts/page.tsx
import { prisma } from "@/lib/prisma";

export default async function PostsPage() {
  const posts = await prisma.post.findMany({
    include: {
      author: true,
    },
    orderBy: {
      createdAt: "desc",
    },
  });

  return <div>{/* Render posts */}</div>;
}
```

### 13.2 MongoDB

```typescript
// lib/mongodb.ts
import { MongoClient } from "mongodb";

const uri = process.env.MONGODB_URI!;
const options = {};

let client;
let clientPromise: Promise<MongoClient>;

if (process.env.NODE_ENV === "development") {
  const globalWithMongo = global as typeof globalThis & {
    _mongoClientPromise?: Promise<MongoClient>;
  };

  if (!globalWithMongo._mongoClientPromise) {
    client = new MongoClient(uri, options);
    globalWithMongo._mongoClientPromise = client.connect();
  }
  clientPromise = globalWithMongo._mongoClientPromise;
} else {
  client = new MongoClient(uri, options);
  clientPromise = client.connect();
}

export default clientPromise;
```

### 13.3 PostgreSQL

```typescript
// lib/postgres.ts
import { Pool } from "pg";

const pool = new Pool({
  connectionString: process.env.DATABASE_URL,
});

export async function query(text: string, params?: any[]) {
  const start = Date.now();
  const res = await pool.query(text, params);
  const duration = Date.now() - start;
  console.log("Executed query", { text, duration, rows: res.rowCount });
  return res;
}
```

### 13.4 Supabase

```bash
npm install @supabase/supabase-js
```

```typescript
// lib/supabase.ts
import { createClient } from "@supabase/supabase-js";

export const supabase = createClient(
  process.env.NEXT_PUBLIC_SUPABASE_URL!,
  process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY!
);
```

```typescript
// app/posts/page.tsx
import { supabase } from "@/lib/supabase";

export default async function PostsPage() {
  const { data: posts } = await supabase.from("posts").select("*");

  return <div>{/* Render posts */}</div>;
}
```

### 13.5 Database Best Practices

1. **Connection Pooling:** Reuse database connections
2. **Error Handling:** Always handle database errors
3. **Transactions:** Use for multiple related operations
4. **Indexing:** Index frequently queried fields
5. **Validation:** Validate data before database operations
6. **Security:** Use parameterized queries
7. **Caching:** Cache frequently accessed data
8. **Monitoring:** Monitor database performance

---

## 14. Performance Optimization

### 14.1 Code Splitting

Automatic code splitting by route.

#### Dynamic Imports

```typescript
import dynamic from "next/dynamic";

const DynamicComponent = dynamic(() => import("@/components/Heavy"), {
  loading: () => <p>Loading...</p>,
  ssr: false, // Disable SSR for this component
});

export default function Page() {
  return <DynamicComponent />;
}
```

### 14.2 Lazy Loading

#### Components

```typescript
import { lazy, Suspense } from "react";

const LazyComponent = lazy(() => import("@/components/Heavy"));

export default function Page() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <LazyComponent />
    </Suspense>
  );
}
```

#### Images

```typescript
<Image src="/image.jpg" alt="Image" width={500} height={500} loading="lazy" />
```

### 14.3 Bundle Analysis

```bash
npm install @next/bundle-analyzer
```

```javascript
// next.config.js
const withBundleAnalyzer = require("@next/bundle-analyzer")({
  enabled: process.env.ANALYZE === "true",
});

module.exports = withBundleAnalyzer({
  // Next.js config
});
```

```bash
ANALYZE=true npm run build
```

### 14.4 Performance Monitoring

#### Web Vitals

```typescript
// app/layout.tsx
import { Analytics } from "@vercel/analytics/react";

export default function RootLayout({ children }) {
  return (
    <html>
      <body>
        {children}
        <Analytics />
      </body>
    </html>
  );
}
```

#### Custom Reporting

```typescript
// app/layout.tsx
"use client";

import { useReportWebVitals } from "next/web-vitals";

export function WebVitals() {
  useReportWebVitals((metric) => {
    console.log(metric);
    // Send to analytics
  });
}
```

### 14.5 Web Vitals

Key metrics:

- **LCP (Largest Contentful Paint):** Loading performance
- **FID (First Input Delay):** Interactivity
- **CLS (Cumulative Layout Shift):** Visual stability
- **TTFB (Time to First Byte):** Server response time
- **FCP (First Contentful Paint):** Initial render

---

## 18. Interview Questions

### 18.1 Fundamental Questions

**Q: What is Next.js and why use it?**
A: Next.js is a React framework that provides server-side rendering, static site generation, API routes, and many optimizations out of the box. Use it for better SEO, performance, and developer experience.

**Q: What's the difference between Next.js and Create React App?**
A: Next.js provides SSR/SSG, file-based routing, API routes, and built-in optimizations. CRA is a client-side only React app with no built-in routing or SSR.

**Q: What is the App Router?**
A: The App Router is Next.js's new routing system (since v13) that uses the `app/` directory, supports React Server Components, and provides better layouts, loading states, and error handling.

**Q: What are Server Components?**
A: Server Components render on the server and send HTML to the client with zero JavaScript. They can access backend resources directly and keep sensitive data on the server.

**Q: What are Client Components?**
A: Client Components render on the client and have access to browser APIs, React hooks, and interactivity. Use `"use client"` directive to create them.

**Q: When should you use Server vs Client Components?**
A: Use Server Components by default for data fetching and static content. Use Client Components for interactivity, hooks, and browser APIs.

**Q: What is file-based routing?**
A: Next.js automatically creates routes based on the file structure in the `app/` directory. `app/about/page.tsx` becomes `/about`.

**Q: What are layouts in Next.js?**
A: Layouts are shared UI that wrap multiple pages. They persist across navigation and don't re-render, making them perfect for navigation bars and common UI.

**Q: What is the difference between layout and template?**
A: Layouts persist across navigation and maintain state. Templates re-render on each navigation and reset state.

**Q: What are dynamic routes?**
A: Dynamic routes use square brackets for URL parameters. `app/posts/[slug]/page.tsx` matches `/posts/hello-world`.

### 18.2 Rendering Questions

**Q: What rendering strategies does Next.js support?**
A: Static Rendering (SSG), Dynamic Rendering (SSR), Streaming, and Incremental Static Regeneration (ISR).

**Q: What is Static Rendering (SSG)?**
A: Pre-rendering pages at build time. HTML is generated once and reused for each request. Best for content that doesn't change often.

**Q: What is Dynamic Rendering (SSR)?**
A: Rendering pages on each request. HTML is generated fresh for every request. Best for personalized or frequently changing content.

**Q: What is ISR (Incremental Static Regeneration)?**
A: Updating static pages after deployment without rebuilding the entire site. Use `revalidate` option to set update frequency.

**Q: What is Streaming?**
A: Progressively rendering and sending UI to the client as it's ready. Use Suspense boundaries to stream components.

**Q: What is Partial Prerendering (PPR)?**
A: New feature in Next.js 16 that combines static and dynamic rendering in the same route. Static shell loads instantly while dynamic parts stream in.

**Q: How does Next.js decide between static and dynamic rendering?**
A: Next.js automatically switches to dynamic rendering when using dynamic functions (cookies, headers, searchParams) or fetch with `cache: 'no-store'`.

**Q: What are dynamic functions?**
A: Functions that make a route dynamic: `cookies()`, `headers()`, `searchParams`, and `fetch()` with no-store cache.

**Q: How do you force static rendering?**
A: Use `export const dynamic = 'force-static'` or ensure no dynamic functions are used.

**Q: How do you force dynamic rendering?**
A: Use `export const dynamic = 'force-dynamic'` or `export const revalidate = 0`.

### 18.3 Performance Questions

**Q: How does Next.js optimize images?**
A: Automatic image optimization with the Image component: lazy loading, responsive images, modern formats (WebP), and automatic sizing.

**Q: What is automatic code splitting?**
A: Next.js automatically splits code by route, so each page only loads the JavaScript it needs.

**Q: How do you implement lazy loading?**
A: Use `dynamic()` for components or `React.lazy()` with Suspense. Images lazy load by default with the Image component.

**Q: What caching layers does Next.js have?**
A: Request Memoization, Data Cache, Full Route Cache, and Router Cache.

**Q: How do you invalidate cache?**
A: Use `revalidatePath()` or `revalidateTag()` for on-demand revalidation, or set time-based revalidation with `revalidate` option.

**Q: What is request memoization?**
A: Automatic deduplication of fetch requests during a single render. Multiple identical fetch calls only make one request.

**Q: How do you optimize fonts?**
A: Use `next/font` which automatically optimizes and self-hosts fonts, eliminating external network requests.

**Q: What are Web Vitals?**
A: Core performance metrics: LCP (loading), FID (interactivity), CLS (visual stability). Next.js provides built-in Web Vitals reporting.

**Q: How do you analyze bundle size?**
A: Use `@next/bundle-analyzer` to visualize what's in your JavaScript bundles and identify optimization opportunities.

**Q: What is prefetching in Next.js?**
A: Next.js automatically prefetches linked routes in the viewport, making navigation instant. Controlled with the `prefetch` prop on Link.

### 18.4 Advanced Questions

**Q: What are Server Actions?**
A: Server-side functions that can be called from Client Components. They enable form submissions and mutations without API routes.

**Q: How do Server Actions work?**
A: Mark functions with `"use server"` directive. Next.js creates an endpoint and handles serialization automatically.

**Q: What is proxy.ts in Next.js 16?**
A: Proxy.ts replaced middleware.ts in Next.js 16. It's code that runs before a request is completed, used for authentication, redirects, rewrites, and modifying headers. It offers better performance and enhanced capabilities compared to the old middleware.ts.

**Q: What are parallel routes?**
A: Feature that allows rendering multiple pages in the same layout simultaneously using `@folder` convention.

**Q: What are intercepting routes?**
A: Routes that intercept navigation to show content in current context (like modals) while updating the URL.

**Q: What is route grouping?**
A: Using `(folder)` to organize routes without affecting URL structure. Useful for multiple layouts or organizing code.

**Q: How do you handle errors in Next.js?**
A: Use `error.tsx` for error boundaries, `not-found.tsx` for 404s, and try-catch in Server Components.

**Q: What is the Edge Runtime?**
A: Lightweight runtime that runs on edge servers (closer to users). Faster cold starts but with limited Node.js APIs.

**Q: How do you implement internationalization (i18n)?**
A: Use route groups for locales, middleware for detection, and libraries like `next-intl` for translations.

**Q: What is Turbopack?**
A: Next.js's new Rust-based bundler (stable in v16). Up to 10x faster than Webpack with better HMR.

### 18.5 Scenario-Based Questions

**Q: How would you build an e-commerce site with Next.js?**
A: Use Static Rendering for product pages (with ISR for updates), Dynamic Rendering for cart/checkout, Server Actions for mutations, and optimize images with Image component.

**Q: How do you implement authentication?**
A: Use NextAuth.js for OAuth/credentials, middleware for route protection, Server Components for session checks, and HttpOnly cookies for tokens.

**Q: How do you optimize a slow Next.js app?**
A: Analyze with bundle analyzer, implement code splitting, use Image optimization, add caching strategies, enable Streaming, and monitor Web Vitals.

**Q: How do you handle SEO in Next.js?**
A: Use Metadata API for static/dynamic metadata, generate sitemaps, implement JSON-LD, use semantic HTML, and ensure proper SSR/SSG.

**Q: How would you implement a blog with Next.js?**
A: Use Static Rendering with `generateStaticParams()` for posts, MDX for content, ISR for updates, and Metadata API for SEO.

**Q: How do you handle real-time data?**
A: Use Client Components with WebSockets or Server-Sent Events, or implement polling with SWR/React Query.

**Q: How do you implement pagination?**
A: Use searchParams for page numbers, Server Components for data fetching, and Suspense for loading states.

**Q: How do you optimize database queries?**
A: Use connection pooling, implement caching, add database indexes, use React cache() for deduplication, and monitor query performance.

**Q: How do you handle file uploads?**
A: Use Server Actions with FormData, validate on server, store in cloud storage (S3, Cloudinary), and show progress with Client Components.

**Q: How would you migrate from Pages Router to App Router?**
A: Incremental migration: use both routers simultaneously, migrate route by route, update data fetching to async/await, convert to Server/Client Components, and update metadata.

---

## Additional Resources

### Official Documentation

- [Next.js Docs](https://nextjs.org/docs)
- [React Server Components](https://react.dev/reference/react/use-server)
- [Vercel Guides](https://vercel.com/guides)

### Learning Platforms

- Next.js Learn Course (Official)
- Next.js Conf Videos
- Vercel YouTube Channel

### Tools and Libraries

- **Prisma:** Database ORM
- **NextAuth.js:** Authentication
- **Tailwind CSS:** Styling
- **React Query:** Data fetching
- **Zod:** Validation
- **Uploadthing:** File uploads

### Community

- Next.js GitHub Discussions
- Next.js Discord
- Reddit r/nextjs

---

**Happy Learning! 🚀**

_These notes cover Next.js 16 concepts, features, and interview questions. Practice building projects to master Next.js._
