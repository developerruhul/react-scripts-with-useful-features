# react scripts with useful features

This is a fork of react-scripts v3.0.1. This fork has these additional useful features in addition to the original create-react-app features. So no need to worry about stability.

## Features

- ⚛️ Create React App 3 (React 16.8)
- 📮 Out of the box monorepo and yarn workspaces support. You have to follow [these small steps](https://github.com/react-workspaces/react-workspaces-playground/blob/master/README.md) to use it.
- ✨ Host Multiple CRA Apps, Component Libraries in one Monorepo
- 🎍Out of the box mobx decorators
- 👾 Out of the box chrome extension support
- 🌈 Better styled-components support via **babel-plugin-styled-components**
- ⛅ babel config support so you can add as many plugins as you want
- 🤯 integration with .eslintrc so any linting error is a compile error

## To use it all you need to do is

```
create-react-app my-app --scripts-version react-scripts-with-useful-features
```

And then bang 🤯 you get all these features in addition to the fantastic **Create react app**.

## To build for chrome -

- Add a `CLIENT_ENV="chrome"` to your `.env` file so react-scripts knows that you wanna build for chrome.
- Put your background.js and manifest and other static files in `/public` folder and it'll be copied unmodified to `/build` folder.
- Add a `content.js` in your `src/`. This will be the entry point for the chrome build instead of `index.js` which will be used in development.
- And finally, when you are done developing your extension locally, run `yarn run build` or `npm run build` and `react-scripts` will generate files without hash and will inline runtime-chunks. The catch here is that you need to hard code the static js and CSS file names in your manifest.content-scripts the first time you run build. There's no way to know how many chunks or CSS there'll be and their names. So you have to look and add appropriate names in you manifest. Each project is different. But if you wanna have an HTML popup you can leave the build folder untouched.

> Note: `index.js` and `content.js` is kinda the same. `index.js` will be used when you wanna develop the extension in the browser. It's not possible to build and reload on every change. So put your extension-related logic in `content.js`.
