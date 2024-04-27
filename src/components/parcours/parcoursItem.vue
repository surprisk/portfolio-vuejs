<script>
export default {
  data() {
    return {}
  }
}
</script>

<template>
  <div class="parcours-item-line">
    <div class="parcours-item-wrapper">
      <div class="parcours-item">hello</div>
    </div>
  </div>
</template>

<style>
.parcours-item-line {
  z-index: 2;
  display: flex;
  position: relative;
}

.parcours-item-line::after {
  content: '';
  width: 18px;
  height: 18px;
  border-radius: 9px;
  background-color: rgb(var(--parcours-dot-primary));
  left: 50%;
  top: 50%;
  position: absolute;
  transform: translate(-50%, -50%);
}

.parcours-item-line:hover::after {
  cursor: pointer;
  width: 25px;
  height: 25px;
}

.parcours-item-line::before {
  content: '';
  border: 1px rgb(var(--parcours-dot-secondary)) solid;
  left: 50%;
  top: 50%;
  position: absolute;
  transform: translate(-50%, -50%);
  animation: 1s test 2s ease-out infinite;
  -webkit-animation: 1s test 2s ease-out infinite;
  border-radius: 20px;
}

@keyframes test {
  from {
    width: 0;
    height: 0;
  }
  to {
    width: 25px;
    height: 25px;
  }
}

@-webkit-keyframes test {
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
}
</style>
