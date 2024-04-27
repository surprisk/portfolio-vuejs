<script>
export default {
  data() {
    return {}
  }
}
</script>

<template>
  <div class="project">
    <div class="project-image"><slot name="image"></slot></div>
    <div class="project-title">
      <h3><slot name="title"></slot></h3>
    </div>
    <div class="project-tag"><slot name="tag"></slot></div>
  </div>
</template>

<style>
.project {
  border-radius: 16px;
  flex-basis: 350px;
  overflow: hidden;
  background-color: rgb(var(--card-background));
  padding-bottom: 8px;
  cursor: pointer;
  transition: 0.2s ease;
}

.project:hover {
  transform: scale(1.05);
}

.project > div:not(:first-child) {
  padding: 10px 16px;
}

.project .project-image {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 150px;
  background: rgb(var(--gradient-primary));
  background: linear-gradient(
    45deg,
    rgba(var(--gradient-primary), 1) 45%,
    rgba(var(--gradient-secondary), 1) 90%,
    rgba(var(--gradient-third), 1) 100%
  );
  text-align: center;
}

.project .project-image img.cover {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.project .project-image :is(p, span) {
  font-size: 2em;
  font-weight: bolder;
  color: rgb(var(--nav-color));
}

.project .project-tag {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
</style>
