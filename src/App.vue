<script setup>
import { ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import FadeSlideTransition from "./components/FadeSlideTransition.vue";
import StateDrivenAnimation from "./components/StateDrivenAnimation.vue";
import AnimatingList from "./components/AnimatingList.vue";

const show = ref(true);
</script>

<template>
  <StateDrivenAnimation />
  <AnimatingList />
  <button @click="show = !show">Toggle animation</button>
  <FadeSlideTransition>
    <div v-show="show">
      <img width="200" height="200" alt="Vue logo" src="./assets/logo.png" />
      <HelloWorld msg="Hello Vue 3 + Vite" />
    </div>
  </FadeSlideTransition>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
