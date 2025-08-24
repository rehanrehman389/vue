---

## 5. Two-Way Binding (`v-model`)
- Syncs input with data property.  
- Works both ways → Template ↔ Script.  
- Supports modifiers:  
  - `.trim` → removes whitespace  
  - `.lazy` → updates on change instead of input  
  - `.number` → converts input to number  

```vue
<template>
  <form>
    <input v-model.trim="username" placeholder="Enter name" />
    <input v-model.number="age" type="number" />
    <p>Preview: {{ username }} ({{ age }})</p>
  </form>
</template>

<script>
export default {
  data() {
    return { username: "", age: 0 }
  }
}
</script>
