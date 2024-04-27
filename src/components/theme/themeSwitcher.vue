<script>
export default {
  data() {
    return {
      state: this.getKeyTheme() ?? false
    }
  },
  props: {
    // Theme props force a default on each reload.
    theme: {
      type: String,
      default: localStorage.getItem('se-theme')
    },
    themes: {
      type: Object,
      default: () => {
        return {
          false: 'default',
          true: 'dark'
        }
      }
    }
  },
  methods: {
    getKeyTheme() {
      return Object.keys(this.themes).find((key) => this.themes[key] === this.theme)
    }
  },
  watch: {
    state: {
      handler(s) {
        document.documentElement.setAttribute('data-theme', this.themes[s])
        localStorage.setItem('se-theme', this.themes[s])
      },
      immediate: true
    }
  }
}
</script>

<template>
  <label class="switcher">
    <input type="checkbox" v-model="state" />
    <span class="slider round"></span>
  </label>
</template>

<style scoped>
.switcher {
  position: relative;
  display: inline-block;
  width: 44px;
  height: 22px;
}
.switcher input {
  opacity: 0;
  width: 0;
  height: 0;
}
.switcher .slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #d7d7d7;
  transition: 0.3s;
}
.switcher .slider.round {
  border-radius: 34px;
}
.switcher .slider.round:before {
  position: absolute;
  content: '';
  height: 16px;
  width: 16px;
  left: 4px;
  bottom: 3px;
  background-color: white;
  transition: 0.3s;
  border-radius: 50%;
}
.switcher input:checked + .slider {
  background-color: var(--color-accent);
}
.switcher input:checked + .slider:before {
  transform: translateX(20px);
}
</style>
