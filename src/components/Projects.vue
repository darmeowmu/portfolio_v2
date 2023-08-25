<template>
  <div>
    <h2 class="font-weight-bold">Projects</h2>
    <v-divider />
    <div v-for="dataItem in data" :key="dataItem.title">
      <ProjectItem v-bind="dataItem" />
    </div>
  </div>
</template>
  
<script setup lang="ts">

import { reactive } from 'vue'
import ProjectItem from '../components/ProjectItem.vue'
//@ts-ignore
import images from '../assets/images.js'

const data = reactive({
  project1: {
    title: 'SpaceX Launches',
    text: 'A project that uses Nuxt Apollo to fetch and manage data from the SpaceX GraphQL API. Both the filtering and sorting logic are composables so I can reuse stateful logic.',
    demo: 'https://meowinn-spacex-launches.netlify.app',
    repo: 'https://github.com/Meowinn/apollo_spaceX',
    imgLink: [images.spaceX_3, images.spaceX_2, images.spaceX],
    stacks: ['Vue3', 'Vuetify3', 'Nuxt3', 'TypeScript', 'GraphQL',]
  },

  project2: {
    title: 'ToDo App',
    text: 'A simple Todo application that allows users to create, edit, and delete their tasks. Used Vuetify for the layout.',
    demo: 'https://wonderful-malasada-7064f8.netlify.app/',
    repo: 'https://github.com/Meowinn/todo-nuxt-starter',
    imgLink: [images.todo_2, images.todo,],
    stacks: ['Vue3', 'Vuetify3', 'Nuxt3', 'TypeScript']
  },

  project6: {
    title: 'Portfolio',
    text: 'A minimalist website portfolio that is very fast, responsive design and functionality that showcases projects in a clean and effective way.',
    demo: 'https://winfagarang.netlify.app/',
    repo: 'https://github.com/darmeowmu/portfolio_v2',
    imgLink: [images.portfolio, images.portfolio_2, images.portfolio_3],
    stacks: ['Vue3', 'Vuetify3', 'TypeScript']
  },

  project3: {
    title: 'Shopping Website',
    text: 'An E-commerce project which uses two client-side routes. It includes a working add to cart functionality using a combination of different array methods and react state hooks.',
    demo: 'https://meowinn.github.io/project-shopping_page/',
    repo: 'https://github.com/Meowinn/top-shopping_page',
    imgLink: [images.shop, images.shop_2, images.shop_3],
    stacks: ['Bootstrap', 'JavaScript', 'React']
  },

  project4: {
    title: 'CV Generator',
    text: 'A project I have built using react. I finished this project using class-based components but I have refactored it to use mostly functional components.',
    demo: 'https://meowinn.github.io/project-cv-generator/',
    repo: 'https://github.com/Meowinn/TOP-CV_Generator',
    imgLink: [images.cv, images.cv_2],
    stacks: ['HTML', 'CSS', 'JS', 'React']
  },

  project5: {
    title: 'Weather App',
    text: 'Utilized OpenWeather Map API in this project then worked with the data to display it accordingly. I also added the feature to show data in either celsius or farenheit.',
    demo: 'https://meowinn.github.io/project-weather_App/',
    repo: 'https://github.com/Meowinn/TOP-Weather_App',
    imgLink: [images.weather, images.weather_2, images.weather_3],
    stacks: ['CSS', 'JavaScript', 'REST Api']
  }
})
</script>
  
  