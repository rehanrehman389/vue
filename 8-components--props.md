---

## 8. Components & Props
- Components allow **reusability** of UI and logic.  
- **Props**: parent → child data communication.  
- **Emits**: child → parent communication.  
- Props support **type validation**.  
- `$attrs` + `inheritAttrs: false` → pass non-prop attributes selectively.  
- `provide/inject` → share values with deeply nested components.

```vue
<!-- Parent -->
<UserCard :name="userName" @logout="handleLogout" />

<!-- Child -->
<template>
  <div>
    <h3>{{ name }}</h3>
    <button @click="$emit('logout')">Logout</button>
  </div>
</template>

<script>
export default {
  props: {
    name: { type: String, required: true }
  }
}
</script>
