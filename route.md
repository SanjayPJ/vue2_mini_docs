## Route

**Create route setup using vue installer or vue gui**

### Creating Route

add routes object to router.js file

```
routes: [
    {
      path: '/',
      name: 'home',
      component: Home
    },
    {
      path: '/about',
      name: 'about',
      // route level code-splitting
      // this generates a separate chunk (about.[hash].js) for this route
      // which is lazy-loaded when the route is visited.
      component: () => import(/* webpackChunkName: "about" */ './views/About.vue')
    },
    {
      path: '/contact',
      name: 'contact',
      // route level code-splitting
      // this generates a separate chunk (about.[hash].js) for this route
      // which is lazy-loaded when the route is visited.
      component: () => import(/* webpackChunkName: "about" */ './views/Contact.vue')
    },
  ]
```

to add routes to templates use:-

```
<router-link :to="{ name: 'contact' }">Contact</router-link>
```

### Parameter Passing

in routes object

```
{
    path: '/profile/:user_id',
    name: 'profile',
    // route level code-splitting
    // this generates a separate chunk (about.[hash].js) for this route
    // which is lazy-loaded when the route is visited.
    component: () => import(/* webpackChunkName: "about" */ './views/Profile.vue')
}
```

in templates
```
<router-link :to="{ name: 'profile', params: { user_id: 123 }}">Profile</router-link>
```

in vue file

```
<script>
    export default {
    name: "Profile",
    data() {
        return {
        userId: this.$route.params.user_id
        };
    },
    methods: {
        updateId() {
        this.userId = this.$route.params.user_id;
        }
    },
    watch: {
        $route: "updateId"
    }
    };
</script>
```

### Navigation

```
// literal string path
this.$router.push({ name: "home" });

// go forward by one record, the same as history.forward()
this.$router.go(1)

// go back by one record, the same as history.back()
this.$router.go(-1)
```