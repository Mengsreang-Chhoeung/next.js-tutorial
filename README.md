# Next.js Tutorial

The React Framework for the Web.

## System Requirements

- [Node.js 14.6.0](https://nodejs.org) or newer
- MacOS, Windows (including WSL), and Linux are supported

## Automatic Setup

For JavaScript Project:

```shell
npx create-next-app@latest
# or
yarn create next-app
# or
pnpm create next-app
```

For TypeScript Project:

```shell
npx create-next-app@latest --typescript
# or
yarn create next-app --typescript
# or
pnpm create next-app --typescript
```

After the installation is complete:

- Run `npm run dev` or `yarn dev` or `pnpm dev` to start the development server on `http://localhost:3000`
- Visit `http://localhost:3000` to view your application
- Edit `pages/index.js` for js project or `pages/index.tsx` for ts project and see the updated result in your browser

**Note:** In this tutorial, we focus on ts project.

## Pages

In Next.js, a **page** is a [React Component](https://reactjs.org/docs/components-and-props.html) exported from a `.js`, `.jsx`, `.ts`, or `.tsx` file in the `pages` directory. Each page is associated with a route based on its file name.

**Example:** If you create `pages/about.tsx` that exports a React component like below, it will be accessible at `/about`.

```tsx
export default function About() {
  return <div>About</div>;
}
```

### Pages with Dynamic Routes

Next.js supports pages with dynamic routes. For example, if you create a file called `pages/posts/[id].tsx`, then it will be accessible at `posts/1`, `posts/2`, etc.

### Pre-rendering

By default, Next.js **pre-renders** every page. This means that Next.js generates HTML for each page in advance, instead of having it all done by client-side JavaScript. Pre-rendering can result in better performance and SEO.

Each generated HTML is associated with minimal JavaScript code necessary for that page. When a page is loaded by the browser, its JavaScript code runs and makes the page fully interactive. (This process is called _hydration_.)

#### Two forms of Pre-rendering

Next.js has two forms of pre-rendering: **Static Generation** and **Server-side Rendering**. The difference is in **when** it generates the HTML for a page.

- **Static Generation (Recommended)**: The HTML is generated at build time and will be reused on each request.
- **Server-side Rendering**: The HTML is generated on each request.

Importantly, Next.js lets you **choose** which pre-rendering form you'd like to use for each page. You can create a "hybrid" Next.js app by using Static Generation for most pages and using Server-side Rendering for others.

We **recommend** using **Static Generation** over Server-side Rendering for performance reasons. Statically generated pages can be cached by CDN with no extra configuration to boost performance. However, in some cases, Server-side Rendering might be the only option.

You can also use **Client-side data fetching** along with Static Generation or Server-side Rendering. That means some parts of a page can be rendered entirely by client side JavaScript. To learn more, take a look at the [Data Fetching](https://nextjs.org/docs/basic-features/data-fetching/client-side) documentation.

### Static Generation

<details>
    <summary><b>Examples</b></summary>
    <br>
    <ul>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-wordpress">WordPress Example</a> <a href="https://next-blog-wordpress.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/blog-starter">Blog Starter using markdown files</a> <a href="https://next-blog-starter.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-datocms">DatoCMS Example</a> <a href="https://next-blog-datocms.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-takeshape">TakeShape Example</a> <a href="https://next-blog-takeshape.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-sanity">Sanity Example</a> <a href="https://next-blog-sanity.vercel.app/">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-prismic">Prismic Example</a> <a href="https://next-blog-prismic.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-contentful">Contentful Example</a> <a href="https://next-blog-contentful.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-strapi">Strapi Example</a> <a href="https://next-blog-strapi.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-prepr">Prepr Example</a> <a href="https://next-blog-prepr.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-agilitycms">Agility CMS Example</a> <a href="https://next-blog-agilitycms.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-cosmic">Cosmic Example</a> <a href="https://next-blog-cosmic.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-buttercms">ButterCMS Example</a> <a href="https://next-blog-buttercms.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-storyblok">Storyblok Example</a> <a href="https://next-blog-storyblok.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-graphcms">GraphCMS Example</a> <a href="https://next-blog-graphcms.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-kontent">Kontent Example</a> <a href="https://next-blog-kontent.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-builder-io">Builder.io Example</a> <a href="https://cms-builder-io.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-tina">TinaCMS Example</a> <a href="https://cms-tina-example.vercel.app">(Demo)</a></li>
        <li><a href="https://static-tweet.vercel.app">Static Tweet</a> <a href="https://static-tweet.vercel.app">(Demo)</a></li>
        <li><a href="https://github.com/vercel/next.js/tree/canary/examples/cms-enterspeed">Enterspeed Example</a> <a href="https://next-blog-demo.enterspeed.com">(Demo)</a></li>
    </ul>
</details>

## Data Fetching Overview

### 📜 References

- [Next.js Start Learning](https://nextjs.org/learn/foundations/about-nextjs?utm_source=next-site&utm_medium=homepage-cta&utm_campaign=next-website)
- [Next.js Docs](https://nextjs.org/docs)

### 🤝 Contributors

- Mengsreang-Chhoeung [@mengsreang_dev](https://twitter.com/mengsreang_dev)
