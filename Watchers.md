---

## 7. Watchers
- **Watchers** are used when you want to perform side effects whenever a reactive data property changes.  
- Useful for tasks like API calls, validations, or updating other data.  
- Supports extra options:  
  - `immediate: true` → runs immediately when the component is created.  
  - `deep: true` → watches nested object/array changes.  

### Example: Basic Watcher
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
