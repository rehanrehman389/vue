---

## 7. Watchers
- **Watchers** are used when you want to perform side effects whenever a reactive data property changes.  
- Useful for tasks like API calls, validations, or updating other data.  
- Supports extra options:  
  - `immediate: true` → runs immediately when the component is created.  
  - `deep: true` → watches nested object/array changes.  

### Example: Basic Watcher and 
### Watcher with Options (immediate & deep)
```vue
<script>
export default {
  data() {
    return { search: "" }
  },
  watch: {
    search(newVal, oldVal) {
      console.log("Searching for:", newVal)
      // Example: API call when search value changes
    }
  }
}
</script>

<script>
export default {
  data() {
    return {
      search: "",
      user: { name: "Rehan", details: { age: 25 } }
    }
  },
  watch: {
    search: {
      handler(newVal) {
        console.log("Searching for:", newVal)
      },
      immediate: true   // runs immediately on component creation
    },
    user: {
      handler(newVal) {
        console.log("User object changed:", newVal)
      },
      deep: true        // watches nested properties inside user
    }
  }
}
</script>

