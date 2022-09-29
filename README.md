# Redux

Redux Toolkit Quick Start
WHAT YOU'LL LEARN
How to set up and use Redux Toolkit with React-Redux
PREREQUISITES
Familiarity with ES6 syntax and features
Knowledge of React terminology: JSX, State, Function Components, Props, and Hooks
Understanding of Redux terms and concepts
Introduction
Welcome to the Redux Toolkit Quick Start tutorial! This tutorial will briefly introduce you to Redux Toolkit and teach you how to start using it correctly.

How to Read This Tutorial
This page will focus on just how to set up a Redux application with Redux Toolkit and the main APIs you'll use. For explanations of what Redux is, how it works, and full examples of how to use Redux Toolkit, see the tutorials linked in the "Tutorials Overview" page.

For this tutorial, we assume that you're using Redux Toolkit with React, but you can also use it with other UI layers as well. The examples are based on a typical Create-React-App folder structure where all the application code is in a src, but the patterns can be adapted to whatever project or folder setup you're using.

The Redux+JS template for Create-React-App comes with this same project setup already configured.

Usage Summary
Install Redux Toolkit and React-Redux
Add the Redux Toolkit and React-Redux packages to your project:

npm install @reduxjs/toolkit react-redux

Create a Redux Store
Create a file named src/app/store.js. Import the configureStore API from Redux Toolkit. We'll start by creating an empty Redux store, and exporting it:

TypeScript
JavaScript
app/store.js
import { configureStore } from '@reduxjs/toolkit'

export const store = configureStore({
  reducer: {},
})

// Infer the `RootState` and `AppDispatch` types from the store itself
export type RootState = ReturnType<typeof store.getState>
// Inferred type: {posts: PostsState, comments: CommentsState, users: UsersState}
export type AppDispatch = typeof store.dispatch

This creates a Redux store, and also automatically configure the Redux DevTools extension so that you can inspect the store while developing.

Provide the Redux Store to React
Once the store is created, we can make it available to our React components by putting a React-Redux <Provider> around our application in src/index.js. Import the Redux store we just created, put a <Provider> around your <App>, and pass the store as a prop:
