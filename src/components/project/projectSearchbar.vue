<script>
export default {}
</script>
<template>
  <div class="project-search-bar">
    <input type="text" />
  </div>
</template>

<style scoped>
.project-search-bar {
  max-width: 600px;
  position: relative;
  margin-bottom: 32px;
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
