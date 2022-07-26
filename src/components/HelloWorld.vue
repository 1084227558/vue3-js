<script setup>
import { ref } from "vue";

defineProps({
  msg: String,
});

const count = ref(0);
const clickbtn = (e) => {
  console.log(`e`, e.target.getAttribute('data-value'))
  console.log(`e`, e.target.dataset.value)
  console.log(`e`, e)
};
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
    <ul @click="clickbtn($event)">
      <li :data-value="1">1</li>
      <li :data-value="2">2</li>
      <li :data-value="3">3</li>
    </ul>
  </div>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
.card > ul > li {
  height: 50px;
  line-height: 50px;
  background: skyblue;
  margin: 10px 0;
}
</style>
