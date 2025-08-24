---

## 3. Lists (`v-for`)
- Loop over arrays/objects.  
- Always provide unique `:key`.  
- Combine with `<template>` for conditions.  

```vue
<template>
  <ul>
    <li v-for="(user, index) in users" :key="user.id">
      {{ index+1 }} - {{ user.name }}
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      users: [{id:1, name:"Rehan"}, {id:2, name:"Ali"}]
    }
  }
}
</script>
