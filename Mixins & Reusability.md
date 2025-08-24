---

## 13. Mixins & Reusability
- **Mixins** allow you to reuse component logic across multiple components.  
- Useful for sharing data, computed properties, methods, lifecycle hooks.  
- Components can also override mixin properties or methods if needed.

💡 Example:

```vue
<!-- mixins/logger.js -->
export const loggerMixin = {
  data() {
    return {
      logPrefix: "Log:"
    }
  },
  methods: {
    log(message) {
      console.log(`${this.logPrefix} ${message}`);
    }
  },
  created() {
    this.log("Component created");
  }
}




<!-- MyComponent.vue -->
<template>
  <div>
    <button @click="log('Button clicked!')">Click Me</button>
  </div>
</template>

<script>
import { loggerMixin } from './mixins/logger.js'

export default {
  mixins: [loggerMixin]
}
</script>
