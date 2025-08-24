---

## 6. Computed Properties vs Methods
- **Computed Properties**  
  - Cached until their dependencies change  
  - Best for derived values used in multiple places  
  - Can also have **getters & setters**  

- **Methods**  
  - Run every time the component re-renders  
  - Not cached → less efficient for repeated usage  

💡 Use **computed** when the same logic is reused and depends on reactive state.  

```vue
<template>
  <div>
    <p>Full Name: {{ fullName }}</p>
    <input v-model="fullName" placeholder="Edit full name" />
  </div>
</template>

<script>
export default {
  data() {
    return { first: "Rehan", last: "Ansari" }
  },
  computed: {
    fullName: {
      // Getter
      get() {
        return `${this.first} ${this.last}`
      },
      // Setter
      set(value) {
        const parts = value.split(" ")
        this.first = parts[0]
        this.last = parts[1]
      }
    }
  }
}
</script>
