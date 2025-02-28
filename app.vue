<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Intro from './components/Intro.vue'
import Prog from './components/Prog.vue'
import Volunteers from './components/Volunteers.vue'
import Ticketing from './components/Ticketing.vue'
import './assets/css/normalize.css'
import './assets/css/grid.min.css'
// import './assets/css/main.scss';
</script>

<template>
  <div class="layout">
    <NuxtRouteAnnouncer />
    <!-- <NuxtWelcome /> -->
     
    <Header />

    <Intro />    

    <Prog />

    <Ticketing />

    <Volunteers />

    <Footer />
  </div>
</template>

<style lang="scss">
@use "./assets/css/main.scss" as *;
  .layout {
    // padding: $space-sm;
    min-height: 100vh;
    display: flex;
    flex-direction: column;    
  }
</style>