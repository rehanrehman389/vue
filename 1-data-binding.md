# 📘 Vue.js Quick Reference Guide

This is a personal **Vue.js cheatsheet** with topic-wise notes and code snippets.  
Useful for quick revision and future reference.

---

## 1. Data Binding
Vue provides multiple ways to bind data into the template.  

- `{{ }}` → interpolation / Jinja-style syntax  
- `v-text` → replaces innerText  
- `v-html` → outputs raw HTML (**⚠️ risk of XSS**)  
- `v-bind` → binds attributes dynamically (`:src`, `:id`, `:class`)  
- Shorthand: `:` for `v-bind`  

```vue
<template>
  <div>
    <p>{{ message }}</p>
    <p v-text="message"></p>
    <p v-html="htmlContent"></p>
    <img :src="imageUrl" :alt="altText" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "Hello Vue!",
      htmlContent: "<b>Bold Text</b>",
      imageUrl: "logo.png",
      altText: "Vue Logo"
    }
  }
}
</script>
