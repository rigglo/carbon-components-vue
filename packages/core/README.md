# carbon-components-vue

[![Carbon Components Vue is released under the Apache-2.0 license](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](./LICENSE)
[![CircleCI](https://circleci.com/gh/carbon-design-system/carbon-components-vue.svg?style=shield)](https://circleci.com/gh/carbon-design-system/carbon-components-vue)

> Vue implementation of the Carbon Design System
> A collection of [Carbon Components](https://github.com/carbon-design-system/carbon-components) implemented using [Vue.js](https://vuejs.org/).

## Carbon Vue library - A Carbon Community Project

The [library](http://vue.carbondesignsystem.com/) provides front-end developers & engineers a collection of reusable Vue components to build websites and user interfaces. Adopting the library enables developers to use consistent markup, styles, and behavior in prototype and production work.

## Community Contributions Needed

As a community project contributions are not only welcome, but essential for the maintenance and growth of this project.

## Changelog

See [CHANGELOG.md](CHANGELOG.md)

## Current Components

View available Vue.js components [here](http://vue.carbondesignsystem.com). Usage information is available when you click the blue `?` icon in the top right corner of the selected component.

See [component status pages](https://www.carbondesignsystem.com/component-status) for the status of each component.

## Development

Please refer to the [Contribution Guidelines](../../.github/CONTRIBUTING.md) before starting any work.

## Contributing

Fork this repository, create a new branch, and submit a pull request to this repository. The PR will be used as part of a review process.

## Usage

### General

The components do not import any of the carbon styles themselves. Use the SCSS or CSS from carbon-components to provide the styling.

- In your main js file (where you include Vue) you can include the styles wholesale: `import "carbon-components/css/carbon-components.min.css";`
- You can also use the unpkg cdn to bring in the styles wholesale: unpkg.com/carbon-components/css/carbon-components.min.css aliases the latest minified css file.
- If you prefer to build the SCSS, in the `<style>` tag of your top-level component you can include the styles wholesale: `@import "~carbon-components/scss/globals/scss/styles.scss";`
- Check out the [Carbon Design System developers](https://www.carbondesignsystem.com/getting-started/developers/vanilla) page for information on including individual component styles into your project.

### List of Available Components

View the available Carbon Vue components [here](http://vue.carbondesignsystem.com). Usage information is in the notes tab.

## Getting Started

### Quick Start (Vue CLI)

Assuming we're starting with a new project through the [Vue CLI](https://cli.vuejs.org/) (not with the plain Vue Webpack template, which might not work):

```sh
> vue create newprojectname
Vue CLI v3.7.0
? Please pick a preset: Manually select features
? Check the features needed for your project: Babel, CSS Pre-processors
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SCSS (with node-
sass)
? Where do you prefer placing config for Babel, PostCSS, ESLint, etc.? In package.json
? Save this as a preset for future projects? No
```

Using Yarn

```sh
yarn add @carbon/vue
```

Or npm

```sh
npm install --save @carbon/vue
```

In src/main.js add the following to include the carbon styles and components.

```js
import 'carbon-components/css/carbon-components.css';
import CarbonComponentsVue from '@carbon/vue/src/index';
Vue.use(CarbonComponentsVue);
```

Replace the contents of src/components/HelloWorld.vue with the following

```html
<template>
  <div class="sample">
    <h1>Example use of @carbon/vue</h1>
    <cv-text-input label="Who are you?" v-model="yourName" placeholder="your name" />
    <cv-button @click="onClick">Hello {{yourName}}</cv-button>
    <cv-modal :visible="visible" @modal-hidden="modalClosed">
      <template slot="title">Welcome to @carbon/vue {{yourName}}</template>
      <template slot="content">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, seed do eiusmod tempor incididunt ut labore et
          dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
          commodo consequat.
        </p>
      </template>
    </cv-modal>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data() {
      return {
        yourName: '',
        visible: false,
      };
    },
    methods: {
      onClick() {
        this.visible = true;
      },
      modalClosed() {
        this.visible = false;
      },
    },
  };
</script>

<style>
  .sample {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    max-width: 600px;
    margin: 5% auto;
  }

  .cv-text-input {
    margin: 30px 0;
  }
</style>
```

That's it! Now start the server and start building.

Using Yarn

```sh
yarn serve
```

Or npm

```sh
npm serve
```

### Install

Run the following command using [Yarn](https://yarnpkg.com/en/):

```bash
yarn add @carbon/vue
```

If you prefer [npm](https://www.npmjs.com/), use the following command instead:

```bash
npm install --save @carbon/vue
```

NOTE: [current-script-polyfill](https://www.npmjs.com/package/current-script-polyfill) is required for older browsers (_e.g._ IE11)

### Using the component library

In your main js file (where you include Vue):

```javascript
import CarbonComponentsVue from '@carbon/vue';
Vue.use(CarbonComponentsVue);
```

The above lines will register all the core components. You can register only the components you need if you prefer:

```
Vue.use(CarbonComponentsVue, ['CvButton', 'CvTag']);
```

### Using the components directly or individually

You can import the component source either for all core components or for the individual components you need.

To import all the core components:

```javascript
import CarbonComponentsVue from '@carbon/vue/src/index';
Vue.use(CarbonComponentsVue);
```

To import individual components:

```javascript
<script>
...
import { CvButton } from '@carbon/vue';
...
components: {
  CvButton,
},
...
</script>
```

Alternataively from source:

```javascript
<script>
...
import { CvButton } from '@carbon/vue/src';
...
components: {
  CvButton,
},
...
</script>
```

or

```javascript
<script>
...
import { CvButton } from '@carbon/vue/src/components/cv-button';
...
components: {
  CvButton,
},
...
</script>
```

or

```javascript
<script>
...
import CvButton from '@carbon/vue/src/components/cv-button/cv-button';
...
components: {
  CvButton,
},
...
</script>
```

Note: to import the component source you will need to ensure that Babel can process the source. We recommend the Babel preset `@vue/app`. If @carbon/vue is installed as a dependency in a `node_modules` folder or similar, you may need to enable Babel to process the source files, for example with the following lines, or similar, inside the `webpack.config.js` file:

```javascript
{
  test: /\.js$/,
  loader: 'babel-loader',
  include: [path.resolve(__dirname, 'node_modules/@carbon'), path.resolve(__dirname, 'src')]
}
```

### Using the components from unkpg

In your html file, no need to babel.

```html
<script src="https://unpkg.com/vue@latest" />
<script src="https://unpkg.com/@carbon/vue" />
<script>
Vue.use(window['carbon-vue'].default);
<script>

. . . <cv-button>Hello</cv-button>
```
