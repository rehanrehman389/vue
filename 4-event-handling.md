---

## 4. Event Handling
- `v-on:event="method"` → attach events.  
- Shorthand: `@event`.  
- `$event` can be passed into methods.  
- Can call multiple methods inside the same event.  

```vue
<template>
  <button @click="sayHello('Rehan', $event)">Click Me</button>
</template>

<script>
export default {
  methods: {
    sayHello(name, event) {
      alert(`Hello ${name}! You clicked: ${event.target.innerText}`);
    }
  }
}
</script>
