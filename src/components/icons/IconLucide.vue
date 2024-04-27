<script>
import * as icons from 'lucide-vue-next'

export default {
  props: {
    icon: {
      type: String,
      required: true
    },
    iconSize: {
      type: String,
      default: '1em'
    },
    colorStroke: {
      type: String,
      default: '#0f1941'
    },
    widthStroke: {
      type: String
    },
    absoluteStrokeWidth: {
      type: Boolean
    }
  },
  methods: {
    propsForLucide(props) {
      let p = { ...props }
      Reflect.deleteProperty(p, 'icon')
      return p
    }
  },
  computed: {
    iconComposant() {
      return icons[this.icon]
    }
  }
}
</script>

<template>
  <component
    :is="iconComposant"
    :size="iconSize"
    class="svg"
    :stroke="colorStroke"
    :stroke-width="widthStroke"
    :absolute-stroke-width="absoluteStrokeWidth"
  />
</template>
