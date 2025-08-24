---

## 9. Slots
- Slots allow passing HTML/templates from parent → child components.  
- **Named slots** allow multiple placeholders in a single component.  
- **Scoped slots** allow passing data from child → parent slot content.  

```vue
<!-- Parent Component -->
<Card>
  <template #header>
    <h2>Title Goes Here</h2>
  </template>
  <template #content>
    <p>Some content inside the card</p>
  </template>
</Card>

<!-- Child Component -->
<template>
  <div class="card">
    <header><slot name="header"></slot></header>
    <main><slot name="content"></slot></main>
  </div>
</template>
