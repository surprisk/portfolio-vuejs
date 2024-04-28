<script>
import a_propos from '@/components/a_propos/a_proposSection.vue'
import parcours from '@/components/parcours/parcoursSection.vue'
import projects from '@/components/project/ProjectSection.vue'
import contact from '@/components/contact/contactSection.vue'

export default {
  data() {
    return {
      talents: ['Autodidacte', 'Passionné', 'Développeur Web', 'JS lover', 'Brestois'],
      talentHandler: 0
    }
  },
  components: { projects, a_propos, parcours, contact },
  computed: {
    getCurrentTalent() {
      return this.talents[this.talentHandler]
    }
  },
  methods: {
    scrollToAnElement(element) {
      const elementDOM = document.querySelector(element)
      const barDOM = document.querySelector('nav.navbar')

      const elementTop = elementDOM.getBoundingClientRect().top
      const barHeight = barDOM.offsetHeight

      window.scrollTo({
        top: window.scrollY + elementTop - barHeight,
        behavior: 'smooth'
      })
    }
  },
  created() {
    setInterval(() => {
      this.talentHandler >= this.talents.length - 1
        ? (this.talentHandler = 0)
        : this.talentHandler++
    }, 3000)
  }
}
</script>

<template>
  <div class="home-banner">
    <div class="banner-content container">
      <p>Samuel Brosse</p>
      <p>{{ this.getCurrentTalent }}</p>
    </div>
    <div class="mouse" @click="scrollToAnElement('#a_propos_section')"></div>
  </div>
  <main>
    <a_propos />
    <parcours />
    <projects />
    <contact />
  </main>
</template>

<style>
.home-banner {
  display: flex;
  align-items: center;

  width: 100vw;
  height: 800px;

  background: rgb(119, 67, 219);
  background: radial-gradient(
    circle,
    rgba(var(--gradient-primary), 1) 60%,
    rgba(var(--gradient-secondary), 1) 95%,
    rgba(var(--gradient-third), 0.8) 100%
  );
  background-position: center;
  backdrop-filter: brightness(10%);

  color: rgb(var(--banner-color));
  text-align: center;
  animation: 5s linear 2s infinite alternate banner;

  margin-bottom: 128px;
}

.home-banner .banner-content p:first-child {
  font-size: 2em;
  /* font-weight: bolder; */
}

.home-banner .banner-content p:last-child {
  font-size: 4em;
  font-weight: bold;
}

.mouse {
  position: absolute;
  bottom: 50px;
  left: 50%;
  transform: translate(-50%);
  width: 40px;
  height: 70px;
  border: 3px solid rgb(var(--banner-color));
  border-radius: 60px;
  cursor: pointer;
  &::before {
    content: '';
    width: 10px;
    height: 10px;
    position: absolute;
    top: 8px;
    left: 50%;
    transform: translateX(-50%);
    background-color: rgb(var(--banner-color));
    border-radius: 50%;
    opacity: 1;
    animation: wheel 2s infinite;
    -webkit-animation: wheel 2s infinite;
  }
}

@keyframes wheel {
  to {
    opacity: 0;
    top: 50px;
  }
}

@-webkit-keyframes wheel {
  to {
    opacity: 0;
    top: 50px;
  }
}

@keyframes banner {
  from {
    background-size: 100%;
  }
  to {
    background-size: 120%;
  }
}

@-webkit-keyframes banner {
  from {
    background-size: 100%;
  }
  to {
    background-size: 120%;
  }
}

.home-title {
  margin-bottom: 64px;
}
</style>
