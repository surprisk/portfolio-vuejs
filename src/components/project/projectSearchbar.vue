<script>
import IconLucide from '@/components/icons/IconLucide.vue';

export default {
  components: {
    IconLucide
  }
}
</script>
<template>
  <div class="project-search-bar" @input="$emit('onSearch', $event)">
    <div class="icon-align"><IconLucide icon="Search" widthStroke="2px" />Recherche et filtres</div>
    <input type="text" />
  </div>
</template>

<style scoped>
.project-search-bar {
  max-width: 600px;
  position: relative;
  margin: auto auto 16px auto;
}

input {
  padding: 0.6rem 0.4rem;
  border-radius: 3px;
  border: 1px solid rgb(226, 226, 225);
  outline: none;
  width: 100%;
  margin-top: 0.6rem;
}

input:focus {
  outline: 2px solid rgb(28, 114, 216);
}
</style>
