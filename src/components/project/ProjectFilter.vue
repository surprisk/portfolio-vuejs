<script>
import projectTag from '@/components/project/ProjectTag.vue'

export default {
  data(){
    return {
      stateHandler: []
    }
  },
  props: {
    tags: {
      type: Array,
      required: true
    }
  },
  components: {
    projectTag,
  },
  methods: {
    clickHandler(position){
      const state = !this.stateHandler[position]
      this.stateHandler[position] = state;
      this.$emit('onFilter', position, state)
    }
  },
  mounted(){
    for (let index = 0; index < this.tags.length; index++)
      this.stateHandler.push(false)
  }
}
</script>
<template>
  <div class="project-filter" @input="$emit('onSearch', $event)">
    <div class="project-filter-tags">
      <projectTag v-for="t,i in this.tags" :key="t" @click="this.clickHandler(i)" class="tag-button" :class="{active: this.stateHandler[i]}" :color="t.color">{{ t.name }}</projectTag>
    </div>
  </div>
</template>

<style scoped>
.project-filter {
  max-width: 600px;
  position: relative;
  margin: auto auto 64px auto;
}

.project-filter .project-filter-tags{
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 16px;
}

.tag-button{
  cursor: pointer;
  user-select: none;
  transition: .1s ease-out;
}

</style>
