<template>
 <header class="bg-black text-white p-6">
      <div class="container mx-auto flex justify-between items-center">
       <div class="uppercase font-light">
       Yordanos habtamu
       </div>
       <nav class="hidden md:block ">
          <ul class="flex justify-around items-center">
            <li v-for="item in Headerlinks" :key="item.name" class="px-2">
                <a  :href="item.link" class="transition hover:text-green-400">{{ item.name }}</a>
            </li>
            <li>
                 <a
      href="/yordanos_habtamu.pdf"
      download="yordanos_habtamu_cv.pdf"
      class="px-4 py-2 bg-blue-600 text-white rounded-lg shadow hover:bg-blue-700 transition"
    >
      Download CV
    </a>
            </li>
          </ul>
       </nav>
      </div>
    </header>
</template>
<script setup lang="ts">
const Headerlinks =[
    {
     name:"Home",
     link:"#"
    },
   
     {
     name:"Projects",
     link:"#showcase"
    },
]
</script>