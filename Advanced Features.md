---

## 10. Advanced Features
- **Scoped CSS** → `<style scoped>` restricts CSS to the component only.  
- **Dynamic Components** → `<component :is="currentComp" />` to render components based on conditions.  
- **KeepAlive** → preserves component state when switching tabs or dynamic components.  
- **Teleport** → render a component outside the root app element (useful for modals, dropdowns, tooltips).  
- **Mixins** → reusable logic across multiple components.  
- **Axios** → library for API calls (GET, POST, etc).  

💡 Example (Teleport):
and Example (Dynamic Components + KeepAlive):
```vue
<template>
  <teleport to="body">
    <div class="modal">
      <h3>Modal Header</h3>
      <p>Modal content rendered outside #app</p>
    </div>
  </teleport>
</template>


<template>
  <keep-alive>
    <component :is="currentTabComponent" />
  </keep-alive>

  <button @click="currentTabComponent = 'TabOne'">Tab One</button>
  <button @click="currentTabComponent = 'TabTwo'">Tab Two</button>
</template>

<script>
import TabOne from './TabOne.vue'
import TabTwo from './TabTwo.vue'

export default {
  components: { TabOne, TabTwo },
  data() {
    return { currentTabComponent: 'TabOne' }
  }
}
</script>
