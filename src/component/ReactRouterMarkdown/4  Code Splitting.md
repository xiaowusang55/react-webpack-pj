# Code Splitting

One great feature of the web is that we don’t have to make our visitors download the entire app before they can use it. You can think of code splitting as incrementally downloading the app. To accomplish this we’ll use webpack, @babel/plugin-syntax-dynamic-import, and loadable-components.

webpack has built-in support for dynamic imports; however, if you are using Babel (e.g., to compile JSX to JavaScript) then you will need to use the @babel/plugin-syntax-dynamic-import plugin. This is a syntax-only plugin, meaning Babel won’t do any additional transformations. The plugin simply allows Babel to parse dynamic imports so webpack can bundle them as a code split. Your .babelrc should look something like this:

```sh
{
  "presets": ["@babel/preset-react"],
  "plugins": ["@babel/plugin-syntax-dynamic-import"]
}

```

loadable-components is a library for loading components with dynamic imports. It handles all sorts of edge cases automatically and makes code splitting simple! Here’s an example of how to use loadable-components:

```js
import loadable from '@loadable/component'
import Loading from "./Loading";

const LoadableComponent = loadable(() => import('./Dashboard'), {
  fallback: Loading,
})

export default class LoadableDashboard extends React.Component {
  render() {
    return <LoadableComponent />;
  }
}

```

That’s all there is to it! Simply use LoadableDashboard (or whatever you named your component) and it will automatically be loaded and rendered when you use it in your application. The fallback is a placeholder component to show while the real component is loading.

## Code Splitting and Server-Side Rendering

loadable-components includes a guide for server-side rendering.

