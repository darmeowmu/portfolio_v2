<template>
  <div>
    <Title />
    <section id="projects">
      <Projects />
    </section>
    <section id="about">
      <About />
    </section>
  </div>
</template>

<script setup lang="ts">
import Title from '../components/Title.vue'
import Projects from '../components/Projects.vue'
import About from '../components/About.vue'

</script>

<style scoped>
#projects,
#about {
  padding: 1%;
}

</style>

