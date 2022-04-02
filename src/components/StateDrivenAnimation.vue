<template>
  <div :class="$style.circle"></div>
</template>
<script setup>
import { ref } from "vue";
const pos = ref({
  x: 0,
  y: 0,
});

window.addEventListener(
  "mousemove",
  e => {
    console.log("mousemove", e.clientX, e.clientY);
    pos.value.x = `${e.clientX}px`;
    pos.value.y = `${e.clientY}px`;
  },
  {
    passive: true,
  }
);
</script>
<style module>
.circle {
  width: 10px;
  height: 10px;
  background: orange;
  border-radius: 50%;
  position: fixed;
  top: v-bind(pos.y);
  left: v-bind(pos.x);
}
</style>
