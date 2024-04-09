# [React Libraries in 2024 - Robin Wieruch](https://www.robinwieruch.de/react-libraries/)

Let's dive into the libraries that you could use for your next React application.

## 1. Starting A New React Project

**Recommendations:**

- Vite for client-side rendered React applications
- NextJS server-side rendered React applications
- Astro for static-side generated React applications

If you're a React veteran and want to try something new, check out [Nitro](https://nitro.unjs.io/) or [Waku](https://github.com/dai-shi/waku).

## 2. Package Manager for React

The most widely used package manager to install libraries in the JavaScript ecosystem is [npm](https://www.npmjs.com/), because it comes with every Node.js installation. However, [yarn](https://yarnpkg.com/) and [pnpm](https://pnpm.io/) are great alternatives.

If you happen to create multiple React applications which depend on each other or which share a common set of custom UI components, you may want to check out the concept of a **monorepo**. All previously mentioned package managers allow you to create monorepos by using their in-house workspaces feature, however, the author had the best developer experience using _yarn_ and _pnpm_.

**Recommendations:**

- Choose one package manager and stick to it
  - Default and most widely used -> npm
  - Increased performance but fairly new and not as popular -> pnpm
- If a monorepo is needed, check out _Turborepo_

## 3. React State Management

React comes with two built-in hooks to manage local state: `useState` and `useReducer`. If state needs to be managed globally, one can opt-in React's built-in `useContext` hook to tunel props from top-level components to components below them without using props and therefore avoiding the problem of props drilling. All three React hooks enable developers to implemennt powerful state management in React.

If you find yourself using React's Context too often for shared/global state, you should definitely check out [Zustand](https://github.com/pmndrs/zustand). Although Zustand becomes the de facto standard in the community, its simplicity makes it popular, you will find plenty of older React applications which come with **Redux**.

If you happen to use Redux, you should definitely check out [Redux Toolkit](https://redux-toolkit.js.org/) as well. If you are into state machines, check out [XState](https://github.com/statelyai/xstate) or [Zag](https://github.com/chakra-ui/zag). As alternatives, if you need a global store but do not like Zustand or Redux, check other popular local state management solutions like [Jotai](https://github.com/pmndrs/jotai), [Recoil](https://github.com/facebookexperimental/Recoil) or [Nano Stores](https://github.com/nanostores/nanostores).

**Recommendations:**

- `useState` and `useReducer` for co-located or shared state
- opt-in `useContext` for enabling _little_ global state
- Zustand or alternative for lots of global state

## 4. React Data Fetching

React's built-in hooks are great for UI state, but when it comes to state management for remote data, the author recommend using [TanStack Query](https://tanstack.com/query).

While TanStack Query itself is not seen as a state management library, because it is primarily used to fetch your remote data from APIs, it takes care of all the state management(e.g. caching, optimistic updates) of this remote data for you. TanStack Query was designed for consuming [REST APIs](https://www.robinwieruch.de/node-express-server-rest-api/). However, recently it supports [GraphQL](https://www.roadtographql.com/) too. If you're looking for a more dedicated GraphQL library for your React frontend, check out either [Apollo Client](https://www.apollographql.com/docs/react/)(popular), [urql](https://formidable.com/open-source/urql/)(lightweight), or [Relay](https://github.com/facebook/relay)(by Meta).

If you are already using Redux and want to add data fetching with integrated state management in Redux, you may want to check out [RTK Query](https://redux-toolkit.js.org/rtk-query/overview) which integrates data fetching neatly into Redux.

Last but not least, if you control the frontend and backend(both TypeScript), check out [tRPC](https://trpc.io/) for end-to-end type safe APIs.

**Recommendations:**

- TanStack Query (REST APIs or GraphQL APIs)
  - combined with `axios` or `fetch`
- Apollo Client (GraphQL APIs)
- tRPC for tightly coupled client-server architectures

## 5. Routing With React Router

If you're using a React framework like Next.js, routing is already taken care of for you. However, if you are using React without a framework and only for client-side rendering, the most powerful and popular routing library out there is [React Router](https://reactrouter.com/), a new alternative with full TypeScript support in mind is [TanStack Router](https://tanstack.com/router).

If you are using client-side routing in React with React Router, it's not much work introducing code splitting on a route level. If you happen to introduce this kind of optimization, you could substitute `React.lazy()` with `@loadable/component`.

**Recommendations:**

- most used: React Router
- trending: TanStack Router
  - primarily for its first-class TS support

## 6. CSS Styling in React

**Recommendations:**

- Utility-First-CSS (most popular)
  - e.g. Tailwind CSS (Trend)
- CSS-in-CSS
  - e.g. CSS Modules
- CSS-in-JS
  - e.g. [StyleX](https://stylexjs.com/) by Meta (compiles to utility-first CSS)
  - e.g. Styled Components (author do not recommend runtime CSS-in-JS anymore due to performance and other problems in server-side environments)
- CSS-in-TS (which support TypeScript and server-side-rendering)

## 7. React UI Libraries

UI library gives you access to lots of pre-built components which share the same design system, functionalities, and rules for accessibility:

- [Material UI (MUI)](https://material-ui.com/) (still most wanted in freelance projects)
- [Mantine UI](https://mantine.dev/) (most popular 2022)
- [Chakra UI](https://chakra-ui.com/) (most popular 2021)
- [NextUI](https://nextui.org/) (based on React Aria)
- [Park UI](https://park-ui.com/) (based on Ark UI)

The trend moves towards headless UI libraries though. They come without styling, but with all the functionalities and accessibilities that a modern component library needs. Most of the time they are combined with a Utility-First-CSS solution like Tailwind:

- [shadcn/ui](https://ui.shadcn.com/) (most popular in 2023)
- [Radix](https://www.radix-ui.com/)
- [React Aria](https://react-spectrum.adobe.com/react-aria/)
- [Catalyst](https://tailwindcss.com/blog/introducing-catalyst)
- [Daisy UI](https://daisyui.com/)
- [Headless UI](https://headlessui.com/)
- [Tailwind UI](https://www.tailwindui.com/) (NOT free)
- [Ark UI](https://ark-ui.com/) (from the makers of Chakra UI)

Perhaps more out of fashion compared to the other UI libraries:

- [Ant Design](https://ant.design/)
- [Semantic UI](https://react.semantic-ui.com/)
- [React Bootstrap](https://react-bootstrap.github.io/)
- [Reactstrap](https://reactstrap.github.io/?path=/story/home-installation--page)

## 8. React Animation Libraries

Any animation in a web application starts with CSS. Eventually you will notice that CSS animations aren't enough for your needs. Usually developers check out [React Transition Group](https://reactcommunity.org/react-transition-group/) then, which gives them the possibility to perform animations with React components. Other well known animation libraries for React are:

- [Framar Motion](https://www.framer.com/motion/) (most recommended)
- [react-spring](https://github.com/react-spring/react-spring)
- [react-motion](https://github.com/chenglou/react-motion)
- [react-move](https://github.com/sghall/react-move)

## 9. Visualization and Chart Libraries in React

If you really want to build charts from the ground up yourself, there is no way around [D3](https://d3js.org/). It's a low level visualization library that gives you everything you need to create amazing charts. However, learning D3 is a whole other adventure, thus many developers just pick a React charting library which does everything in exchange for flexibility. Popular solutions are:

- [Recharts]() (personal recommendation)
  - off the shelf charts
  - great composability
  - optional customization due to opt-in composability
- [visx]()
  - leaning more towards low-level D3 than high-level abstraction
  - steeper learning curve
- more off the shelf charts, more difficult to customize
  - [Victory](https://formidable.com/open-source/victory/)
  - [nivo](https://nivo.rocks/)
  - [react-chartjs](https://github.com/reactchartjs/react-chartjs-2)

## 10. Form Libraries in React

The most popular library for forms in React is [React Hook Form](https://react-hook-form.com/). It comes with everything needed: validation (most popular integrations is [zod](https://github.com/colinhacks/zod)), form submission, form state management. As alternative there are [Formik](https://github.com/jaredpalmer/formik) and [React Final Form](https://final-form.org/react).

**Recommendation**

- React Hook Form
  - with zod integration for validation

## 11. React Type Checking

The industry standard is using TypeScript in React applications. If you want to go beyond TypeScript for typed form validation, API validations (e.g. when using tRPC) and more, check out [Zod](https://github.com/colinhacks/zod).

**Recommendation**

- if typed JavaScript is wanted, use TypeScript

## 12. Code Structure in React

If you want to embrace a unified and common sense code style, use [ESLint](https://eslint.org/) in your React project. If you want to embrace a unified code format, use [Prettier](https://github.com/prettier/prettier) in your React project. Prettier doesn't replace ESLint though, but it integrates nicely with it.

Maybe a rising star in 2024 will be [Biome](https://biomejs.dev/) (formerly Rome). ESLint and Prettier are not the most favorite utilities when it comes to their setup and especially interplay. **Biome** wants to be an alternative to Prettier and ESLint by providing a fast (Rust based) and all-in-one toolchain.

**Recommendations:**

- ESLint + Prettier
- Try Biome

## 13. React Authentication

In a React application, you may want to introduce authentication with functionalities such as sign up, sign in, and sign out. Other features like password reset and password change features are often needed as well. These features go far beyond React, because a backend application manages these things for you.

The best learning experience would be implementing a backend application with authentication (e.g. [GraphQL backend](https://www.robinwieruch.de/graphql-apollo-server-tutorial/)) yourself. However, since authentication comes with lots of security risks and nitty gritty details not everyone knows about, the author advices to use one of many authentication/backend-as-a-service solutions which are out there:

- [Lucia](https://github.com/lucia-auth/lucia)
  - very interesting open source project
  - makes you independent from any third-party service (lock-in)
- [Supabase Auth](https://supabase.com/docs/guides/auth/overview)
- [Clerk](https://clerk.com/)
- [AuthKit](https://www.authkit.com/)
- [NextAuth](https://next-auth.js.org/)
- [Firebase Auth](https://www.robinwieruch.de/complete-firebase-authentication-react-tutorial/)
- [Auth0](https://auth0.com/)
- [AWS Cognito](https://aws.amazon.com/cognito/)

## 14. React Backend

Since there is a strong trend moving React to the server, the most natural habitat for a React project would be a meta framework like **Next.js**, **Astro**, or **Remix**.

If you can't use a full-stack framework due to various reasons (while still being able to use a JS/TS), you have to check out [tRPC](https://trpc.io/) or [Hono](https://hono.dev/). Honorable mention goes to the old school but must popular Node backend [Express](https://expressjs.com/). Other alternatives are [Fasitfy](https://fastify.dev/) or [Nest](https://nestjs.com/).

## 15. React Database

Not tied to React, but since full-stack React applications are getting popular these days, React is closer than ever to the database layer. While developing any Next.js application, you will most likely deal with a database ORM. The most popular ORM choice these days is [Prisma](https://www.prisma.io/). A _trending_ alternative is [Drizzle ORM](https://orm.drizzle.team/). More alternatives are [Kysely](https://kysely.dev/) and [database-js](https://github.com/planetscale/database-js) (only PlanetScale).

When it comes to choosing a database, Supabase (or Firebase) are valid database providers. Supabase with its PostgreSQL can be self-hosted or used as a paid service. Popular alternatives which offer serverless databases are [PlanetScale](https://planetscale.com/) (personal recommendation), [Neon](https://neon.tech/), and [Xata](https://xata.io/).

## 16. React Hosting

You can deploy and host a React application like any other web application. If you want to have full control, choose something like [Digital Ocean](https://www.digitalocean.com/). If you want to have someone taking care of everything, [Netlify](https://www.netlify.com/) or [Vercel](https://vercel.com/) (especially for Next.js) are popular solutions.

## 17. Testing in React

If you want to get a deep dive about testing in React, read this: [How to test components in React](https://www.robinwieruch.de/react-testing-tutorial/). The gist: The backbone of testing a React application is a test framework like [Jest](https://github.com/facebook/jest). It gives you test runner, assertion library and spying, mocking, stubbing functionalities. Everything that's needed from a comprehensive test framework. If you are a fan of Vite, you should check out [Vitest](https://vitest.dev/) as viable Jest alternative though.

Eventually you will find yourself using the popular [React Testing Library (RTL)](https://www.robinwieruch.de/react-testing-library/), which is used within your testing framework's environment, as a comprehensive testing library for React. RTL makes it possible to render your components and to simulate events on HTML elements. Afterward, your test framework is used for the assertions.

If you are looking for a testing tool for React end-to-end (E2E) tests, [Playwright](https://playwright.dev/) and [Cypress](https://www.robinwieruch.de/react-testing-cypress/) are the most popular choices.

**Recommendations:**

- Unit/Integration: Vitest + React Testing Library (most popular)
- Snapshot Tests: Vitest
- E2E Tests: Playwright or Cypress

## 18. React and Immutable Data Structure

Most popular choice is [Immer](https://github.com/immerjs/immer)

## 19. React Internationalization

**Recommendations:**

- [FormatJS](https://github.com/formatjs/formatjs)
- [react-i18next](https://github.com/i18next/react-i18next)
- [Lingui](https://lingui.dev/)

## 20. Rich Text Editor in React

When it comes to Rich Text Editors in React, I can only think of the following:

- [Plate](https://platejs.org/)
- [Lexical](https://github.com/facebook/lexical)
- [Slate.js](https://www.slatejs.org/)

## 21. Payment in React

The most common payment providers are Stripe and PayPal. Both can be neatly integrated into React.

- [PayPal](https://developer.paypal.com/docs/checkout/)
- Stripe
  - [React Stripe Elements]()
  - [Stripe Checkout]()

## 22. Time in React

If your React application deals heavily with dates, times, and timezones, you could introduce a library which manages these things for you. These are your options:

- [date-fns](https://github.com/date-fns/date-fns)
- [Day.js](https://github.com/iamkun/dayjs)
- [Luxon](https://github.com/moment/luxon/)

## 23. React Desktop Applications

[Electron](https://www.electronjs.org/) and [Tauri](https://github.com/tauri-apps/tauri) are the go to frameworks for cross-platform desktop applications.

## 24. File Upload in React

- [react-dropzone](https://react-dropzone.js.org/)

## 25. Mails in React

- [react-email](https://react.email/) (personal recommendation)
- [Mailing](https://www.mailing.run/)
- [mjml](https://mjml.io/)

## 26. Drag and Drop

Personally I have used [the successor of react-beautiful-dnd](https://github.com/hello-pangea/dnd) and cannot say anything negative about it. A popular alternative which offers way more flexibility and options, but comes with the cost of a steeper learning curve, is [dnd kit](https://dndkit.com/). Another alternative in the space is [react-dnd](https://github.com/react-dnd/react-dnd).

## 27. Mobile Development with React

The go-to solution for bringing React from the web to mobile is still [React Native](https://facebook.github.io/react-native/). The most popular framework for creating React Native applications is [Expo](https://www.robinwieruch.de/react-native-expo/). If you need unified components across web and mobile, you want to check out [Tamagui](https://tamagui.dev/).

## 28. Design Prototyping for React

If you are coming from a UI/UX background, you may want to use a tool for fast prototyping for new React components, layouts, or UI/UX concepts. Personally I use [Figma](https://www.figma.com/). For rough yet lightweight sketches, I like to use [Excalidraw](https://excalidraw.com/), others prefer [tldraw](https://www.tldraw.com/).

## 29. React Component Documentation

If you are in charge of writing the documentation for your components, there are various neat React documentation tools out there. I've used [Storybook](https://storybook.js.org/) in many projects and have a neutral opinion about it. I've heard good things about these other solutions too:

- [Docusaurus](https://github.com/facebook/docusaurus)
- [Docz](https://github.com/doczjs/docz)
- [Styleguidist](https://github.com/styleguidist/react-styleguidist)
- [React Cosmos](https://reactcosmos.org/)
