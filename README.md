# Explore-Routes - Production-Ready React Nested SPA

<!-- MIT License -->

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

<!-- CSS -->

[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)

<!-- Languages & Web Standards -->

[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

<!-- Infra & Runtime -->

[![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://react.dev/)

## Plain docs links

- CSS (MDN) docs: [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- JavaScript (MDN) docs: [https://developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- Node.js docs: [https://nodejs.org/](https://nodejs.org/)

---

A compact React SPA demonstrating nested routing, data loaders, and component-driven layout using React Router v6. This project is a clean, production-ready sample suitable for showcasing modern React routing patterns and best practices.

## Key files and components

- Application root: [`App`](src/App.js) - [src/App.js](src/App.js)
- Layout container: [`Main`](src/layout/Main.js) - [src/layout/Main.js](src/layout/Main.js)
- Header / navigation: [`Header`](src/components/Header/Header.js) - [src/components/Header/Header.js](src/components/Header/Header.js)
- Pages and features:
  - [`Home`](src/components/Home/Home.js) - [src/components/Home/Home.js](src/components/Home/Home.js)
  - [`Products`](src/components/Products/Products.js) - [src/components/Products/Products.js](src/components/Products/Products.js)
  - [`Friends`](src/components/Friends/Friends.js) - [src/components/Friends/Friends.js](src/components/Friends/Friends.js)
  - [`Friend`](src/components/Friend/Friend.js) - [src/components/Friend/Friend.js](src/components/Friend/Friend.js)
  - [`FriendDetails`](src/components/FriendDetails/FriendDetails.js) - [src/components/FriendDetails/FriendDetails.js](src/components/FriendDetails/FriendDetails.js)
- Entrypoint: [`index`](src/index.js) - [src/index.js](src/index.js)
- Build output (production): [`build/index.html`](build/index.html) - [build/index.html](build/index.html)
- Metadata and scripts: [package.json](package.json) - [package.json](package.json)

## Project Overview

1. **Explore-Routes Is Built With Create React App:**

- Nested layout with an application shell (`Main`) and an `Outlet` for nested routes.
- Declarative route definitions using `createBrowserRouter` and `RouterProvider` in [`App`](src/App.js).
- Data loading with route loaders (fetching users from jsonplaceholder) in [`App`](src/App.js) and consumption in [`Friends`](src/components/Friends/Friends.js) and [`FriendDetails`](src/components/FriendDetails/FriendDetails.js).
- Minimal, component-focused styling (see [`Header.css`](src/components/Header/Header.css) and [`Friend.css`](src/components/Friend/Friend.css)).

2. **Routing and data loading - High Level**

- Root layout: path `/` → [`Main`](src/layout/Main.js).
- Child routes are defined in [`App`](src/App.js):
  - `/` and `/home` → [`Home`](src/components/Home/Home.js)
  - `/products` → [`Products`](src/components/Products/Products.js)
  - `/friends` → [`Friends`](src/components/Friends/Friends.js) - loader fetches users from https://jsonplaceholder.typicode.com/users
  - `/friend/:friendId` → [`FriendDetails`](src/components/FriendDetails/FriendDetails.js) - loader fetches single user by id

3. **Why this is production-proof:**

- Route-based loaders keep data fetching colocated with routes for predictable behavior and better UX.
- The project uses Create React App defaults for build and optimization: see [package.json](package.json) scripts (`start`, `build`, `test`).
- Clear component boundaries (Header, pages, small presentational components) ease maintainability and future extension.

## Getting started - developer quickstart

1. **To run locally and Install dependencies:**

```bash
npm install

```

2. **Start development server:**

```bash
npm start

```

3. **Available scripts (from package.json)**

- npm start - start dev server with hot reload
- npm run build - production build (output to build/) - see build/index.html
- npm test - run test runner

### Testing

> Basic test scaffold is present in src/App.test.js. Unit and integration tests can be added with @testing-library/react. Test setup uses src/setupTests.js.

### Quality, Structure and Extensibility

Single responsibility components: each page and UI element lives under src/components/\*.
Centralized layout: Main holds shared UI (header) and outlet for nested pages.
Clear separation of data and presentation - loaders return fetch responses that components consume with useLoaderData.

### Deployment

Production-ready static output is generated by npm run build and served from the build/ folder. The production manifest and static assets are under build/manifest.json and build/static/.
The app uses client-side routing; for most static hosts configure fallback to index.html to support deep linking (see public/index.html).

### Files Of Interest

- src/App.js
- src/layout/Main.js
- src/index.js
- src/components/Header/Header.js
- src/components/Friends/Friends.js
- src/components/Friend/Friend.js
- src/components/FriendDetails/FriendDetails.js
- package.json
- .gitignore

### License

- This project is licensed under the terms of the **[MIT License](./LICENSE)**.
- You may replace or update the license as needed for client or proprietary projects.

---

### Contact & Maintainer

- The route loaders currently return fetch Responses directly. Consider parsing JSON in the loader to centralize error handling and to provide consistent data shapes to components.
  Replace the demo API (jsonplaceholder) with your production API and add authentication/authorization middleware as needed.
  Consider extracting API calls into a small service layer (src/services/users.js) for testability and reuse.

- **_Project:_** _route-driven-spa_
- **_Name:_** Md Abu Kayser - Full-Stack Engineer
- **_Maintainer:_** [md-abu-kayser](https://github.com/md-abu-kayser)
- **_Email:_** [abu.kayser.official@gmail.com](mailto:abu.kayser.official@gmail.com)
- **_GitHub:_** [github.com/abu.kayser-official](https://github.com/md-abu-kayser)

If you’d like this README tailored for a specific purpose - such as **hiring managers**, **open-source contributors**, or **client deliverables** - feel free to request a custom tone or format.

---

- This repository is a focused demo for modern React Router usage and can be used as a base for progressive route-driven code splitting and UX-focused data loading.

**Thank you for reviewing this project!**

---
