<script>
export default {
  props: {
    color: {
      type: String,
      default: 'red'
    }
  }
}
</script>

<template>
  <span class="tag"><slot></slot></span>
</template>

<style>
.tag {
  font-weight: 400;
  border: 1px v-bind(color) solid;
  color: v-bind(color);
  padding: 2px 16px;
  border-radius: 8px;
}
</style>
