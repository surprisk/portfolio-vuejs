<script>
import item from '@/components/parcours/parcoursItem.vue'
import school from '@/components/parcours/parcoursSchool.vue'
import experience from '@/components/parcours/parcoursExperience.vue'

import lyceeparcdesloges from '@/assets/schools/logo-lyceeparcdesloges.webp'
import mydigitalschool from '@/assets/schools/logo-mydigitalschool.png'
import brestopencampus from '@/assets/schools/logo-brestopencampus.png'

import randstaddigital from '@/assets/experiences/logo-randstaddigital.png'
import creditmutuelarkea from '@/assets/experiences/logo-creditmutuelarkea.webp'
import netao from '@/assets/experiences/logo-netao.png'
import promomatelas from '@/assets/experiences/logo-promomatelas.png'
import sipej from '@/assets/experiences/logo-sipej.jpg'
import enedis from '@/assets/experiences/logo-enedis.png'

export default {
  data() {
    return {
      timebar: {
        current: [],
        history: [],
        state: []
      },
      schools: [
        {
          content: {
            logo: {
              src: lyceeparcdesloges,
              alt: 'Logo Lycée Parc des Loges'
            },
            title: 'BTS Services Informatiques aux Organisations',
            date: '2ans - 2018/2020',
            subtitle: 'Lycée Parc des Loges, Evry'
          },
          timebar: ['', '', '', 'lower', 'full', 'upper', '']
        },
        {
          content: {
            logo: {
              src: mydigitalschool,
              alt: 'Logo MyDigitalSchool'
            },
            title: 'Bachelor Développeur web et mobile',
            date: '1an - 2020/2021',
            subtitle: 'MyDigitalSchool, Angers'
          },
          timebar: ['', '', 'lower', 'upper', '', '', '']
        },
        {
          content: {
            logo: {
              src: brestopencampus,
              alt: 'Logo Brest Open Campus'
            },
            title: 'Mastère Manager de projets innovants',
            date: '2ans - 2021/2023',
            subtitle: 'LaDigitalSchool, Brest'
          },
          timebar: ['lower', 'full', 'upper', '', '', '', '']
        }
      ],
      parcours: [
        {
          date: 2023,
          content: [
            {
              logo: {
                src: randstaddigital,
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
          ]
        },
        {
          date: 2022,
          content: [
            {
              logo: {
                src: creditmutuelarkea,
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
          ]
        },
        {
          date: 2021,
          content: [
            {
              logo: {
                src: netao,
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
          ]
        },
        {
          date: 2020,
          content: [
            {
              logo: {
                src: promomatelas,
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
            },
            {
              logo: {
                src: enedis,
                alt: 'Logo Enedis'
              },
              title: 'Développeur web',
              date: '1mois - 2020 - Stage',
              subtitle: 'Enedis, Noisy-Le-Grand',
              description: [
                'Maintenance du site intranet.',
                'Création de modules applicatifs et utilisation de fichiers json (affichage de données et de graphiques).',
                'Gestion de la base de données.',
                'Utilisation des langages : JavaScript(Ajax), PHP Poo, SQL et framework bootstrap.'
              ]
            }
          ]
        },
        {
          date: 2019,
          content: [
            {
              logo: {
                src: sipej,
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
          ]
        },
        {
          date: 2018
        }
      ]
    }
  },
  components: {
    item,
    school,
    experience
  },
  methods: {
    timebarHandler(position, state) {
      if (this.timebar.history.length > 0) this.timebar.state[this.timebar.history.pop()] = false

      this.timebar.state[position] = !state
      this.timebar.history.push(position)

      this.timebar.current = !state ? this.schools[position]?.timebar : []
    }
  },
  mounted() {
    for (let index = 0; index < this.schools.length; index++) this.timebar.state.push(false)
  }
}
</script>

<template>
  <div class="parcours-section-wrapper">
    <div id="parcours_section" class="container section">
      <h2 class="home-title">🚩 Parcours</h2>
      <div class="parcours">
        <item
          v-for="(p, i) in this.parcours"
          :key="p"
          :id="`experience_${p.date}`"
          @timebar="timebarHandler"
          :position="i"
          :hasContent="!!p.content"
        >
          <template #content>
            <experience v-for="c in p.content" :key="c" :e="c" />
          </template>
          <template #date>{{ p.date }}</template>
          <template #timebar>
            <span class="timebar" :class="[this.timebar.current[i]]"></span>
          </template>
        </item>
        <span class="start-dot"></span>
        <span class="end-dot"></span>
      </div>
      <div class="schools">
        <school
          v-for="(c, i) in this.schools"
          :key="c"
          :s="c.content"
          :position="i"
          @timebar="timebarHandler"
          :state="this.timebar.state[i]"
        >
        </school>
      </div>
    </div>
  </div>
</template>

<style>
.parcours-section-wrapper {
  background-color: rgba(var(--parcours-background));
}

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

.schools {
  margin-top: 64px;
  font-size: 0.8em;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
