# Nuxt 3 with Vuetify 3

Look at the [Nuxt 3 documentation](https://nuxt.com/docs/getting-started/introduction) to learn more.

## Setup

Make sure to install the dependencies:

```bash
# project creation
npx nuxi init <project-name>

# open folder
cd <project-name>

# yarn
yarn install

# install vuetify3
yarn add vuetify@next sass mdi

# remove app.vue
rm app.vue

# create folders for pages, plugins, layouts
mkdir pages
mkdir plugins
mkdir layouts
```

## create vuetify.js plugin inside plugins folder

```js
import { createVuetify } from 'vuetify'
import * as components from 'vuetify/components'
import * as directives from 'vuetify/directives'

export default defineNuxtPlugin(nuxtApp => {
    const vuetify = createVuetify({
        components,
        directives,
    })

    nuxtApp.vueApp.use(vuetify)
})
```

## update nuxt.config.ts
```js
// https://nuxt.com/docs/api/configuration/nuxt-config
export default defineNuxtConfig({
    css: [
        'vuetify/lib/styles/main.sass',
        'mdi/css/materialdesignicons.min.css'
    ],
    build: {
        transpile: ['vuetify'],
    },
})
```

## write the code
- Add default.vue inside layouts folder
- Add index.vue inside pages folder


## Development Server

Start the development server on http://localhost:3000

```bash
yarn dev
```

## Production

Build the application for production:

```bash
yarn build
```

Locally preview production build:

```bash
yarn preview
```

Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.
