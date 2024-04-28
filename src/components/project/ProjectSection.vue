<script>
import searchbar from '@/components/project/projectSearchbar.vue'
import projectComponent from '@/components/project/ProjectComponent.vue'
import projectTag from '@/components/project/ProjectTag.vue'

export default {
  data() {
    return {
      projects: [
        {
          image: {
            class: 'cover',
            src: 'https://img.freepik.com/free-photo/sunset-silhouettes-trees-mountains-generative-ai_169016-29371.jpg?size=626&ext=jpg&ga=GA1.1.1224184972.1714003200&semt=ais'
          },
          title: 'Anycoast',
          tags: [
            {
              color: 'green',
              name: 'NodeJS'
            }
          ],
          route: { name: 'Anycoast' }
        },
        {
          image: {
            class: 'cover'
          },
          title: 'Anycoast',
          tags: [
            {
              color: 'green',
              name: 'NodeJS'
            }
          ],
          route: { name: 'Anycoast' }
        }
      ]
    }
  },
  components: { searchbar, projectComponent, projectTag }
}
</script>

<template>
  <div class="container section">
    <h2 class="home-title">💻 Projets</h2>
    <searchbar></searchbar>
    <div class="projects">
      <projectComponent v-for="p in projects" :key="p" @click="$router.push(p.route)">
        <template #image>
          <img v-if="p.image.src" v-bind="p.image" />
          <p v-else>Aucune image</p>
        </template>
        <template #title>{{ p.title }}</template>
        <template #tag>
          <projectTag v-for="t in p.tags" :key="t" :color="t.color">{{ t.name }}</projectTag>
        </template>
      </projectComponent>
    </div>
  </div>
</template>

<style>
.projects {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 32px;
}
</style>
