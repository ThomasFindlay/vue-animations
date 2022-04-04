<template>
  <div>
    <div class="form-block">
      <label>Item name</label>
      <input type="text" v-model="itemName" />
      <button @click="addItem">Add item</button>
    </div>
    <div>
      <TransitionGroup name="slide" tag="ul" appear class="list">
        <li v-for="item of items" :key="item">
          {{ item }}
        </li>
      </TransitionGroup>
    </div>
  </div>
</template>
<script setup>
import { TransitionGroup, ref } from "vue";
const items = ref([]);
const itemName = ref("");
const addItem = () => {
  items.value.push(itemName.value);
  itemName.value = "";
};
</script>
<style scoped>
.form-block {
  display: inline-flex;
  align-items: flex-start;
  flex-direction: column;
  margin: 0 auto;
}

.form-block :is(label, input) {
  margin-bottom: 0.5rem;
}

.list {
  list-style-type: none;
  padding: 0;
}

.list li {
  margin-bottom: 0.5rem;
}

.slide-enter-active,
.slide-leave-active {
  transition: all 0.5s ease;
}
.slide-enter-from,
.slide-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
</style>
