<!-- Please remove this file from your project -->
<template>
  <div>
    <nuxt-logo />
    <nuxt-link to="/about">About Page</nuxt-link>
  </div>
</template>

<script>
import NuxtLogo from './NuxtLogo.vue'
export default {
  name: 'NuxtTutorial',
  components: { NuxtLogo },
}
</script>
