<script>

export default {
  components : {},
  methods:{
  }
}
</script>
<template>
  <div class="form-control">
    <div>
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
  .form-control > div{
    margin: auto;
    width: 600px;
    display: inline-flex;
    text-align: left;
    color: rgb(16, 25, 66);
    font-size: 16px;
    gap: 2rem;
  }
  .form-control{
    margin-top: 3em;
    width: 100%;
    display: inline-block;
  }
</style>
