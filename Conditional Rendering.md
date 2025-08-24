---

## 2. Conditional Rendering
- `v-if / v-else-if / v-else` → removes/adds elements from DOM.  
- `v-show` → toggles `display:none` but keeps element in DOM.  
- Wrap multiple elements inside `<template>` if needed.  

```vue
<template>
  <div>
    <p v-if="status === 'success'">✅ Success</p>
    <p v-else-if="status === 'error'">❌ Error</p>
    <p v-else>⏳ Loading...</p>

    <p v-show="isVisible">This is always in DOM but hidden if false</p>
  </div>
</template>
