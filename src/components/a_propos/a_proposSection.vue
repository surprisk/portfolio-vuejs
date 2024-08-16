<script>
export default {
  data() {
    return {}
  },
  methods: {
    getYearFromDate(date) {
      return Math.floor((new Date() - new Date(date).getTime()) / 3.15576e10)
    }
  },
  computed: {
    getAge() {
      return this.getYearFromDate('2000-02-04')
    },
    getArrival() {
      return this.getYearFromDate('2021-06-01')
    }
  }
}
</script>

<template>
  <div id="a_propos_section" class="container section">
    <h2 class="home-title">🙎🏼 A propos</h2>
    <div class="a-propos">
      <div class="a-propos-image">
        <img src="@/assets/avatar.jpg" />
      </div>
      <div class="a-propos-content">
        <h3>L'informatique, de la magie à la passion</h3>
        <p class="a-propos-text">
          Je m'appelle Samuel, j'ai {{ this.getAge }} ans cela fait maintenant
          {{ this.getArrival }} ans que je suis arrivé dans le finistère et je vais vous raconter
          brièvement comment je suis me suis pris d'affection pour le développement d'applications
          web. Au départ ce n'était pas gagné, j'ai grandi loin des ordinateurs et des jeux vidéo.
          Avant de passer mon baccalauréat, je pensais que travail rimait avec ennui mortel. Ne
          sachant pas ce que je souhaitais faire, j'ai écumé bon nombre de salons de l'étudiant,
          mais aucune filière ne me m'attirait vraiment. Mon choix s'est finalement porté sur un BTS
          SIO, après tout, je n'étais pas mauvais avec un clavier sur les jeux vidéo. Et c'est là
          que j'ai compris que le travail pouvait être ludique. Depuis ce jour, le développement
          d'applications web fait parti de mes nombreuses passions que je pratique quotidiennement,
          notamment entre deux sessions de jeu ;)
        </p>
        <div class="a-propos-stack">
          <span>Stack</span>
          <img src="@/assets/stack/nodejs.png" alt="NodeJS" />
          <img src="@/assets/stack/js.png" alt="JS" />
          <img src="@/assets/stack/vuejs.png" alt="VueJS" />
          <img src="@/assets/stack/php.png" alt="PHP" />
          <img src="@/assets/stack/symfony.png" alt="Symfony" />
          <img src="@/assets/stack/docker.png" alt="Docker" />
          <img src="@/assets/stack/mysql.png" alt="MySQL" />
          <img src="@/assets/stack/mongodb.png" alt="MongoDB" />
          <span>et plus encore...</span>
        </div>
        <div class="a-propos-os">
          <span>Systèmes d'exploitation</span>
          <img src="@/assets/os/apple.png" alt="Apple" />
          <img src="@/assets/os/windows.png" alt="Windows" />
          <img src="@/assets/os/debian.png" alt="Debian" />
          <img src="@/assets/os/ubuntu.png" alt="Ubuntu" />
        </div>
        <div class="a-propos-hobbies">
          <span>Passions</span>
          <img src="@/assets/hobbies/movies.png" alt="Films" />
          <img src="@/assets/hobbies/video-games.png" alt="Jeux vidéo" />
          <img src="@/assets/hobbies/fishing.png" alt="Pêche" />
          <img src="@/assets/hobbies/hiking.png" alt="Randonnée" />
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.a-propos {
  display: flex;
  gap: 64px;
}

.a-propos .a-propos-image {
  min-width: 200px;
  height: 200px;
  border-radius: 100px;
  overflow: hidden;
  box-shadow: 0px 0px 50px rgba(var(--gradient-primary), 0.5);
}

.a-propos .a-propos-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.a-propos .a-propos-content {
  text-align: justify;
}

.a-propos .a-propos-content h3 {
  margin-bottom: 32px;
}

.a-propos .a-propos-content .a-propos-text {
  margin-bottom: 64px;
}

.a-propos :is(.a-propos-stack, .a-propos-os, .a-propos-hobbies) {
  display: flex;
  align-items: center;
  gap: 15px;
  flex-wrap: wrap;
  margin: 16px auto;
}

.a-propos :is(.a-propos-stack, .a-propos-os, .a-propos-hobbies) img {
  height: 2em;
  filter: grayscale(100%);
  transition: 0.2 ease;
}

.a-propos :is(.a-propos-stack, .a-propos-os, .a-propos-hobbies) img:hover {
  filter: grayscale(0);
}

@media screen and (max-width: 900px) {
  .a-propos {
    justify-content: center;
    flex-wrap: wrap;
  }
}
</style>
