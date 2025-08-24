## 12. Template Refs
Template refs allow direct access to **DOM elements** or **child components**.

- Use `ref="name"` in the template.  
- Access it in `mounted()` or methods using `this.$refs.name`.

💡 Example: Focus an input on page load and Example: Access child component methods
```vue
<template>
  <input ref="username" placeholder="Enter your name" />
</template>

<script>
export default {
  mounted() {
    this.$refs.username.focus()
  }
}
</script>




<ChildComponent ref="child" />

<script>
export default {
  methods: {
    callChildMethod() {
      this.$refs.child.childMethod()
    }
  }
}
</script>
