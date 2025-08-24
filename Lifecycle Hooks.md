## 11. Lifecycle Hooks
Vue components have **13 lifecycle hooks**. Some commonly used ones:  

- `beforeCreate` → Called **before** data observation and events setup.  
- `created` → Data and methods are reactive; good for API calls.  
- `beforeMount` → Right before mounting the template to the DOM.  
- `mounted` → Template is mounted; DOM elements are accessible.  
- `beforeUpdate` → Called before reactive data changes are applied to DOM.  
- `updated` → Called after reactive data changes are applied to DOM.  
- `beforeUnmount` → Cleanup before component is destroyed.  
- `unmounted` → Component destroyed.  

💡 Example: Making an API call using `created()`   and Example: Accessing DOM using mounted()
```vue
<script>
export default {
  data() { 
    return { users: [] } 
  },
  created() {
    fetch("/api/users")
      .then(res => res.json())
      .then(data => this.users = data)
  }
}
</script>



<template>
  <input ref="username" placeholder="Type name..." />
</template>

<script>
export default {
  mounted() {
    this.$refs.username.focus()
  }
}
</script>

