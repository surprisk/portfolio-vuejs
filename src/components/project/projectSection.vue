<script>
import searchbar from '@/components/project/projectSearchbar.vue'
import projectComponent from '@/components/project/projectComponent.vue'
import projectTag from '@/components/project/projectTag.vue'
import projectFilter from '@/components/project/projectFilter.vue'
import IconLucide from '../icons/IconLucide.vue'
import { projects, tags } from '@/assets/database.json'

export default {
  data() {
    return {
      tags: tags,
      searchText: '',
      filterList: []
    }
  },
  methods: {
    searchHandler(e) {
      this.searchText = e.target.value.toLowerCase().trim()
    },
    filterHandler(position, state) {
      if (state) this.filterList.push(this.tags[position])
      else this.filterList = this.filterList.filter((f) => f != this.tags[position])
    }
  },
  computed: {
    getProjectsHandled() {
      let deepProjects = [...projects]

      return deepProjects.filter(
        (p) =>
          p.title.toLowerCase().trim().includes(this.searchText) &&
          (!this.filterList.length > 0 ||
            p.tags.some((t) => this.filterList.includes(this.tags[t])))
      )
    }
  },
  components: { searchbar, projectFilter, projectComponent, projectTag, IconLucide }
}
</script>

<template>
  <div id="projects_section" class="container section">
    <h2 class="home-title">💻 Projets</h2>
    <searchbar @onSearch="searchHandler" />
    <projectFilter :tags="this.tags" @onFilter="filterHandler" />
    <TransitionGroup name="projects" tag="div" class="projects">
      <projectComponent
        v-for="p in this.getProjectsHandled"
        :key="p"
        @click="$router.push(p.route)"
      >
        <template #image>
          <img v-if="p.image.src" v-bind="p.image" />
          <p v-else><IconLucide icon="FolderClosed" iconSize="2em" widthStroke="2px" /></p>
        </template>
        <template #title>{{ p.title }}</template>
        <template #tag>
          <projectTag v-for="t in p.tags" :key="t" :color="this.tags[t].color">{{
            this.tags[t].name
          }}</projectTag>
        </template>
      </projectComponent>
    </TransitionGroup>
  </div>
</template>

<style>
.projects {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 32px;
}

.projects-enter-active,
.projects-leave-active {
  transition: all 0.5s ease;
}
.projects-enter-from,
.projects-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
</style>
