<script>
import item from '@/components/parcours/parcoursItem.vue'

export default {
  data() {
    return {
      timebar: {
        current: [],
        history: []
      },
      parcours: [
        {
          date: 2023,
          content: [
            {
              logo: {
                src: 'https://www.grouperandstad.fr/wp-content/uploads/2023/08/image-a-mettre-en-avant-2.png',
                alt: 'Logo Randstad Digital'
              },
              title: 'Développeur web VueJS',
              date: '1an - 2023 - CDI',
              subtitle: 'Randstad digital (ex AUSY), Brest',
              description: [
                'Cadrage du projet. (Lecture du cahier des charges, brainstorming, reflexion autour des features, ...)',
                'Élaboration du schéma de données.',
                "Proposition d'une stack technique.",
                "Échanges agile avec l'ensemble des MOA du projet.",
                'Création de la base de données PostgreSQL.',
                'Création des dépôts GitHub. (Front, back, database)',
                "Rédaction de la documentation technique relative à la configuration de l'environnement de développement sur machine personnelle.",
                "Configuration d'une machine Debian. (Création des utilisateurs et de leurs droits, configuration du SSH, du Fail2Ban et du pare-feu, ajout d'un dossier partagé entre les utilisateurs, ...)",
                "Production d'une maquette sur l'outil Adobe XD.",
                "Création de l'application front-end.",
                'Référent VueJS sur le projet.',
                'Création des vues et configuration du router.',
                "Production des composants front-end liés à l'API back-end.",
                'Développement de la brique de connexion.'
              ]
            }
          ],
          timebar: ['upper', '', '', '', '', '', '']
        },
        {
          date: 2022,
          content: [
            {
              logo: {
                src: 'https://nd2d.fr/wp-content/uploads/2021/03/Sans-titre-19-1024x1024.png',
                alt: 'Logo Crédit Mutuel Arkéa'
              },
              title: 'Chef de projet transverse',
              date: '1an - 2022 - Alternance',
              subtitle: 'Crédit Mutuel Arkéa, Le Relecq-Kerhuon',
              description: [
                "Animation d'ateliers avec les équipes. (Team building, Rétrospective, RACI, Gestion de problèmes, ...)",
                "Création d'outils de suivi. (Roadmap pour la factory, Calcul de CàF, Burnup, MVP, ...)",
                "Rédaction de documentation sur l'outil Confluence.",
                "Analyse d'indicateurs clés. (Stock/flux d'incidents, Confiance de squads, CàF, ...)",
                "Gestion de projets agile. (Scrum, Kanban, Découpage d'US, Rédaction de tickets JIRA)",
                "Refonte de l'espace documentaire commun à la factory sur la plateforme Confluence."
              ]
            }
          ],
          timebar: ['lower', 'upper', '', '', '', '', '']
        },
        {
          date: 2021,
          content: [
            {
              logo: {
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR_xUKlRkqekcyAfnVqTxH4vYKUfUrEBUltbfKZz7l_xQ&s',
                alt: 'Logo Netao'
              },
              title: 'Développeur web',
              date: '1an - 2021 - Alternance',
              subtitle: 'Netao, Quimper',
              description: [
                'Création de sites Wordpress (E-commerces & vitrines).',
                'Développement de plugins WordPress en PHP vanille.',
                'Déploiement des sites WordPress sur VPS (Dev & prod).',
                'Maintenance et mise à niveau des sites du parc.',
                'Mise à jour des thèmes.',
                'Participation à la création de maquettes.',
                'Configuration de VPS sous Ubuntu pour accueillir les futurs sites et bases de données.',
                "Installation de l'outil CloudPanel pour la gestion de site WordPress.",
                'Veille technologique sur le CMS WordPress et ses plugins.',
                'Rédaction de script Javascript adaptés aux besoins.',
                'Réalisation de thèmes en SCSS.',
                "Collaboration agile entre les différentes parties prenantes de l'entreprise."
              ]
            }
          ],
          timebar: ['', 'lower', 'upper', '', '', '', '']
        },
        {
          date: 2020,
          content: [
            {
              logo: {
                src: 'https://www.promo-matelas.com/matelas/vecto-logo-promo-matelas-02.png',
                alt: 'Logo Promo-matelas'
              },
              title: 'Développeur web',
              date: '1an - 2020 - Alternance',
              subtitle: 'Distrimob SARL, Sablé-sur-Sarthe',
              description: [
                'Étude du cahier des charges mis à ma disposition.',
                'Veille technologique.',
                'Rédaction des spécificités techniques.',
                'Découpage des US',
                "Production d'un diagramme de GANTT",
                "Modélisation, création et gestion d'une base de données MySQL complexe. (Procédures stockées, Vues, tables de liaisons)",
                "Création du back-end d'un site e-commerce à l'aide du framework Symfony 5.",
                'Création de vues avec Twig.',
                "Utilisation de l'ORM Doctrine.",
                'Réflexion UI/UX design.',
                "Production d'un wireframe.",
                'Maquetage du futur site e-commerce.',
                "Création d'un outil d'import/export des produits via fichier Excel.",
                'Maintenance du site existant en php.'
              ]
            }
          ],
          timebar: ['', '', 'lower', 'upper', '', '', '']
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
          timebar: ['', '', '', 'lower', 'full', 'full', 'full']
        }
      ]
    }
  },
  components: {
    item
  },
  methods: {
    timebarHandler(position, state) {
      if (state) this.timebar.history.push(position)
      else this.timebar.history = this.timebar.history.filter((p) => p != position)

      this.timebar.current =
        this.parcours[this.timebar.history[this.timebar.history.length - 1]]?.timebar ?? []
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
        <template #timebar
          ><span class="timebar" :class="[this.timebar.current[i]]"></span
        ></template>
      </item>
      <span class="start-dot"></span>
      <span class="end-dot"></span>
    </div>
  </div>
</template>

<style>
.parcours {
  position: relative;
  padding: 26px 0;
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
  left: calc(50%);
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
