<script>
export default {
  data() {
    return {
      state: false
    }
  }
}
</script>

<template>
  <div class="school">
    <div class="school-logo">
      <slot name="logo"></slot>
    </div>
    <p class="school-title">
      <slot name="title"></slot>
    </p>
    <p class="school-date">
      <slot name="date"></slot>
    </p>
    <p class="school-subtitle">
      <slot name="subtitle"></slot>
    </p>
  </div>
</template>

<style>
.school {
  padding: 8px;
  text-align: center;
  display: inline-block;
  padding: 16px 32px;
  width: 320px;
  text-align: center;
  transition: .1s ease-out;
  cursor: pointer
}

.school:hover {
  background-color: rgba(0, 0, 0, .1);
}

.school .school-logo {
  display: inline-block;
  height: 70px;
  min-width: 70px;
  max-width: 70px;
}

.school .school-logo img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.school .school-title {
  font-weight: bold;
  font-size: 1.2em;
}

.school .school-date {
  font-size: 0.9em;
  font-style: italic;
  font-weight: lighter;
  margin-bottom: 4px;
}

.school .school-subtitle {
  color: rgb(var(--parcours-dot-primary));
  font-weight: 600;
  margin-bottom: 16px;
}
</style>
