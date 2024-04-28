<template>
  <a href="#" id="arrow"><span>&#9658;&#9658;</span></a>
</template>

<style>
#arrow.left {
  transform: scale(-1);
  left: 0;
}

#arrow.right {
  right: 0;
}

#arrow {
  transition: border 0.2s linear;

  text-decoration: none;
  line-height: 0;
  margin-top: -100px;
  font-size: 40px;
  position: absolute;
  height: 0;
  top: 50%;

  border-bottom: 100px solid transparent;
  border-top: 100px solid transparent;

  border-right: 150px solid rgb(var(--project-nav));
}
#arrow > span {
  transition: margin 0.1s linear;
  font-family: 'Open Sans', 'Courier New', Courier, monospace;
  line-height: 0;
  margin-left: 65px;
  margin-top: -1px;
  position: absolute;
  display: block;
  color: white;
  height: 0;
}

#arrow:hover {
  border-right-color: rgb(var(--project-active));
}

#arrow:hover > span {
  margin-left: 75px;
}
</style>
