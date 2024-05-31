<script>
import IconLucide from '@/components/icons/IconLucide.vue'

export default {
  data() {
    return {}
  },
  components: {
    IconLucide
  }
}
</script>

<template>
  <div id="contact_section" class="contact-section-wrapper section">
    <div class="container">
      <h2 class="home-title">📨 Contact</h2>
      <div class="contact">
        <div class="contact-item">
          <div class="contact-icon">
            <IconLucide icon="Send"></IconLucide> Mail
          </div>
          <a class="contact-link" href="mailto:brosse.samuel91@gmail.com">brosse.samuel91@gmail.com</a>
        </div>
        <div class="contact-item">
          <div class="contact-icon">
            <IconLucide icon="Linkedin"></IconLucide> LinkedIn
          </div>
          <a class="contact-link" href="https://www.linkedin.com/in/samuel-brosse-web/">linkedin.com/in/samuel-brosse-web</a>
        </div>
        <div class="contact-item">
          <div class="contact-icon">
            <IconLucide icon="Github"></IconLucide> Github
          </div>
          <a class="contact-link" href="https://github.com/surprisk">github.com/surprisk</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.contact-section-wrapper {
  background-color: rgb(var(--contact-background));
}

.contact-section-wrapper .home-title{
  margin-bottom: 128px;
}

.contact{
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 64px;
}

.contact .contact-icon{
  font-size: 2em;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 8px;
  margin-bottom: 16px;
  user-select: none;
}

.contact .contact-item{
  min-width: 325px;
  text-align: center;
  transition: .1s ease-out;
}

.contact .contact-item:hover{
  transform: scale(1.05);
}

.contact .contact-item:hover > a.contact-link{
  transition: .1s ease-out;
  color: rgb(var(--contact-link));
}
</style>
