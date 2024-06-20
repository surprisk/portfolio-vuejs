<script>
import { RouterLink } from 'vue-router'
import IconLucide from '@/components/icons/IconLucide.vue'

export default {
  data() {
    return {}
  },
  props: {
    related: {
      type: Array
    }
  },
  components: { IconLucide, RouterLink }
}
</script>

<template>
  <div class="project-singlepage-background">
    <div class="container">
      <RouterLink :to="{ name: 'home' }" class="icon-align icon-back">
        <IconLucide widthStroke="2px" icon="ArrowLeft"></IconLucide>
        <span>Retour</span>
      </RouterLink>
      <slot></slot>
    </div>
  </div>
</template>

<style>
.project-singlepage-background {
  position: fixed;
  background: rgb(var(--gradient-background));
  background: radial-gradient(
    circle,
    rgba(var(--gradient-primary), 1) 60%,
    rgba(var(--gradient-secondary), 1) 95%,
    rgba(var(--gradient-third), 0.8) 100%
  );
  background-position: center;
  backdrop-filter: brightness(10%);

  animation: 5s linear 2s infinite alternate banner;
  width: 100vw;
  height: 100vh;
}

.project-singlepage-background .container {
  border-radius: 8px;
  background-color: rgba(var(--project-singlepage-background), 0.8);
  color: rgb(var(--project-singlepage-color));
  margin-top: 64px;
}

.project-singlepage-background .icon-back {
  margin-bottom: 32px;
}
</style>
