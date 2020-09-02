This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

## Deployment

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

# More Details

## SCSS Architecture & style

### ITCSS

We are using itcss (inverted triangle scss) in this project to structure our scss architecture.

More information on ITCSS can be found here: https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/

A good Example of ITCSS can be found here: https://github.com/xfiveco/generator-chisel/tree/master/generators/app/templates/styles/itcss

### BEM

We are also using the BEM naming style.

More information: https://mashbo.gitlab.io/front-end/guidelines/#/css-code-style

### Tailwind

This project uses tailwind: [https://tailwindcss.com/](https://tailwindcss.com/)

### Styled Components

We try to seperate our component css from our global css. Each component (if needed) should have its own css file. This will be done via css modules which will be explained in the next section.

Unforunately due to this, the css modules will be decoupled from the scss flow, so variables/mixins etc cant be shared between css modules.

### CSS Modules (SCSS)

We use css modules to import scss into our components. We do this so that were not loading unnecessary css into the dom. This way it is imported when the component is imported. The css is also scoped to the component so we dont need to worry about global styles clashing.

---

## Data Fetching

### Static rendering, Server side rendering or Client side rendering

Any pages in which all data fetching can be done at build time can use static rendering which is the fastest method.
Use `getStaticProps()`

Any pages that needs data at request time, and still should be pre-rendered, should use server side rendering.
Use `getServerSideProps(context)`

Pages that are more user specific and dont need SEO benefits, should use Client-side rendering.
Use SWR (read below)
