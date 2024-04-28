<script>
import item from '@/components/parcours/parcoursItem.vue'

export default {
  data() {
    return {
      timebar: [],
      parcours: [
        {
          date: 2024,
          content: [
            {
              logo: {
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS4qwoK9i4sG4RQj7dgzaMjSanKbKexWNnWkntaaxzcdg&s',
                alt: 'Logo SIPEJ'
              },
              title: 'Développeur web',
              date: '1mois - 2019 - Stage',
              subtitle: 'SIPEJ, Saint-Pierre-du-Perray',
              description: [
                'Maintenance du site Internet.',
                'Création de modules applicatifs (système d’actualités avec photo)',
                'Gestion de la base de données.',
                'Utilisation des langages : JavaScript, PHP, SQL et framework bootstrap.'
              ]
            }
          ],
          timebar: ['', '', '', '', '', '', '']
        },
        {
          date: 2023,
          content: [
            {
              logo: {
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS4qwoK9i4sG4RQj7dgzaMjSanKbKexWNnWkntaaxzcdg&s',
                alt: 'Logo SIPEJ'
              },
              title: 'Développeur web',
              date: '1mois - 2019 - Stage',
              subtitle: 'SIPEJ, Saint-Pierre-du-Perray',
              description: [
                'Maintenance du site Internet.',
                'Création de modules applicatifs (système d’actualités avec photo)',
                'Gestion de la base de données.',
                'Utilisation des langages : JavaScript, PHP, SQL et framework bootstrap.'
              ]
            }
          ],
          timebar: ['', '', '', '', '', '', '']
        },
        {
          date: 2022,
          content: [
            {
              logo: {
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS4qwoK9i4sG4RQj7dgzaMjSanKbKexWNnWkntaaxzcdg&s',
                alt: 'Logo SIPEJ'
              },
              title: 'Développeur web',
              date: '1mois - 2019 - Stage',
              subtitle: 'SIPEJ, Saint-Pierre-du-Perray',
              description: [
                'Maintenance du site Internet.',
                'Création de modules applicatifs (système d’actualités avec photo)',
                'Gestion de la base de données.',
                'Utilisation des langages : JavaScript, PHP, SQL et framework bootstrap.'
              ]
            }
          ],
          timebar: ['', '', '', '', '', '', '']
        },
        {
          date: 2021,
          content: [
            {
              logo: {
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS4qwoK9i4sG4RQj7dgzaMjSanKbKexWNnWkntaaxzcdg&s',
                alt: 'Logo SIPEJ'
              },
              title: 'Développeur web',
              date: '1mois - 2019 - Stage',
              subtitle: 'SIPEJ, Saint-Pierre-du-Perray',
              description: [
                'Maintenance du site Internet.',
                'Création de modules applicatifs (système d’actualités avec photo)',
                'Gestion de la base de données.',
                'Utilisation des langages : JavaScript, PHP, SQL et framework bootstrap.'
              ]
            }
          ],
          timebar: ['', '', '', '', '', '', '']
        },
        {
          date: 2020,
          content: [
            {
              logo: {
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS4qwoK9i4sG4RQj7dgzaMjSanKbKexWNnWkntaaxzcdg&s',
                alt: 'Logo SIPEJ'
              },
              title: 'Développeur web',
              date: '1mois - 2019 - Stage',
              subtitle: 'SIPEJ, Saint-Pierre-du-Perray',
              description: [
                'Maintenance du site Internet.',
                'Création de modules applicatifs (système d’actualités avec photo)',
                'Gestion de la base de données.',
                'Utilisation des langages : JavaScript, PHP, SQL et framework bootstrap.'
              ]
            }
          ],
          timebar: ['', '', '', '', '', '', '']
        },
        {
          date: 2019,
          content: [
            {
              logo: {
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS4qwoK9i4sG4RQj7dgzaMjSanKbKexWNnWkntaaxzcdg&s',
                alt: 'Logo SIPEJ'
              },
              title: 'Développeur web',
              date: '1mois - 2019 - Stage',
              subtitle: 'SIPEJ, Saint-Pierre-du-Perray',
              description: [
                'Maintenance du site Internet.',
                'Création de modules applicatifs (système d’actualités avec photo)',
                'Gestion de la base de données.',
                'Utilisation des langages : JavaScript, PHP, SQL et framework bootstrap.'
              ]
            }
          ],
          timebar: ['', '', '', '', '', '', '']
        },
        {
          date: 2018,
          content: [
            {
              logo: {
                src: 'https://image-parcours.copainsdavant.com/image/750/1760127760/4147743.png',
                alt: 'Logo Lycée Parc des Loges'
              },
              title: 'BTS Services Informatiques aux Organisations',
              date: '2ans - 2018/2020',
              subtitle: 'Lycée Parc des Loges, Evry',
              description: ''
            }
          ],
          timebar: ['', '', '', '', '', 'lower', 'full']
        }
      ]
    }
  },
  components: {
    item
  },
  methods: {
    timebarHandler(position, state) {
      const parcoursTimebar = this.parcours[position].timebar
      parcoursTimebar.forEach((c, i) => {
        if (c != '') this.timebar[i] = state ? c : ''
      })
    }
  }
}
</script>

<template>
  <div class="container section">
    <h2 class="home-title">🚩 Parcours</h2>
    <div class="parcours">
      <item
        v-for="(p, i) in parcours"
        :key="p"
        :id="`experience_${p.date}`"
        @timebar="timebarHandler"
        :position="i"
      >
        <template #content>
          <div class="experience" v-for="c in p.content" :key="c">
            <div class="experience-logo">
              <img v-bind="c.logo" />
            </div>
            <div class="experience-content">
              <p class="experience-title">
                {{ c.title }}
              </p>
              <p class="experience-date">({{ c.date }})</p>
              <p class="experience-subtitle">{{ c.subtitle }}</p>
              <ul class="experience-description">
                <li v-for="d in c.description" :key="d">{{ d }}</li>
              </ul>
            </div>
          </div>
        </template>
        <template #date>{{ p.date }}</template>
        <template #timebar><span class="timebar" :class="[this.timebar[i]]"></span></template>
      </item>
      <span class="start-dot"></span>
      <span class="end-dot"></span>
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

span.timebar {
  z-index: -1;
  background: rgb(var(--gradient-primary));
  width: 4px;
  position: absolute;
  left: calc(50% - 4px);
  transform: translateX(-50%);
  opacity: 0;
  transition: 0.2s linear;
}

span.timebar.full {
  height: 100%;
  top: 0;
  opacity: 1;
}

span.timebar.upper {
  top: 0;
  height: 50%;
  opacity: 1;
}

span.timebar.lower {
  top: 50%;
  height: 50%;
  opacity: 1;
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

.parcours .experience {
  display: flex;
  gap: 32px;
  font-size: 0.8em;
}

.parcours .experience:not(:last-child) {
  margin-bottom: 32px;
}

.parcours .experience .experience-title {
  font-weight: bold;
  font-size: 1.2em;
}

.parcours .experience .experience-date {
  font-size: 0.9em;
  font-style: italic;
  font-weight: lighter;
  margin-bottom: 4px;
}

.parcours .experience .experience-logo {
  height: 70px;
  min-width: 70px;
  max-width: 70px;
}

.parcours .experience .experience-logo img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.parcours .experience .experience-subtitle {
  color: rgb(var(--parcours-dot-primary));
  font-weight: 600;
  margin-bottom: 16px;
}

.parcours .experience ul.experience-description {
  list-style: square;
  font-size: 0.9em;
}
</style>
