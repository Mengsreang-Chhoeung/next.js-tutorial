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

## Data Fetching Overview

### 📜 References

- [Next.js Start Learning](https://nextjs.org/learn/foundations/about-nextjs?utm_source=next-site&utm_medium=homepage-cta&utm_campaign=next-website)
- [Next.js Docs](https://nextjs.org/docs)

### 🤝 Contributors

- Mengsreang-Chhoeung [@mengsreang_dev](https://twitter.com/mengsreang_dev)
