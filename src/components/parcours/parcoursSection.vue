<script>
import item from '@/components/parcours/parcoursItem.vue'

export default {
  data() {
    return {}
  },
  components: {
    item
  }
}
</script>

<template>
  <div class="container">
    <h2 class="home-title">🚩 Parcours</h2>
    <div class="parcours">
      <span class="start-dot"></span>
      <span class="end-dot"></span>
      <item></item>
      <item></item>
      <item></item>
      <item></item>
      <item></item>
    </div>
  </div>
</template>

<style>
.parcours {
  position: relative;
  padding: 64px 0;
}

.start-dot,
.end-dot {
  z-index: 1;
  position: absolute;
  width: 24px;
  height: 24px;
  border-radius: 10px;
  background-color: rgba(var(--gradient-secondary, 0.6));
  left: 50%;
  transform: translateX(-50%);
}

.start-dot {
  top: 0;
}

.end-dot {
  bottom: 0;
}

.parcours::after {
  content: '';
  background: rgba(var(--gradient-secondary), 0.6);
  width: 4px;
  height: 100%;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
}
</style>
