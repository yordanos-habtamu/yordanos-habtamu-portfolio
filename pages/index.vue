<template>
  <div>
    <baseheader></baseheader>

    <!-- Hero Section -->
    <section class="bg-gray-100 text-green py-20">
      <div class="container grid md:grid-cols-2 gap-8 px-4">
        <div class="col-span-1 flex flex-col justify-center items-start">
          <h1 class="text-2xl lg:text-5xl mb-4">I'm Yordanos Habtamu</h1>
          <p class="text-lg w-60 lg:w-full lg:text-2xl mb-8 ">A full stack software engineer based in Addis Ababa. Specializing in Nuxt, Vue and GoLang</p>
          <button 
            class="bg-black text-white px-6 sm:px-8 py-3 sm:py-4 rounded-full hover:border-2 hover:border-black hover:text-black hover:bg-white transition duration-100"
            @click="useScrollTo('showcase')"
          >
            View My Work
          </button>
        </div>

        <div class="flex flex-col justify-start items-center gap-1">
          <animated-ball></animated-ball>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-18 bg-white mt-6">
      <div class="container mx-auto text-center px-4">
        <div class="w-36 sm:w-48 h-36 sm:h-48 flex justify-center items-center mx-auto">
          <img src="/assets/images/mypic.png" class="object-cover rounded-full w-36 sm:w-48 h-48 sm:h-60 border-4 border-dashed border-green-400 drop-shadow-green-500 drop-shadow-2xl">
        </div>
        <p class="text-gray-500 max-w-4xl mx-auto text-base sm:text-lg leading-loose mb-6 px-2 sm:px-4 py-12">
          Hello! I'm Yordanos Habtamu, a frontend developer with a passion for building performant and user-friendly web applications. With expertise in Vue.js and Nuxt.js, I take pride in crafting solutions that are not only functional but also elegantly coded.
        </p>
        <div class="flex flex-wrap justify-center gap-2 sm:gap-x-8 gap-y-4 mb-8">
          <Skillchip v-for="(skill,index) in Skills" :key="index">{{ skill }}</Skillchip>
        </div>
        <a href="/yordanos_habtamu.pdf" download="yordanos_habtamu.pdf">
          <button class="text-green-400 px-4 sm:px-6 py-2 sm:py-3 rounded-full m-2 border-2 border-border hover:bg-green-400 hover:text-white">
            Download CV
          </button>
        </a>
      </div>
    </section>

    <Curveddivider></Curveddivider>

    <!-- Showcase Section -->
    <section id="showcase" class="py-16 bg-gray-100 rounded-b-2xl">
      <h2 class="text-black text-2xl sm:text-3xl mb-8 text-center">My Works</h2>
      <div class="container mx-auto grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-12 px-4">
        <Showcase v-for="(item,index) in Project" :key="index" :project="item"/>
      </div>
    </section>

    <Blackcurved/>

    <!-- Contact Section -->
    <section id="contact-me" class="py-18 bg-black text-white">
      <h2 class="text-white text-center text-2xl sm:text-3xl mb-4">Contact Me</h2>
      <div class="container mx-auto grid grid-cols-1 md:grid-cols-2 gap-10 px-4">
        <div class="flex flex-col p-4 sm:p-8 text-black">
          <form action="https://formspree.io/f/xgvzqlpv" method="POST">
            <input type="text" placeholder="Name" class="bg-white mt-1 p-3 w-full border rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500">
            <input type="text" placeholder="Email" class="bg-white mt-1 p-3 w-full border rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500">
            <textarea name="message" placeholder="Message" rows="5" class="bg-white mt-1 p-3 w-full border rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 resize-none"></textarea>
            <button type="submit" class="bg-green-600 rounded-full w-full px-6 py-3 mt-4 hover:bg-black hover:text-white hover:border-green-400 hover:border-2 transition-all">
              Submit Message
            </button>
          </form>
        </div>

        <div class="flex flex-col p-4 sm:p-8 text-white">
          <h2 class="text-xl sm:text-2xl font-bold text-green-400 mb-4">Interested Enough!</h2>
          <p class="text-sm sm:text-base">
            By joining my social media journey, you'll be among the first to know about new projects, collaborations, and special offers that can elevate your business and help you achieve your goals. Let's build a community of like-minded individuals who share our enthusiasm for Web Development!
          </p>

          <div class="mt-4 flex flex-wrap justify-center gap-4">
            <!-- GitHub -->
            <a href="https://github.com/yordanos-habtamu" target="_blank" rel="noopener noreferrer"
              class="group relative bg-white h-20 w-20 sm:h-24 sm:w-24 flex items-center justify-center rounded-full shadow-lg transition-transform duration-300 transform hover:scale-110 hover:bg-black">
              <span class="absolute inset-0 rounded-full border-2 border-transparent group-hover:border-green-400 transition-all duration-300 z-0"></span>
              <font-awesome-icon :icon="['fab', 'github']" class="text-3xl sm:text-4xl text-black transition-colors duration-300 group-hover:text-green-400 z-10" />
            </a>

            <!-- LinkedIn -->
            <a href="https://www.linkedin.com/in/yordanos-habtamu" target="_blank" rel="noopener noreferrer"
              class="group relative bg-white h-20 w-20 sm:h-24 sm:w-24 flex items-center justify-center rounded-full shadow-lg transition-transform duration-300 transform hover:scale-110 hover:bg-blue-700">
              <span class="absolute inset-0 rounded-full border-2 border-transparent group-hover:border-blue-700 transition-all duration-300 z-0"></span>
              <font-awesome-icon :icon="['fab', 'linkedin']" class="text-3xl sm:text-4xl text-blue-700 transition-colors duration-300 group-hover:text-white z-10" />
            </a>

            <!-- Twitter -->
            <a href="https://twitter.com/yordanos_rich" target="_blank" rel="noopener noreferrer"
              class="group relative bg-white h-20 w-20 sm:h-24 sm:w-24 flex items-center justify-center rounded-full shadow-lg transition-transform duration-300 transform hover:scale-110 hover:bg-sky-500">
              <span class="absolute inset-0 rounded-full border-2 border-transparent group-hover:border-sky-500 transition-all duration-300 z-0"></span>
              <font-awesome-icon :icon="['fab', 'twitter']" class="text-3xl sm:text-4xl text-sky-500 transition-colors duration-300 group-hover:text-white z-10" />
            </a>
          </div>
        </div>
      </div>
    </section>

    <Footer></Footer>
  </div>
</template>

    
<script setup lang="ts">



const Skills = [
    "Javascript",
    "Vue",
    "Nuxt",
    "Tailwindcss",
    "Flutter",
    "Golang"
]

const Project= [{
    "title":"FRESH MAN GUIDE ADMIN PANEL",
    "description":"A FullStack Admin panel built with flutter and firebase, for the fresh man guide application. It features analytics and all the admin controls", 
    "link":"https://github.com/yordanos-habtamu",
    "image":"/freshman_guide.png"
},
{
    "title":"Pharmacy Store and Sales Management System",
    "description":"A pharmacy store and sales management system built with Flutter and Firebase. It allows users to manage inventory, sales, and customer data efficiently.",
    "link":"https://github.com/yordanos-habtamu",
    "image":"/pharmacy_management.png"
},
{
    "title":"EcomGo",
    "description":"A containerized e-commerce application built with GoLang and MySql. It features a RESTful API for product management, user authentication, and order processing.",
    "link":"https://github.com/yordanos-habtamu",
    "image":"/ecomgo.png"
},
{
    "title":"SmartHomez",
    "description":"Simple nuxt based realstate listing web application",
    "link":"https://github.com/yordanos-habtamu",
    "image":"/smarthome.png"
},
]
</script>