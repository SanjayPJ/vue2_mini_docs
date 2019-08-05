## Creating Vue Instance

```
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!',
    items: ['Banana', 'Green Shells', 'Red Shells', 'Mushrooms', 'Star'],
    ninjas: [
        { name: 'Foo', age: 12 },
        { name: 'Bar', age: 23 }
    ],
  },
  methods: {
        change_wage(amount) {
            this.wage += amount
        },
        log_coords(e) {
            // console.log(e)
            this.coords.x = e.offsetX
            this.coords.y = e.offsetY
        },
        update_name(e) {
            // console.log(e.target.value)
            this.name = e.target.value
        },
    }
})
```

**Can declare variables inside data object and methodes inside methodes object.**

