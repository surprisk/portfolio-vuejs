<script>
export default {
  data() {
    return {
      state: this.hasContent ? false : true
    }
  },
  props: {
    position: {
      type: Number,
      required: true
    },
    hasContent: {
      type: Boolean,
      required: true
    }
  }
}
</script>

<template>
  <div class="parcours-item-line">
    <div class="parcours-item-wrapper">
      <Transition name="slide-fade" v-if="hasContent">
        <div class="parcours-item" v-show="this.state">
          <slot name="content"></slot>
        </div>
      </Transition>
      <span
        class="date-dot"
        :class="{ active: state, noContent: !this.hasContent }"
        @click="!this.hasContent || (this.state = !this.state)"
      ></span>
    </div>
    <span class="item-date" :class="{ active: state }">
      <slot name="date"></slot>
    </span>
    <slot name="timebar"></slot>
  </div>
</template>

<style>
.parcours-item-line {
  z-index: 2;
  display: flex;
  position: relative;
  align-items: center;
}

.parcours-item-line .parcours-item-wrapper .date-dot {
  width: 18px;
  height: 18px;
  border-radius: 9px;
  background-color: rgb(var(--parcours-dot-primary));
  left: 50%;
  top: 50%;
  position: absolute;
  transform: translate(-50%, -50%);
}

.parcours-item-line .parcours-item-wrapper :is(.date-dot:hover, .date-dot.active) {
  cursor: pointer;
  width: 25px;
  height: 25px;
  transition: 0.1s ease;
}

.parcours-item-line .parcours-item-wrapper .date-dot.noContent {
  cursor: inherit;
}

.parcours-item-line .parcours-item-wrapper :is(.date-dot:hover, .date-dot.active)::before {
  opacity: 0;
}

.parcours-item-line .parcours-item-wrapper .date-dot::before {
  content: '';
  border: 1px rgb(var(--parcours-dot-secondary)) solid;
  left: 50%;
  top: 50%;
  position: absolute;
  transform: translate(-50%, -50%);
  animation: heartbeat 1s ease-out infinite;
  -webkit-animation: heartbeat 1s ease-out infinite;
  border-radius: 20px;
  opacity: 1;
}

@keyframes heartbeat {
  from {
    width: 0;
    height: 0;
  }
  to {
    width: 25px;
    height: 25px;
  }
}

@-webkit-keyframes heartbeat {
  from {
    width: 0;
    height: 0;
  }
  to {
    width: 25px;
    height: 25px;
  }
}

.parcours-item-line .parcours-item-wrapper {
  width: 50%;
  padding: 32px;
}

.parcours-item-line .parcours-item-wrapper .parcours-item {
  border-radius: 16px;
  padding: 16px;
  background-color: rgb(var(--card-background));
}

.parcours-item-line:nth-child(even) {
  justify-content: end;
  flex-direction: row-reverse;
}

.parcours-item-line span.item-date {
  padding: 32px;
  font-weight: bold;
}

.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
}

@media screen and (max-width: 900px) {
  .parcours-item-line .parcours-item-wrapper {
    width: 100%;
    padding: 32px 0;
  }

  .parcours-item-line span.item-date.active {
    display: none;
  }

  .parcours-item-line .parcours-item-wrapper .parcours-item {
    padding: 32px;
  }

  .parcours-item-line .parcours-item-wrapper .date-dot.active:not(.noContent) {
    left: 100%;
  }
}
</style>
