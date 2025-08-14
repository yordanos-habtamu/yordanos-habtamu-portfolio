<template>
  <div class="flex flex-col justify-start items-center gap-4">
    <div class="flex gap-4" ref="row1">
      <div class="ball hidden lg:bg-green-600 lg:shadow-lg lg:shadow-green-300 "></div>
      <div class="ball bg-green-600 shadow-lg shadow-green-300"></div>
      <div class="ball bg-yellow-400 shadow-lg shadow-yellow-200"></div>
      <div class="ball hidden lg:bg-red-500 lg:shadow-lg lg:shadow-red-400"></div>
    <div class="ball bg-red-500 shadow-lg shadow-red-400"></div>
    </div>

    <div class="flex gap-4" ref="row2">
        <div class="ball hidden lg:bg-green-600 lg:shadow-lg lg:shadow-green-300 "></div>
      <div class="ball bg-green-600 shadow-lg shadow-green-300"></div>
      <div class="ball bg-yellow-400 shadow-lg shadow-yellow-200"></div>
      <div class="ball bg-red-500 shadow-lg shadow-red-400"></div>
       <div class="ball hidden lg:bg-red-500 lg:shadow-lg lg:shadow-red-400"></div>

    </div>

    <div class="flex gap-4" ref="row3">
       <div class="ball hidden lg:bg-green-600 lg:shadow-lg lg:shadow-green-300"></div>
      <div class="ball bg-green-600 shadow-lg shadow-green-300"></div>
      <div class="ball bg-yellow-400 shadow-lg shadow-yellow-200"></div>
      <div class="ball bg-red-500 shadow-lg shadow-red-400"></div>
        <div class="ball hidden lg:bg-red-500 lg:shadow-lg lg:shadow-red-400"></div>

    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import gsap from "gsap";

const row1 = ref(null);
const row2 = ref(null);
const row3 = ref(null);

onMounted(() => {
  // Animate all rows
  [row1, row2, row3].forEach((row, index) => {
    gsap.to(row.value.children, {
      y: -30, // how high they go up
      repeat: -1, // infinite
      yoyo: true, // come back down
      ease: "sine.inOut",
      duration: 1.2, // speed of bounce
      stagger: {
        each: 0.2, // delay between balls
        from: "start",
      },
      delay: index * 0.4, // offset rows to not bounce together
    });
  });
});
</script>

<style scoped>
.ball {
  width: 100px;
  height: 100px;
  border-radius: 9999px;
 
}
</style>
