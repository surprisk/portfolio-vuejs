<script>
import { RouterLink, RouterView } from 'vue-router' // eslint-disable-line

export default {
  data() {
    return {
      isOpened: false,
      scroll: false
    }
  },
  methods: {
    handleScroll() {
      this.scroll = window.scrollY > 50
    }
  },
  created() {
    window.addEventListener('scroll', this.handleScroll)
  },
  unmounted() {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<template>
  <nav class="navbar" :class="{ scroll: scroll }">
    <div class="navbar-wrapper container">
      <div class="navbar-title">
        <a href="#">Portfolio.</a>
      </div>
      <div class="navbar-menu" :class="{ 'is-opened': isOpened }">
        <ul>
          <li><a href="#">A propos</a></li>
          <li><a href="#">Parcours</a></li>
          <li><a href="#">Projets</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </div>
      <div
        class="navbar-hamburger"
        @click="this.isOpened = !this.isOpened"
        :class="{ 'is-opened': isOpened }"
      >
        <span></span>
      </div>
    </div>
  </nav>
</template>

<style>
.navbar {
  background: transparent;
  position: fixed;
  z-index: 5;
  width: 100vw;
  transition: 0.2s linear;
}

.navbar.scroll {
  background: rgb(var(--nav-background));
  box-shadow: 0 0 30px rgb(var(--gradient-secondary), 0.6);
}

.navbar .navbar-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar .navbar-title {
  font-size: 2em;
  font-weight: bold;
}

.navbar .navbar-menu ul {
  display: flex;
  gap: 32px;
}

.navbar .navbar-menu ul {
  display: flex;
  gap: 40px;
}

.navbar :is(.navbar-menu ul li a, a) {
  color: rgb(var(--nav-color));
}

.navbar .navbar-menu ul li a:is(.active, :focus, :hover, :active) {
  color: rgb(var(--nav-active));
  border-bottom: 1px rgb(var(--nav-active)) solid;
}

.navbar .navbar-hamburger {
  display: none;

  position: relative;
  width: 40px;
  height: 40px;
  cursor: pointer;

  transition: transform 0.5s;
}

.navbar .navbar-hamburger span {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translateX(-50%) translateY(-50%);

  display: block;
  width: 22px;
  height: 2px;

  background-color: #fff;

  transition: background 0.5s;
}

.navbar .navbar-hamburger span::before,
.navbar .navbar-hamburger span::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  transform: translateY(-6px);

  display: block;
  width: 22px;
  height: 2px;

  background-color: #fff;

  transition: transform 0.5s;
}
.navbar .navbar-hamburger span::after {
  transform: translateY(6px);
}

.navbar .navbar-hamburger.is-opened span {
  background: transparent;
}
.navbar .navbar-hamburger.is-opened span::before {
  transform: translateY(0) rotate(45deg);
}
.navbar .navbar-hamburger.is-opened span::after {
  transform: translateY(0) rotate(-45deg);
}
.navbar .navbar-hamburger.is-opened {
  transform: rotate(180deg);
}

@media screen and (max-width: 600px) {
  .navbar .navbar-menu {
    position: absolute;

    display: flex;
    justify-content: center;
    align-items: center;

    top: 0;
    width: 100%;
    height: 100vh;
    right: -100%;

    background-color: rgba(var(--nav-background), 0.6);
    backdrop-filter: blur(16px);
    font-size: 1.5em;

    transition: 0.8s ease-out;
  }
  .navbar .navbar-menu.is-opened {
    right: 0;
  }

  .navbar .navbar-menu ul {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .navbar .navbar-hamburger {
    display: unset;
  }
}
</style>
