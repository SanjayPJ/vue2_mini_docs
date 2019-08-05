## Render Data to DOM

### Show data variables

```
{{ message }}
```

### Data Binding

```
v-bind:attribute_name="variable_name"
```
```
:attribute_name="variable_name"
```

### Event Handling

```
v-on:event_name="methode_name()"
```
```
@event_name="methode_name()"
```

### Two way data binding

```
v-model="variable_name"
```

### Event Modifier

```
@event_name.event_modifier="methode_name"
```

**prevent is an eventmodifier**

### If Condition

```
<h1 v-if="awesome">Vue is awesome!</h1>
<div v-else-if="type === 'C'">C</div>
<h1 v-else>Oh no 😢</h1>
```

### For Loop

```
<ul id="example-1">
  <li v-for="item in items">
    {{ item.message }}
  </li>
</ul>
```



