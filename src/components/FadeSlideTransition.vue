<template>
  <div>
    <Transition name="fade-slide" appear>
      <slot />
    </Transition>
  </div>
</template>
<script setup>
import { Transition } from "vue";
</script>
<style scoped>
.fade-slide-enter-active,
.fade-slide-leave-active {
  transition: opacity 2s ease, transform 1s ease-in-out;
  transform: translateY(0px);
}

.fade-slide-enter-from,
.fade-slide-leave-to {
  opacity: 0;
  transform: translateY(100px);
}
</style>
