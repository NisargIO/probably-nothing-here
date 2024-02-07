# <img src="./assets/logo.png" width="600" />

> [!WARNING]
>
> _(experimental, pls do not share)_

hi! this is a super secret project we've been working on. it's a React linter for performance that helps you find rerender issues + explains why they're happening.

this should take <5 min to setup :)

## 0. prerequisites

clone this repo onto your local machine:

```bash
git clone https://github.com/NisargIO/probably-nothing-here.git
```

## 1. install vscode extension

i should have sent you a file called million-lint-0.0.x.vsix. install that onto your vscode by dragging it into your extensions sidebar tab (<kbd>Cmd ⌘ + Shift ⇧ + X</kbd>)

<img src="./assets/installing-extension.gif" width="450" />

reload your vscode window (or restart it) to make sure the extension is installed.

## 2. open dev environment

go to this repo:

```bash
cd probably-nothing-here
```

then run:

```bash
cd notes-demo
npm install
npm run start
```

then open [localhost:5173](http://localhost:5173) in your browser.

## 3. try it out!

play around with the app and see if you can find any performance issues. if you do, you should see it in the "Problems" tab in vscode.

_**hint**: try the `NoteButton` component_

here's how i use it:

https://github.com/aidenybai/probably-nothing-here/assets/38025074/1afbaa95-51f4-4967-822f-a1d5bf801993


---

# 🚧 **extra**: setup on your own project

## 1. install npm package

```bash
npm install @million/experimental-lint
```

## 2. add bundler integration

<details>
<summary><img src="https://nextjs.org/favicon.ico" width="15" height="15" /> Next.js (app)</summary>

`next.config.mjs`

```js
import copilot from '@million/experimental-lint';

/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
};

export default copilot.next(nextConfig, { rsc: true });
```

</details>

<details>
<summary><img src="https://nextjs.org/favicon.ico" width="15" height="15" /> Next.js (pages)</summary>

`next.config.mjs`

```js
import copilot from '@million/experimental-lint';

/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
};

export default copilot.next(nextConfig, {});
```

</details>

<details>
<summary><img src="https://webpack.js.org/icon_150x150.png" width="15" height="15" /> Webpack</summary>

`webpack.config.js`

```js
const copilot = require('@million/experimental-lint');
module.exports = {
  plugins: [million.webpack()],
};
```

</details>

<details>

<summary><img src="https://vitejs.dev/logo.svg" width="15" height="15" /> Vite</summary>

`vite.config.js`

```js
import copilot from '@million/experimental-lint';
import react from '@vitejs/plugin-react';
import { defineConfig } from 'vite';

export default defineConfig({
  plugins: [copilot.vite(), react()],
});
```

</details>

## 3. open development server

click around + interact with the app. check the "Problems" tab in vscode to see if you can find any performance issues.

---

# Security & Privacy

We don't collect or store any data from your project. The only information we send externally is through direct calls to OpenAI's API in order to generate the explanations. We also ping an internal server to check for updates.

We're planning to open source by Feb 29, 2024. Until then, please keep this project confidential.
