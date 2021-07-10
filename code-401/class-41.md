# React Native

![React Native](https://icts.io/wp-content/uploads/2020/04/react-native.png)

## Review, Research, and Discussion

1. Compare and Contrast Redux Toolkit with Redux “Ducks”

Ducks is a way to bundle reducers, action types, and actions into the same file. Rather than splitting up related code, it can be packaged into redux modules. 

Redux Toolkit goal is to help simplify common Redux use cases. It is not intended to be a complete solution for everything you might want to do with Redux, but it should make a lot of Redux-related code you need to write a lot simpler. Redux Toolkit exports several individual functions that you can use in your application, and adds in dependencies on some other packages that are commonly used with Redux.

2. What is the principle advantage of Redux Toolkit

Helps to solve three major problems with Redux: configuring a Redux store, adding numerous packages to get Redux to things, and removing unnecessary or boilerplate code.

## Terms

- **Redux Toolkit slices**: Redux slice is a collection of reducer logic and actions for a single feature of application. Redux state is typically organized into slices, defined by the reducers that are passed to combineReducers.
- **Namespace**: Programming paradigm of providing scope to identifiers (names of types, functions, variables, etc) to prevent collisions between them. JavaScript does not provide namespace by default. However, we can replicate this functionality by making a global object which can contain all functions and variables.

## What is React Native

React Native is a JavaScript framework for writing real, natively rendering mobile applications for iOS and Android. It’s based on React, Facebook’s JavaScript library for building user interfaces, but instead of targeting the browser, it targets mobile platforms. In other words: web developers can now write mobile applications that look and feel truly “native,” all from the comfort of a JavaScript library that we already know and love. Plus, because most of the code you write can be shared between platforms, React Native makes it easy to simultaneously develop for both Android and iOS.

Similar to React for the Web, React Native applications are written using a mixture of JavaScript and XML-esque markup, known as JSX. Then, under the hood, the React Native “bridge” invokes the native rendering APIs in Objective-C (for iOS) or Java (for Android). Thus, your application will render using real mobile UI components, not webviews, and will look and feel like any other mobile application. React Native also exposes JavaScript interfaces for platform APIs, so your React Native apps can access platform features like the phone camera, or the user’s location.

React Native currently supports both iOS and Android, and has the potential to expand to future platforms as well.

