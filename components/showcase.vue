<template>
<div class="bg-gray-300 rounded-lg shadow-lg overflow-hidden w-full h-full">
<img :src="project.image" :alt="project.title" class="w-full h-[200px] object-cover object-top">
<div class="p-6 ">
  <h3 class="text-xl text-black mb-2">
    {{ project.title }}
  </h3>
  <p class="text-black mb-4">
    {{ project.description }}
  </p>
  <a :href="project.link" class="text-green-400 font-semibold transform transition-all duration-300 hover:text-black hover:ps-1">
    View Project
  </a>
</div>
</div>
</template>
<script setup lang="ts">

defineProps<{
project: {
title: string
description: string
image: string
link: string
}
}>()

</script>