<template>
  <div class="child2">
    <input type="text" v-model="searchName" />
    <div>
      <p v-for="name in filterNames" :key="name">
        {{ name }}
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive, computed } from "vue";

let searchName = ref("");
const names = reactive([
  "akash",
  "saurabh aggrawal",
  "vivek",
  "pranav",
  "omkar",
  "ankit",
  "girija",
  "pooja",
  "vishal",
  "arjun",
  "saurabh joshi",
  "subham",
  "suraj",
  "abhishek",
  "onkar",
  "akshay",
  "viplav",
  "priyanka",
  "kastov",
  "ganesh",
  "kiran",
  "sharavari",
]);
let filterNames = computed(() => {
  return names.filter((name) => name.includes(searchName.value.toLowerCase()));
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.child2 {
  margin: 10px auto;
  flex-direction: column;
  border-bottom: 1px solid black;

}
.child2 > div {
  display: flex;
  flex-wrap: wrap;
}
.child2 p{
  margin-right: 5px;
  display: flex;
  flex-wrap: wrap;
}
.child2 p::after{
  content: ",";
}
</style>
