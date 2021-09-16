# vue carbon components

[![@rigglo/carbon-vue is released under the Apache-2.0 license](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](./LICENSE)
[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg)](https://lernajs.io/)

> Vue implementation of the Carbon Design System
> A collection of [Carbon Components](https://github.com/carbon-design-system/carbon-components) implemented using [Vue.js](https://vuejs.org/).

## Carbon Vue library - A fork of the original Carbon Vue Project

The [library](https://carbon-vue.rigglo.io/) provides front-end developers & engineers a collection of reusable Vue components to build websites and user interfaces. Adopting the library enables developers to use consistent markup, styles, and behavior in prototype and production work.

## Community Contributions Needed

As a community project contributions are not only welcome, but essential for the maintenance and growth of this project.

### Changelog

[CHANGELOG.md](./packages/core/CHANGELOG.md)

## Getting started

[Usage and getting started instructions](./packages/core/README.md#getting-started) for @rigglo/carbon-vue.

## Packages

### [@rigglo/carbon-vue](./packages/core)

A library of the Carbon core components

### List of available components

View available Vue Components [here](https://carbon-vue.rigglo.io). Usage information is available in the notes provided with each story.

## Building and publishing

This is a monorepo using `lerna`.
The following steps will build and publish the packages:

- clone or download the repo;
- run `yarn` to install dependencies and bootstrap the packages;
- run `yarn build` to build all the packages including the storybook;

If you just want to build an individual package you can limit the scope:

`yarn build --scope @rigglo/carbon-vue`

`yarn build --scope storybook`

To start the storybook in a local server use `yarn start`.
