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
        history: [],
        state: []
      },
      db: database,
    }
  },
  components: {
    item,
    school,
    experience
  },
  methods: {
    timebarHandler(position, state) {
      if(this.timebar.history.length > 0)
        this.timebar.state[this.timebar.history.pop()] = false

      this.timebar.state[position] = !state
      this.timebar.history.push(position)

      this.timebar.current =
        !state ? this.db.schools[position]?.timebar : []
    }
  },
  mounted(){
    for (let index = 0; index < this.db.schools.length; index++)
      this.timebar.state.push(false)
  }
}
</script>

<template>
  <div id="parcours_section" class="container section">
    <h2 class="home-title">🚩 Parcours</h2>
    <div class="parcours">
      <item
        v-for="(p, i) in this.db.parcours"
        :key="p"
        :id="`experience_${p.date}`"
        @timebar="timebarHandler"
        :position="i"
        :hasContent="!!p.content"
      >
        <template #content>
          <experience v-for="c in p.content" :key="c" :e="c"/>
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
      <school v-for="c, i in this.db.schools" :key="c" :s="c.content" :position="i" @timebar="timebarHandler" :state="this.timebar.state[i]"/>
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
