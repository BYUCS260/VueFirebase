# VueFirebase
This tutorial will show you how to connect Vue to firebase.  Firebase can replace your database (Mongo) and other functions.  You can even host your html and css files there for a full solution. Some of this material came from [this tutorial](https://medium.com/@anas.mammeri/vue-2-firebase-how-to-build-a-vue-app-with-firebase-authentication-system-in-15-minutes-fdce6f289c3c)

If you don’t already have vue cli installed, let’s install it:
```
npm install -g @vue/cli
```
Now that you have vue cli installed, let’s create a new project. 
```
vue create vue-firebase-tutorial
```
You will be prompted to pick a preset. For our case, we are going to select “Manually select features” and choose vue-router option since we will be using it during this tutorial. 

Then, enter the new vue-firebase-tutorial directory, and run npm run the server
```
cd vue-firebase-tutorial
npm run serve
```
Now, if you open the url ‘http://yourhost:8080’, you should have the default view of the Vue project!

This app will consist of three views, two (Login view and Sign Up view) that we can access only without authentication, and one (Home view) that we can access only with authentication.

# Step 1: Login and Signup
Let’s create the Login view. To do so, we will create a new Vue component called Login under src/views
For the moment, the component will simply consist of a title, two input fields, a button and a small sentence in the html.

```
<template>
    <div class="login">
        <h3>Sign In</h3>
        <input type="text" placeholder="Email"><br>
        <button>Connection</button>
        <p>If you dont have an account you can create one</p>
    </div>
</template>
<script>
    export default {
        name: 'login',
        data() {
            return{};
        },
        methods: {}
    }
</script>
<style scoped> /* "scoped" attribute limites the CSS to this componenet */
</style>
```
Now use the vue-router to display this component.  Add the Login component to the "src/router/index.js" file.
```
import Vue from 'vue'
import VueRouter from 'vue-router'
import Home from '../views/Home.vue'

Vue.use(VueRouter)

const routes = [
  {
    path: '/',
    name: 'home',
    component: Home
  },
  {
    path: '/login',
    name: 'login',
    component: Login
  }
]

const router = new VueRouter({
  mode: 'history',
  base: process.env.BASE_URL,
  routes
})

export default router
```



