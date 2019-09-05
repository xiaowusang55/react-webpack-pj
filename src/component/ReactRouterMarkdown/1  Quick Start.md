# Quick Start

You’ll need a React web app to add `react-router`.

If you need to create one, the easiest way to get started is with a popular tool called Create React App.

First install `create-react-app`, if you don’t already have it, and then make a new project with it.

```sh
npm install -g create-react-app
creat-react-app demo-app
cd demo-app
```

## Installation

`React Router DOM`is published to npm so you can install it with either npm or yarn.

```sh
npm install react-router-dom
```

## Example: Basic Routing

In this example we have 3 ‘Page’ Components handled by the `<Router>`.

Note: Instead of `<a href="/">` we use `<Link to="/">`.

## Example: Nested Routing

This example shows how nested routing works. The route `/topics` loads the Topics component, which renders any further `<Route>'s` conditionally on the paths `:id` value.

## Now you’re ready to tinker. Happy routing!

