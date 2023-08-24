<template>
  <div>
    <input type="text" v-model="name" placeholder="Enter your name" />
    <!-- <button @click="stopWatch">stop</button> -->
  </div>
</template>
<script setup>
import { ref, watch, watchEffect } from "vue";

const name = ref("");

/*it will continously watch name variable and trigger the function if name is modified
    it take two arguments
*/
watch(name, () => {
  console.log("watch method triggered");
});

/*it will continously watch name variable and trigger the function if name is modified
    it take one argument
    it will also run the very first time
    mostly uses as compared to watch
*/
watchEffect(() => {
  console.log("watchEffect method triggered", name.value);
});
</script>
<style scoped>
div {
}
</style>
