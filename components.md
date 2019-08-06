## Creating Components

### Basic Structure

```
<template>
 // Add Template here //
</template>

<script>
export default {
  name: 'NameOfTemplate',
  data() {
    return {
        msg: "Hello World!!!!"
    }
  }
}
</script>

<style scoped>
// styles here //
</style>
```
**Create components inside src/components**

### Data Function

```
export default {
  name: 'NameOfTemplate',
  data() {
    return {
        msg: "Hello World!!!!"
    }
  }
}
</script>
```

### Nesting Components

```
<template>
  <div id="app">
    <ComponentName />
  </div>
</template>

<script>
import ComponentName from './components/ComponentName.vue'

export default {
  name: 'app',
  components: {
    ComponentName
  }
}
</script>
```

### Scoped Styles

```
<style scoped>
// styles here
</style>
```

### Passing data through components

```
export default {
  name: 'app',
  props: {
    msg: String
  },
  //or
  props: ['msg'],
}
</script>
```

### Emiting Events

**In child component**

```
@click="functionName(param)"

functionName(pram){
    this.$emit('EmitEventName', {param})
}
```

**In parent component**

```
@EmitEventName="FunctionName"
```

### Including Methods

```
export default {
  name: 'app',
  methods: {
    functionName(){
        // do something here
    },
  },
}
</script>
```

### Computed Properties

```
<div id="example">
  <p>Original message: "{{ message }}"</p>
  <p>Computed reversed message: "{{ reversedMessage }}"</p>
</div>
```

```
var vm = new Vue({
  el: '#example',
  data: {
    message: 'Hello'
  },
  computed: {
    // a computed getter
    reversedMessage: function () {
      // `this` points to the vm instance
      return this.message.split('').reverse().join('')
    }
  }
})
```

### Filters

**Inside main.js**

```
Vue.filter('capitalize', function (value) {
  if (!value) return ''
  value = value.toString()
  return value.charAt(0).toUpperCase() + value.slice(1)
})
```

```
<!-- in mustaches -->
{{ message | capitalize }}
```