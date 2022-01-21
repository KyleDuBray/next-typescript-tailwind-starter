# Next.js-TypeScript-Tailwind Boilerplate

This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) See [From Scratch](#from-scratch) if interested in all of the commands used.
[Documentation for Typescript with Next](https://nextjs.org/docs/basic-features/typescript)
[Documentation for Tailwind with Next](https://tailwindcss.com/docs/guides/nextjs)

## Getting Started

Install modules:

```bash
npm install
# or
yarn install
```

Then, run the development server (this will also create a `tsconfig.json` file when run for the first time):

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

## From Scratch

This project was created using the following commands/files:

```bash
npx create-next-app@latest --ts

npm install typescript @types/react

npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
`tailwind.config.js`:

```js
module.exports = {
  content: [
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

`./styles/globals.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

`./pages/_app.tsx`:

```js
import "../styles/globals.css";
import type { AppProps } from "next/app";
import Layout from "../components/Layout";

function MyApp({ Component, pageProps }: AppProps) {
  return (
    <Layout>
      <Component {...pageProps} />
    </Layout>
  );
}
```

`./pages/index.tsx`:

```js
import type { NextPage } from "next";

const Home: NextPage = () => {
  return <div>Hi there, home page.</div>;
};

export default Home;
```

`components/Layout.tsx`:

```js
import * as React from "react";

interface LayoutProps {}

const Layout: React.FunctionComponent<LayoutProps> = ({ children }) => {
  return <div>{children}</div>;
};

export default Layout;
```

`tsconfig.json` file is created if not existing on first start:

```bash
npm run dev
# or
yarn dev
```


## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.
- [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.
- [Next.js GitHub repository](https://github.com/vercel/next.js/)
