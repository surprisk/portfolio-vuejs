<script>
import item from '@/components/parcours/parcoursItem.vue'
import school from '@/components/parcours/parcoursSchool.vue'
import experience from '@/components/parcours/parcoursExperience.vue'
import database from '@/assets/database.json';

export default {
  data() {
    return {
      timebar: {
        current: [],
        history: []
      },
      db: database,
      parcours: database.parcours
    }
  },
  components: {
    item,
    school,
    experience
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
          <experience v-for="c in p.content" :key="c" :e="c"/>
        </template>
        <template #date>{{ p.date }}</template>
        <template #timebar
          ><span class="timebar" :class="[this.timebar.current[i]]"></span
        ></template>
      </item>
      <span class="start-dot"></span>
      <span class="end-dot"></span>
    </div>
    <div class="schools">
      <school v-for="s in this.db.schools" :key="s">
        <template #logo>
          <img v-bind="s.content.logo" />
        </template>
        <template #title>{{ s.content.title }}</template>
        <template #date>{{ s.content.date }}</template>
        <template #subtitle> {{ s.content.subtitle }}</template>
      </school>
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

.schools{
  margin-top: 64px;
  font-size: 0.8em;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
