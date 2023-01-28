# Setting up a new Vue.js Tailwind project
> everything that is going to be talked about below can be looked at in more detail at the following 2 links; [Vue.js installation docs](https://www.thisdot.co/blog/getting-started-with-tailwind-in-vue) and [Using Tailwind with Vue.js](https://www.thisdot.co/blog/getting-started-with-tailwind-in-vue)

> npm init vue@latest

> answer no to all questions other than Vue Router - you want to install this so that you can create multiple pages

> cd into the new folder and run "npm install" in the terminal

> npm install -D tailwindcss@latest postcss@latest autoprefixer@latest

> npx tailwindcss init -p

> open tailwind.config.js and replace the content with the tailwind.config.js file in this repo

> if you incude the plugin @tailwindcss/forms in your tailwind.config.js file run the command "npm install @tailwindcss/forms --save"

> in the "src" folder make a new folder called "css" and in the folder create 2 files "app.css" and "tailwind.css"

> in open tailwind.css and enter the below code and save the file

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

> app.css is where you can enter you custom css

> open the file main.js and replace the content with the below code

```js
import { createApp } from 'vue'
import App from './App.vue'
import router from './router'
import './css/tailwind.css'
import './css/app.css'

const app = createApp(App)

app.use(router)

app.mount('#app')
```

> replace your App.vue file with the below code
```vue
<script setup>
import { RouterView } from 'vue-router'
</script>

<template>
  <RouterView />
</template>
```
> open your index.js file inside the router folder and replace it with the below code
```js
import { createRouter, createWebHistory } from 'vue-router'
import Home from '../views/Home.vue'

const router = createRouter({
  history: createWebHistory(import.meta.env.BASE_URL),
  routes: [
    {
      path: '/',
      name: 'home',
      component: Home
    }
  ]
})

export default router

```
> delete all the files and folders inside your components folder

> delete all the files inside your views folder then create a new file called "Home.vue" as referenced in your router/index.js file

> enter the below code into the file and save it
```vue
<template>
  <h1 class="text-red-400">Hello</h1>
</template>

<script>
export default {
  name: "Home"
}
</script>

```
> add the below link to your index.html file as well as any google fonts you want to use like Montserrat

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.2.19/tailwind.min.css" referrerpolicy="no-referrer" />

<!--Fonts -->
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Montserrat:wght@200;300;400;500;600;700;800;900&display=swap">
```

> npm run dev
