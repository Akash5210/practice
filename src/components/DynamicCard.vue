<template>
  <div class="child1">
    <div v-for="name in deleteName" :key="name" class="nameCard">
      <p>Hi, My name is {{ name }}</p>
      <button @click="deleteButton(name)">Delete</button>
    </div>
  </div>
</template>
<script setup>
import { computed, reactive, ref } from "vue";

let names = reactive(["pranav", "saurabh", "kaustav", "vivek"]);
let temp = ref("");
const deleteName = computed(() => {
  names = names.filter((item) => item !== temp.value);
  return names;
});
function deleteButton(name) {
  temp.value = name;
}
</script>

<style scoped>
.child1 {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  border-bottom: 1px solid black;
}
.nameCard {
  border: 1px solid black;
  width: 180px;
  display: flex;
  padding: 10px;
  margin-bottom: 10px;
}
</style>
