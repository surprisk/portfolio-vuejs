<script>
import { RouterView } from 'vue-router'

import navNavbar from '@/components/nav/navNavbar.vue'
import navFooter from '@/components/nav/navFooter.vue'

export default {
  data() {
    return {}
  },
  components: { navNavbar, navFooter, RouterView }
}
</script>

<template>
  <header></header>
  <navNavbar />
  <RouterView />
  <navFooter />
</template>

<style scoped></style>
