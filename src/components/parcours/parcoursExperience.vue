<script>
export default {
  data() {
    return {
      state: false
    }
  },
  props: {
    e: {
      type: Object,
      required: true
    }
  },
}
</script>

<template>
  <div class="experience">
    <div class="experience-logo">
      <img v-bind="this.e.logo" />
    </div>
    <div class="experience-content">
      <p class="experience-title">
        {{ this.e.title }}
      </p>
      <p class="experience-date">{{ this.e.date }}</p>
      <p class="experience-subtitle">{{ this.e.subtitle }}</p>
      <ul class="experience-description">
        <li v-for="d in this.e.description" :key="d">{{ d }}</li>
      </ul>
    </div>
  </div>
</template>

<style>
.experience {
  display: flex;
  gap: 32px;
  font-size: 0.8em;
}

.experience:not(:last-child) {
  margin-bottom: 32px;
}

.experience .experience-title {
  font-weight: bold;
  font-size: 1.2em;
}

.experience .experience-date {
  font-size: 0.9em;
  font-style: italic;
  font-weight: lighter;
  margin-bottom: 4px;
}

.experience .experience-logo {
  height: 70px;
  min-width: 70px;
  max-width: 70px;
}

.experience .experience-logo img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.experience .experience-subtitle {
  color: rgb(var(--parcours-dot-primary));
  font-weight: 600;
  margin-bottom: 16px;
}

.experience ul.experience-description {
  list-style: square;
  font-size: 0.9em;
}

</style>
