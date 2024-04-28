<script>
export default {
  data() {
    return {}
  }
}
</script>

<template>
  <footer class="footer">
    <div class="container">
      © {{ new Date().getFullYear() }} Création & Développement par Samuel BROSSE | Tous droits
      réservés
    </div>
  </footer>
</template>

<style>
.footer {
  width: 100vw;
  background: rgb(var(--footer-background));
  text-align: center;
  color: rgb(var(--footer-color));
}
</style>
