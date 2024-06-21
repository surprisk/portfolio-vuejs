<script>
import searchbar from '@/components/project/projectSearchbar.vue'
import projectComponent from '@/components/project/projectComponent.vue'
import projectTag from '@/components/project/projectTag.vue'
import projectFilter from '@/components/project/projectFilter.vue'
import IconLucide from '../icons/IconLucide.vue'

export default {
  data() {
    return {
      projects: [
        {
          image: {
            class: 'cover',
            src: 'https://img.freepik.com/free-photo/sunset-silhouettes-trees-mountains-generative-ai_169016-29371.jpg?size=626&ext=jpg&ga=GA1.1.1224184972.1714003200&semt=ais'
          },
          title: 'Jaxa',
          tags: [4],
          route: { name: 'Jaxa' }
        },
        {
          image: {
            class: 'cover',
            src: 'https://img.freepik.com/free-photo/sunset-silhouettes-trees-mountains-generative-ai_169016-29371.jpg?size=626&ext=jpg&ga=GA1.1.1224184972.1714003200&semt=ais'
          },
          title: 'Anycoast',
          tags: [4],
          route: { name: 'Anycoast' }
        },
        {
          image: {
            class: 'cover'
          },
          title: 'SavEat',
          tags: [0, 1, 3, 4, 6],
          route: { name: 'SavEat' }
        },
        {
          image: {
            class: 'cover',
            src: 'https://img.freepik.com/free-photo/sunset-silhouettes-trees-mountains-generative-ai_169016-29371.jpg?size=626&ext=jpg&ga=GA1.1.1224184972.1714003200&semt=ais'
          },
          title: 'QuerYT',
          tags: [4],
          route: { name: 'QuerYT' }
        },
        {
          image: {
            class: 'cover',
            src: 'https://img.freepik.com/free-photo/sunset-silhouettes-trees-mountains-generative-ai_169016-29371.jpg?size=626&ext=jpg&ga=GA1.1.1224184972.1714003200&semt=ais'
          },
          title: 'BirdAPI',
          tags: [4],
          route: { name: 'BirdAPI' }
        },
        {
          image: {
            class: 'cover',
            src: 'https://img.freepik.com/free-photo/sunset-silhouettes-trees-mountains-generative-ai_169016-29371.jpg?size=626&ext=jpg&ga=GA1.1.1224184972.1714003200&semt=ais'
          },
          title: 'NodeJSON',
          tags: [0, 1, 2, 4],
          route: { name: 'NodeJSON' }
        },
        {
          image: {
            class: 'cover',
            src: 'https://img.freepik.com/free-photo/sunset-silhouettes-trees-mountains-generative-ai_169016-29371.jpg?size=626&ext=jpg&ga=GA1.1.1224184972.1714003200&semt=ais'
          },
          title: 'Serveur Linux Maison',
          tags: [8],
          route: { name: 'Homelab' }
        }
      ],
      tags: [
        {
          color: 'rgb(229, 83, 44)',
          name: 'HTML'
        },
        {
          color: 'rgb(61, 157, 215)',
          name: 'CSS'
        },
        {
          color: 'rgb(248, 224, 38)',
          name: 'Javascript'
        },
        {
          color: 'rgb(72, 186, 135)',
          name: 'VueJS'
        },
        {
          color: 'rgb(148, 199, 70)',
          name: 'NodeJS'
        },
        {
          color: 'rgb(8, 8, 8)',
          name: 'Symfony'
        },
        {
          color: 'rgb(8, 8, 8)',
          name: 'MySQL'
        },
        {
          color: 'rgb(8, 8, 8)',
          name: 'MongoDB'
        },
        {
          color: 'rgb(8, 8, 8)',
          name: 'Linux'
        }
      ],
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
      let deepProjects = [...this.projects]

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
    <div
      style="
        font-style: italic;
        font-size: 0.8em;
        text-align: center;
        margin-bottom: 32px;
        padding: 8px;
        color: #fff;
        background-color: #d98880;
      "
    >
      La section est en cours de réalisation. Les projets affichés ont bien été réalisés par mes
      soins, n'hésitez pas à me contact pour obtenir des détails sur leur réalisation.
    </div>
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
