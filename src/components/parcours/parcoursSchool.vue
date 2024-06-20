<script>
export default {
  data() {
    return {}
  },
  props: {
    state: {
      type: Boolean,
      default: false
    },
    position: {
      type: Number,
      required: true
    },
    s: {
      type: Object,
      required: true
    }
  }
  // watch: {
  //   state: {
  //     handler(s) {
  //       this.$emit('timebar', this.position, s)
  //     }
  //   }
  // }
}
</script>

<template>
  <div
    class="school"
    :class="{ active: state }"
    @click="this.$emit('timebar', this.position, state)"
  >
    <div class="school-logo">
      <slot>
        <img v-bind="s.logo" :src="s.logo.src" />
      </slot>
    </div>
    <p class="school-title">
      {{ s.title }}
    </p>
    <p class="school-date">
      {{ s.date }}
    </p>
    <p class="school-subtitle">
      {{ s.subtitle }}
    </p>
  </div>
</template>

<style>
.school {
  padding: 8px;
  text-align: center;
  display: inline-block;
  padding: 16px 32px;
  width: 320px;
  text-align: center;
  transition: 0.1s ease-out;
  cursor: pointer;
}

.school:is(:hover, .active) {
  background-color: rgba(var(--parcours-active-item), 0.1);
}

.school .school-logo {
  display: inline-block;
  height: 70px;
  min-width: 70px;
  max-width: 70px;
}

.school .school-logo img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.school .school-title {
  font-weight: bold;
  font-size: 1.2em;
}

.school .school-date {
  font-size: 0.9em;
  font-style: italic;
  font-weight: lighter;
  margin-bottom: 4px;
}

.school .school-subtitle {
  color: rgb(var(--parcours-dot-primary));
  font-weight: 600;
  margin-bottom: 16px;
}
</style>
