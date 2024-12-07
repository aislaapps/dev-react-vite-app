# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

- Replace `tseslint.configs.recommended` to `tseslint.configs.recommendedTypeChecked` or `tseslint.configs.strictTypeChecked`
- Optionally add `...tseslint.configs.stylisticTypeChecked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and update the config:

```js
// eslint.config.js
import react from 'eslint-plugin-react'

export default tseslint.config({
  // Set the react version
  settings: { react: { version: '18.3' } },
  plugins: {
    // Add the react plugin
    react,
  },
  rules: {
    // other rules...
    // Enable its recommended rules
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
```
# Project Creation

## Create project

npm create vite@latest dev-react-vite-app -- --template react-ts

## Install

```
cd dev-react-vite-app
npm install
```

## Change port in vite.config.ts

```
export default defineConfig({
  plugins: [react()],
  server: {
    port: 3000
  }
})

```

## Launching the Appe

```
npm run dev
```

# Configure a .devcontainer for Codespaces

F1 -> Search Add/Create Dev Container and select universal, then skip the rest of selection

![alt text](image-2.png)
![alt text](image-1.png)

# Reopening in Dev Container Locally

7th December 2024 - it is currently not supported yet in MacOS ARM

# Configure dev for Codespaces

To fix Vite for codespaces, modify package.json and append '--host' to the script.dev 

```
  "scripts": {
    "dev": "vite --host",
  }
```

This is the command that the dev container runs, set up in devcontainer.json "postAttachCommand": "npm run dev" on startup

## Running CRA in Codespaces

To run a React application created with CRA(create-react-app), the start command must be changed to:

```
  "scripts": {
    "start": "BROWSER=none WDS_SOCKET_PORT=0 react-scripts start"
    //...
  },
```

# Setting Up Github Codespaces

