# Creating this app

```
npx create-react-app <app-name>
npx create-react-app bacnetzviewer

cd <app-name>
cd bacnetzviewer
```

# Electron

https://entwickler.de/online/javascript/electron-react-desktopanwendungen-579896835.html

In package.json add a homepage property

```
{
"name": "react-t-timer-app",
"homepage": ".",
"version": "0.1.0",
...
```

```
npm run build

npm install -–save-dev electron

npm run electron
```

# Phase 1 - Develop the React Application

To start the webpack development server which live-reloads all your changes during development, execute

```
npm start
```

This will not update content in the electron app!

After installing electron-forge, electron-forge will override the start command in package.json.

That is why you have to introduce a new command (startdev):

```
"scripts": {
    "startdev": "react-scripts start",
    "start": "electron-forge start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "electron": "electron .",
    "package": "electron-forge package",
    "make": "electron-forge make"
  },
```

Now to start the webpack development server:

```
npm run startdev
```

## Phase 2 - Copy the React Application into Electron

This will take the latest state of the React Application and copy it, so it is contained in the electron app.

```
npm run build
```

You can start electron for testing purposes:

```
npm run electron
```

If you are happy with the electron app, go to phase three to build a executable

## Phase 3 - Create a native app

Here, electron-forge is used.

Install the packager once and import your app

```
npm install --save-dev @electron-forge/cli
npx electron-forge import
```

Create the binaries

```
npm run make
```

The result is placed into the ./out folder.
On mac, execute the binary ./out/bacnetzviewer-darwin-x64/bacnetzviewer.app

# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `yarn build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
